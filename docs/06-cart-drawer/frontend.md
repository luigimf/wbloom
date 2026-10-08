# 06 Cart drawer: frontend

- Slides in from the right (full width on mobile). The header shows "Your bag (n)" and a close button.
- Line items: thumbnail (→ PDP), title, variant meta, subscription badge + frequency if subscribed, quantity stepper, remove, line price.
- **Recommendations stay visible** after the first add: a "You may also like" list under a divider (thumbnail, title, Add · €price). The list scrolls; everything from the subtotal divider down is pinned to the bottom of the drawer.
- Totals: Subtotal → Subscription saving (green, if any) → **Welcome 10% · CODE · applied** (green, if a welcome code is on the session) → Delivery (emphasised; "Free" in green once over the threshold, otherwise "€x away from free delivery") → Total.
- **No discount-code field** in the drawer. Codes are auto-applied (see 09), and manual entry happens in Shopify checkout.
- Checkout button, then the "30-day money-back promise · Secure checkout" line.
- Empty state: "What's trending": the top 4 best sellers with inline Add to bag, plus a link to the full range.
