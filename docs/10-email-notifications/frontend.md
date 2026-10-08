# 10 Email notifications: frontend

Full spec: `emails/README.md`. Visual reference: `emails/preview.html`. Starting templates: `emails/templates/*.html` (table-based, inline styles, bulletproof buttons with VML for Outlook, mobile media query, hidden preheader).

- The 14 emails are a **sample set**. Build only the ones that apply to the real delivery workflow (Shopify, logistics, courier, subscription app).
- The templates show sample values inline, and every value maps to the Liquid variable listed in the file header comment. **Line-item rows are sample markup: wrap one row in the `{% for line in line_items %}` loop and delete the rest.**
- Logos must be PNG @2x (maroon header, cream footer). Upload them to the theme or email assets and replace the `asset_url` references.
- Keep each email under 102KB. Test in Litmus / Email on Acid (Gmail, Apple Mail, Outlook 365 + Windows, Yahoo).
