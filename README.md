# J.P. Morgan Payments Developer Portal — Commerce APIs Bruno Collection

A [Bruno](https://www.usebruno.com/) collection of ready-to-run requests for J.P. Morgan's Payments Developer Portal (PDP) Commerce APIs. Bruno is a fast, open-source, offline-first API client — collections are stored as plain-text `.bru` files, so this repository can be opened directly in the Bruno app with no import step required.

The collection covers Checkout, Online Payments, 3-D Secure, Account Updater, Consumer Profile Management, Tokenization, Verifications, Wallet Decryptions, and Notifications. This README only provides a high-level overview — for full API reference material and integration guides, see the official [J.P. Morgan Payments Developer Portal documentation](https://developer.payments.jpmorgan.com/docs/home).

## Disclaimer

> **Use at Your Own Risk.** The code and instructions provided in this repository are intended for reference purposes only. The maintainers of this repository do not assume any responsibility for any issues, damages, or losses that may arise from the use of this code or instructions.

---

## What's Inside

This is a high-level index only — folders are grouped by API, and each contains ready-to-send requests for that API's endpoints.

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
| `environments/` | Environment variable sets (base URLs, credentials, test data) shared across requests |

For full endpoint documentation, request/response schemas, and field-level constraints, refer to the official [J.P. Morgan Payments Developer Portal](https://developer.payments.jpmorgan.com/docs/home).

---

## Installation

1. Install [Bruno](https://www.usebruno.com/) — available for Windows, macOS, and Linux.
2. In Bruno, choose **Open Collection** and select this repository's root folder (`bruno.json` identifies it as a Bruno collection).
3. Select the `CAT ENV` environment (or create your own) from the environment picker in the top right of the Bruno window.

---

## Usage

1. Open the `CAT ENV` environment and fill in your credentials — `clientId`, `gOauth_Priv_Key`, `kid`, `merchant-id`, and any other values marked with `<YOUR_...>` placeholders.
2. Run **JWT and Access Token.bru** (or **Only Access Token.bru** if you already have a signed client assertion) to exchange credentials for an access token. Collection-level OAuth2 (client credentials) is already configured in `collection.bru` to auto-fetch and auto-refresh tokens for every subsequent request.
3. Open any folder (e.g. `Checkout/`, `Online Payments/`, `3-D Secure/`) and send a request. Pre-request and post-response scripts populate the environment variables (`transactionId`, `consumerprofileid`, etc.) that dependent requests rely on.

> For step-by-step integration guides and full field documentation, see the official [J.P. Morgan Payments Developer Portal](https://developer.payments.jpmorgan.com/docs/home).

---

## Repo Structure

```
.
├── 3-D Secure/                        # 3DS authentication requests
├── Account Updater/                   # Discover / Mastercard / Visa account updater requests
├── Checkout/                          # Checkout Drop-in / Hosted Payments Page requests
├── Consumer Profile Management/       # Consumer profile, address, and payment method requests
├── Notifications/                     # Webhook subscription management requests
├── Online Payments/                   # Auth, capture, void, refund, and verification requests
├── Tokenization/                      # Tokenization requests
├── Verifications/                     # Verification requests
├── Wallet Decryptions/                # Wallet decryption requests
├── environments/                      # Environment variable sets (e.g. CAT ENV.bru)
├── bruno.json                         # Bruno collection manifest
├── collection.bru                     # Collection-level OAuth2 configuration
├── JWT and Access Token.bru           # JWT signing + token exchange request
├── Only Access Token.bru              # Token exchange request using a pre-built assertion
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
