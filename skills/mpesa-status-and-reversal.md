---
name: Check transaction status and reverse a payment
description: Query the status of an M-Pesa transaction and, when needed, reverse it back to the payer.
api: openapi/mpesa-openapi.yml
operations: [generateAccessToken, transactionStatus, reversal]
---

# Check transaction status and reverse a payment

Investigate a transaction and, if warranted, return the funds. A reversal moves REAL money — require human-in-the-loop confirmation (see `agentic-access/mpesa-agentic-access.yml`).

## Steps

1. **Mint a token** — `generateAccessToken` with HTTP Basic; reuse for ~3599s.
2. **Prepare the SecurityCredential** — RSA-encrypt the initiator password with the environment's M-Pesa public certificate.
3. **Query status** — `transactionStatus` (`POST /mpesa/transactionstatus/v1/query`) with `Initiator`, `SecurityCredential`, `TransactionID`, `PartyA` = shortcode, `IdentifierType`, `ResultURL`, `QueueTimeOutURL`. Result arrives on `ResultURL`.
4. **Reverse if needed** — `reversal` (`POST /mpesa/reversal/v1/request`) with `TransactionID`, `Amount`, `ReceiverParty` = shortcode, `CommandID` `TransactionReversal`, a unique `OriginatorConversationID`, plus `ResultURL`/`QueueTimeOutURL`. Outcome is POSTed to `ResultURL`.

## Rules
- Confirm the transaction actually settled (status query) before reversing.
- Keep `OriginatorConversationID` unique per reversal to avoid double reversals; see `errors/mpesa-result-codes.yml` for outcome codes.
