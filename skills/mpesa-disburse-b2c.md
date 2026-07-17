---
name: Disburse funds to a customer (B2C)
description: Pay out from a business shortcode to a customer M-Pesa wallet — salaries, refunds, winnings — and reconcile the async result.
api: openapi/mpesa-openapi.yml
operations: [generateAccessToken, b2cPaymentRequest]
---

# Disburse funds to a customer (B2C)

Move money from your business shortcode to a customer's M-Pesa wallet. This moves REAL money in KES — require human-in-the-loop confirmation before executing (see `agentic-access/mpesa-agentic-access.yml`).

## Steps

1. **Mint a token** — `generateAccessToken` with HTTP Basic (consumer key/secret); reuse for ~3599s.
2. **Prepare the SecurityCredential** — encrypt the initiator password with the M-Pesa public X.509 certificate (RSA) for your environment (sandbox and production certs differ; see `authentication/mpesa-authentication.yml`).
3. **Send the payout** — `b2cPaymentRequest` (`POST /mpesa/b2c/v3/paymentrequest`) with the bearer token, `InitiatorName`, `SecurityCredential`, `CommandID` (`SalaryPayment` | `BusinessPayment` | `PromotionPayment`), `Amount`, `PartyA` = shortcode, `PartyB` = customer MSISDN, a unique `OriginatorConversationID`, plus `ResultURL` and `QueueTimeOutURL`. The synchronous response is only an acknowledgement.
4. **Await the result** — the outcome is POSTed to your `ResultURL`; `ResultCode` `0` = paid. A timeout is delivered to `QueueTimeOutURL`.

## Rules
- Supply a stable unique `OriginatorConversationID` per payout so retries do not double-pay (Daraja de-dupes on it; see `conventions/mpesa-conventions.yml`).
- Do not retry until you have seen the `ResultURL` callback or a `QueueTimeOutURL` timeout.
