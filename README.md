# J.P. Morgan Payments — Bruno Collections

[Bruno](https://www.usebruno.com/) collections of ready-to-run requests for the J.P. Morgan Payments APIs. Bruno is a fast, open-source, offline-first API client — collections are stored as plain-text `.bru` files, so this repository can be opened directly in the Bruno app with no import step required.

This repository currently hosts one collection, [`merchant-services/`](merchant-services/), covering Checkout, Online Payments, 3-D Secure, Account Updater, Consumer Profile Management, Tokenization, Verifications, Wallet Decryptions, and Notifications. This README only provides a high-level overview — for full API reference material and integration guides, see the official [J.P. Morgan Payments documentation](https://developer.payments.jpmorgan.com/docs/home) on the Payments Developer Portal.

## Disclaimer

> **Use at Your Own Risk.** The code and instructions provided in this repository are intended for reference purposes only. The maintainers of this repository do not assume any responsibility for any issues, damages, or losses that may arise from the use of this code or instructions.

---

## What's Inside

Each top-level folder is a separate, self-contained Bruno collection (own `bruno.json` and `collection.bru`). This is a high-level index only — see each collection's `collection.bru` docs for details.

| Folder | Purpose |
| ------ | ------- |
| [`merchant-services/`](merchant-services/) | Checkout, Online Payments, 3-D Secure, Account Updater, Consumer Profile Management, Tokenization, Verifications, Wallet Decryptions, and Notifications requests |

Within `merchant-services/`, folders are grouped by API, each containing ready-to-send requests for that API's endpoints:

| Folder | Purpose |
| ------ | ------- |
| `Checkout/` | Checkout Drop-in / Hosted Payments Page intent and notification requests |
| `Online Payments/` | Card, wallet, and alternative payment method authorization, capture, void, refund, and verification requests |
| `3-D Secure/` | 3-D Secure authentication preparation, frictionless, and challenge flows |
| `Account Updater/` | Discover, Mastercard, and Visa account updater requests |
| `Consumer Profile Management/` | Create, retrieve, update, and delete consumer profiles, addresses, and payment methods |
| `Notifications/` | Manage webhook subscriptions and event types |
| `Tokenization/` | Token vaulting requests |
| `Verifications/` | Account/entity verification requests |
| `Wallet Decryptions/` | Wallet payload decryption requests |
For full endpoint documentation, request/response schemas, and field-level constraints, refer to the official [J.P. Morgan Payments documentation](https://developer.payments.jpmorgan.com/docs/home) on the Payments Developer Portal.

---

## Installation

1. Install [Bruno](https://www.usebruno.com/) — available for Windows, macOS, and Linux.
2. In Bruno, choose **Open Collection** and select the collection folder you want to use (e.g. `merchant-services/`, which contains its own `bruno.json`).
3. Configure the collection variables in Bruno's environment settings.

---

## Usage

1. Fill in the user-supplied secret variables in Bruno's secrets tab: `clientId`, `kid`, `merchantId`, `gOauth_Priv_Key`, and `resourceId`. The token request scripts populate `JWSPayload` and `auth-token` automatically.
2. Run **JWT and Access Token.bru** (or **Only Access Token.bru** if you already have a signed client assertion) to exchange credentials for an access token. Collection-level OAuth2 (client credentials) is already configured in `collection.bru` to auto-fetch and auto-refresh tokens for every subsequent request.
3. Open any folder (e.g. `Checkout/`, `Online Payments/`, `3-D Secure/`) and send a request. Pre-request and post-response scripts populate the environment variables (`transactionId`, `consumerprofileid`, etc.) that dependent requests rely on.

> For step-by-step integration guides and full field documentation, see the official [J.P. Morgan Payments documentation](https://developer.payments.jpmorgan.com/docs/home) on the Payments Developer Portal.

---

## Repo Structure

```
.
├── merchant-services/                 # Bruno collection: Commerce APIs
│   ├── 3-D Secure/                    # 3DS authentication requests
│   ├── Account Updater/               # Discover / Mastercard / Visa account updater requests
│   ├── Checkout/                      # Checkout Drop-in / Hosted Payments Page requests
│   ├── Consumer Profile Management/   # Consumer profile, address, and payment method requests
│   ├── Notifications/                 # Webhook subscription management requests
│   ├── Online Payments/               # Auth, capture, void, refund, and verification requests
│   ├── Tokenization/                  # Tokenization requests
│   ├── Verifications/                 # Verification requests
│   ├── Wallet Decryptions/            # Wallet decryption requests
│   ├── bruno.json                     # Bruno collection manifest
│   ├── collection.bru                 # Collection-level OAuth2 configuration
│   ├── JWT and Access Token.bru       # JWT signing + token exchange request
│   └── Only Access Token.bru          # Token exchange request using a pre-built assertion
├── LICENSE
└── README.md
```

---

## Contributing to JPMC Projects

Only valid contributors are able to provide contributions to this repository.

If this is your first time contributing to JPMC codebases you will need to fill out our Contribution Licence Agreement (CLA). More information can be found at: <https://github.com/jpmorganchase/.github/blob/main/CONTRIBUTING.md>

---

## License

This project is licensed under the Apache License 2.0 — see the [LICENSE](LICENSE) file for details.
