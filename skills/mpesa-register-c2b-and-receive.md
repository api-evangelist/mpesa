---
name: Register C2B callbacks and receive customer payments
description: Register validation/confirmation URLs so inbound customer paybill/till payments are delivered to your webhook, and simulate one in sandbox.
api: openapi/mpesa-openapi.yml
operations: [generateAccessToken, c2bRegisterURL, c2bSimulate]
---

# Register C2B callbacks and receive customer payments

Set up Customer-To-Business so payments customers make to your paybill/till land on your webhook.

## Steps

1. **Mint a token** — `generateAccessToken` with HTTP Basic; reuse for ~3599s.
2. **Register URLs** — `c2bRegisterURL` (`POST /mpesa/c2b/v1/registerurl`) with `ShortCode`, `ResponseType` (`Completed` | `Cancelled`), a `ValidationURL` and a `ConfirmationURL` (both publicly reachable HTTPS). Validation is opt-in (Safaricom must enable external validation for your shortcode); confirmation always fires.
3. **Receive events** — Daraja POSTs the payment to your `ConfirmationURL` (payload includes `TransID`, `TransAmount`, `MSISDN`, `BillRefNumber`); see `asyncapi/mpesa-callbacks-asyncapi.yml`.
4. **Test in sandbox** — `c2bSimulate` (`POST /mpesa/c2b/v1/simulate`, sandbox only) with `ShortCode`, `CommandID`, `Amount`, `Msisdn` (`254708374149`), `BillRefNumber` to inject a test payment. This endpoint does not exist in production.

## Rules
- Return HTTP 200 with `{"ResultCode":0,"ResultDesc":"Accepted"}` from your validation endpoint to accept a payment; a non-zero code rejects it.
- Idempotently key stored payments on `TransID` to avoid double-processing redelivered confirmations.
