# J.P. Morgan Payments — Merchant Services

## Usage

1. Fill in the user-supplied secret variables in Bruno's secrets tab: `clientId`, `kid`, `merchantId`, `gOauth_Priv_Key`, and `resourceId`. The token request scripts populate `JWSPayload` and `auth-token` automatically.
2. Run **JWT and Access Token.bru** (or **Only Access Token.bru** if you already have a signed client assertion) to exchange credentials for an access token. Collection-level OAuth2 (client credentials) is already configured in `collection.bru` to auto-fetch and auto-refresh tokens for every subsequent request.
   a. Disputes needs an additional token, get that on the Auth tab of the `Disputes` folder, after getting the access token in step 2.
3. Open any folder (e.g. `Checkout/`, `Online Payments/`, `3-D Secure/`) and send a request. Pre-request and post-response scripts populate the environment variables (`transactionId`, `consumerprofileid`, etc.) that dependent requests rely on.

> For step-by-step integration guides and full field documentation, see the official [J.P. Morgan Payments documentation](https://developer.payments.jpmorgan.com/docs/home) on the Payments Developer Portal.

## Runbooks

Both `Checkout/` and `Online Payments/` contain a `00 Runbook` folder — an ordered, step-by-step walkthrough of that product's capabilities. Each numbered step folder has its own `docs` note with a link to the matching guide on the official Payments Developer Portal. Open the folder for the area you're working on and follow the link there for the full request/response field reference. `Disputes/` is broken down by type, then response, and within each is are the runbook steps.

> **Tip:** These notes use Bruno's built-in documentation feature. In the Bruno app, select a folder (or request) and open the **Docs** tab to read its notes and follow the links. Each `00 Runbook` step folder's `docs` note contains only a link to the official documentation for that folder's actions; this overview (also kept in the collection's own `docs`) is the collection-level `collection.bru` at the root.

## Entitlements

Some actions are entitlement-gated per merchant ID, per brand or function (e.g. Account Updater by brand — Discover, Mastercard, Visa; 3-D Secure as a function). Requests for actions your `merchantId` isn't entitled to will fail; that is expected.
