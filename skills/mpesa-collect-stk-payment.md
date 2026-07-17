---
name: Collect a payment with M-Pesa Express (STK Push)
description: Prompt a Kenyan customer's phone for their M-Pesa PIN to collect a paybill/till payment, then confirm the outcome.
api: openapi/mpesa-openapi.yml
operations: [generateAccessToken, stkPush, stkPushQuery]
---

# Collect a payment with M-Pesa Express (STK Push)

Use this to charge a customer by pushing a PIN-entry prompt to their phone.

## Steps

1. **Mint a token** — call `generateAccessToken` (`GET /oauth/v1/generate?grant_type=client_credentials`) with HTTP Basic auth (consumer key = username, consumer secret = password). Cache the `access_token` and reuse it for ~3599s (see `conventions/mpesa-conventions.yml`); do not re-mint per request.
2. **Build the password** — `Password = Base64(BusinessShortCode + Passkey + Timestamp)` where `Timestamp` is `YYYYMMDDHHMMSS`. In sandbox use shortcode `174379` and the published test passkey (see `sandbox/mpesa-sandbox.yml`).
3. **Initiate** — call `stkPush` (`POST /mpesa/stkpush/v1/processrequest`) with the bearer token, `Amount` (whole KES), `PhoneNumber`/`PartyA` = customer MSISDN `2547XXXXXXXX`, `TransactionType` = `CustomerPayBillOnline` or `CustomerBuyGoodsOnline`, `AccountReference`, and a publicly reachable HTTPS `CallBackURL`. A `ResponseCode` of `0` means the prompt was accepted — NOT that payment succeeded.
4. **Await the callback** — the real result is POSTed to your `CallBackURL` (see `asyncapi/mpesa-callbacks-asyncapi.yml`). `ResultCode` `0` = paid; `1032` = user cancelled; `1037` = timeout/unreachable; `1` = insufficient funds; `2001` = wrong PIN (see `errors/mpesa-result-codes.yml`).
5. **Reconcile if no callback** — call `stkPushQuery` (`POST /mpesa/stkpushquery/v1/query`) with the `CheckoutRequestID` to poll the status. Treat the callback as the source of truth.

## Rules
- Keep `AccountReference`/`CheckoutRequestID` unique per logical payment to detect duplicates on retry.
- Never retry a payment on timeout without first querying — the customer may still be entering their PIN.
