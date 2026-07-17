# M-Pesa (Safaricom Daraja) (mpesa)

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
