# M-Pesa (Safaricom Daraja) (mpesa)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

M-Pesa is Safaricom's mobile-money platform for Kenya, exposed to developers through the Daraja API. The Daraja REST APIs let businesses collect payments (M-Pesa Express / STK Push, C2B), disburse funds (B2C, B2B), query transactions and balances, reverse payments, generate dynamic QR codes, and run standing orders — authorized with OAuth bearer tokens minted from Basic credentials, priced in Kenyan Shillings (KES).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/mpesa/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/mpesa/refs/heads/main/apis.yml)

## Tags

- Mobile Money
- Payments
- Fintech
- Kenya
- Africa
- M-Pesa

## Timestamps

- **Created:** 2026-07-17
- **Modified:** 2026-07-17

## APIs

### M-Pesa Authorization API

Mints a short-lived OAuth access token from Basic-authenticated consumer key and secret via GET /oauth/v1/generate?grant_type=client_credentials; the token is used as a Bearer credential on all other Daraja calls.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/Authorization](https://developer.safaricom.co.ke/APIs/Authorization)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- OAuth
- Authentication
- Access Token

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/Authorization)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Express (STK Push) API

M-Pesa Express, formally Lipa Na M-Pesa Online (STK Push — SIM Toolkit prompt), pushes a PIN-entry prompt to a customer's phone to authorize a paybill/till payment, plus a query endpoint to check the resulting transaction status.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/MpesaExpressSimulate](https://developer.safaricom.co.ke/APIs/MpesaExpressSimulate)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- STK Push
- Lipa Na M-Pesa
- Collections

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/MpesaExpressSimulate)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Customer To Business (C2B) API

Customer To Business lets customers pay a business paybill or till number from M-Pesa; register validation and confirmation callback URLs, and (in sandbox) simulate inbound payments.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/CustomerToBusinessRegisterURL](https://developer.safaricom.co.ke/APIs/CustomerToBusinessRegisterURL)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- C2B
- Collections
- Paybill
- Till

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/CustomerToBusinessRegisterURL)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Business To Customer (B2C) API

Business To Customer disburses funds from a business shortcode to customer M-Pesa wallets — salaries, supplier payments, winnings, refunds — with results returned asynchronously to a registered callback URL.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/BusinessToCustomer](https://developer.safaricom.co.ke/APIs/BusinessToCustomer)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- B2C
- Payouts
- Disbursement

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/BusinessToCustomer)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Business To Business (B2B) API

Business To Business moves funds between business shortcodes (paybill to paybill / till), including buy-goods and pay-bill merchant-to-merchant transfers.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/BusinessPayBill](https://developer.safaricom.co.ke/APIs/BusinessPayBill)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- B2B
- Merchant Payments

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/BusinessPayBill)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa B2B Express Checkout (USSD Push) API

B2B Express Checkout triggers a USSD push to a paying merchant's till operator to authorize a till-to-paybill payment on the spot.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/B2BExpressCheckout](https://developer.safaricom.co.ke/APIs/B2BExpressCheckout)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- B2B Express
- USSD Push
- Checkout

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/B2BExpressCheckout)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Transaction Status API

Checks the status of a completed M-Pesa transaction by transaction ID or originator conversation ID; results are delivered to a result callback URL.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/TransactionStatus](https://developer.safaricom.co.ke/APIs/TransactionStatus)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- Transaction Status
- Query

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/TransactionStatus)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Account Balance API

Queries the available and working balance of a business M-Pesa shortcode; results are returned asynchronously to a registered result URL.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/AccountBalance](https://developer.safaricom.co.ke/APIs/AccountBalance)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- Account Balance
- Query

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/AccountBalance)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Reversal API

Reverses an M-Pesa transaction, returning funds from a business shortcode back to the originating party; the outcome is posted to a result callback URL.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/Reversal](https://developer.safaricom.co.ke/APIs/Reversal)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- Reversal
- Refund

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/Reversal)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Dynamic QR Code API

Generates a dynamic M-Pesa QR code encoding a merchant, amount, and reference that a customer scans in the M-Pesa app to pay.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/DynamicQRCode](https://developer.safaricom.co.ke/APIs/DynamicQRCode)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- QR Code
- Payments

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/DynamicQRCode)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Tax Remittance API

Remits taxes from a business shortcode to the Kenya Revenue Authority (KRA) via the M-Pesa B2B tax-remittance rails.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/TaxRemittance](https://developer.safaricom.co.ke/APIs/TaxRemittance)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- Tax
- Remittance
- KRA

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/TaxRemittance)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Bill Manager API

Bill Manager lets billers onboard, send e-invoices and payment reminders, and reconcile customer bill payments through M-Pesa.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/BillManager](https://developer.safaricom.co.ke/APIs/BillManager)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- Bill Manager
- Invoicing
- Reconciliation

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/BillManager)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### M-Pesa Ratiba (Standing Order) API

M-Pesa Ratiba creates external standing orders that automatically collect recurring payments from a customer on a defined schedule.

- **Human URL:** [https://developer.safaricom.co.ke/APIs/MpesaRatiba](https://developer.safaricom.co.ke/APIs/MpesaRatiba)
- **Base URL:** `https://api.safaricom.co.ke`

#### Tags

- Ratiba
- Standing Order
- Recurring

#### Properties

- [Documentation](https://developer.safaricom.co.ke/APIs/MpesaRatiba)
- [OpenAPI](openapi/mpesa-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mpesa.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

## Common Properties

- [GitHub Organization](https://github.com/safaricom)
- [Website](https://developer.safaricom.co.ke/)
- [Documentation](https://developer.safaricom.co.ke/APIs)
- [Plans](plans/mpesa-plans-pricing.yml)
- [Rate Limits](rate-limits/mpesa-rate-limits.yml)
- [Fin Ops](finops/mpesa-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
