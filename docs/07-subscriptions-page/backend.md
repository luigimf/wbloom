# 07 Subscriptions page: backend / Shopify

- Page template `templates/page.subscriptions.json` with sections: hero (image, badge text, heading, body, CTA label, manage link), perks (blocks), product grid (collection picker, default "subscribable"), comparison table (blocks: row label + one-time ✓/✕ toggle), testimonials (blocks), FAQ (blocks or metaobject list).
- Subscribed price = `variant.price × (1 − plan discount)`, read from the selling plan's `price_adjustments`, never hard-coded.
- "Manage it here" → the subscription app's customer portal URL (logged in) or the account login with a return URL.
- Product grid links append `?plan=subscribe`.
