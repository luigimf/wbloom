# 09 Welcome discount flow: backend

**Principle:** abuse protection is server-side and keyed on the email. Nothing about this flow is trusted from browser storage.

## Visitor classes
1. **Anonymous:** no customer session, no prior-login cookie (can't tell first visit from hundredth). Shown the entry point.
2. **Logged out:** has a cookie from a previous login. Not shown.
3. **Logged in:** validated session (`customer` present). Not shown.

## Endpoints (app proxy or Shopify Flow + custom app)
- `POST /apps/welcome/claim { email, goal }`
  - Rate limit per IP and per email.
  - Look up the customer by email. If they have the tag `customer-email-onboarding-discount-issued` → **409** "already used". Don't resend a new code (offer "resend my code" only through support).
  - Otherwise create or update the customer: email, tag `customer-interested-in-<goal>` (e.g. `customer-interested-in-hair_products`), and marketing consent with timestamp + source `welcome-takeover` **as a separate field from verification**. Generate a signed, single-use verification token (24h expiry) and send email 01.
- `GET /pages/welcome-verified?token=…`
  - Validate the token (unexpired, unused). Create a **unique** discount code (10%, one use, customer-eligible, first order only, 30-day expiry) via the Admin GraphQL `discountCodeBasicCreate`. Tag the customer `customer-email-onboarding-discount-issued`, send email 02, and redirect through `/discount/<CODE>?redirect=/pages/welcome-verified/success` so the code attaches to the cart.
  - Expired or used token → friendly page with "send a new link".
- Resend: same token flow, throttled (1 per minute, 5 per day).

## Data & legal
- Stores personal data and preferences. T&Cs and Privacy Policy must cover it (Branka Media). GDPR (Malta/EU): lawful basis, retention period, unsubscribe in every marketing email.

## Testing (required before launch)
End-to-end scenarios: new email → verify → code applied in cart → checkout; duplicate email; unverified then resend; expired token; used token; logged-in visitor (no entry point); rate limit; code reuse attempt at checkout. Run them as an automated suite in CI.
