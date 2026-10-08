# Woman Bloom — email notification specs

`preview.html` is the visual reference for all 14 emails. `templates/` holds email-client-safe starting HTML for each one. Every email uses the same shell plus a small set of content blocks, so build them once as partials and compose.

> **These are samples, not a fixed list.** The final set depends on how orders actually flow: the Shopify setup, the fulfilment/logistics process, the delivery partner(s) and the subscription app chosen. Build only the emails that apply to the business. For example, drop *Delivered* if the courier doesn't send delivery events, or add *Out for delivery* / *Ready for pickup* if the partner supports them. Adapt triggers, timings, courier names and tracking copy to the real workflow. Any new email should reuse the same shell and blocks.

## Platforms
- **Shopify notifications** (Settings → Notifications → Customer notifications): account invite, password reset, order confirmation, shipping confirmation, delivered, order canceled, refund, abandoned checkout. Edit the Liquid templates directly; variables below are Shopify's.
- **Subscription app** (Shopify Subscriptions / Recharge / Seal — whichever is chosen): subscription created, upcoming order, payment failed, cancelled. Variable names differ per app; the ones shown are descriptive. Rebuild the app's templates with the same shell and blocks.
- **Welcome flow** (custom): verify + code emails, sent from Shopify Flow → Shopify Email / Klaviyo. See "Welcome discount flow" in `Developer notes.md`.

## Build rules (email-client safe)
- 600px fixed-width centred table, fluid down to 320px (`width:100%; max-width:600px`). Tables for layout, **all styles inline**. A `<style>` block is only for `@media (max-width: 620px)` tweaks and dark mode.
- Mobile (≤620px): side padding 48px → 24px; hero title 30px → 26px; info cells stack to one column; step tracker labels 12px → 11px.
- Buttons: "bulletproof" buttons (table cell with background + padded `<a>`; add a VML roundrect for Outlook). Min height 48px.
- Images: logo as **PNG @2x** (SVG doesn't render in Gmail/Outlook): header 36px tall in maroon, footer 30px tall in cream. Product thumbs 64×64 (send 128×128), 12px radius (square in Outlook is fine). Always set `alt`, `width` and `height`.
- Fonts: `Figtree, Arial, Helvetica, sans-serif`. Load Figtree via `@font-face` (Apple Mail / iOS render it); everything else falls back to Arial, and the layout must hold with Arial.
- Keep each email under 102KB of HTML so Gmail doesn't clip it.
- Preheader: hidden div at the top of `<body>`, padded with `&zwnj;&nbsp;` so body text doesn't leak into the inbox preview.
- Dark mode: keep the white body; add `color-scheme: light` meta. The maroon footer and pink code box hold up under auto-inversion; test in Gmail iOS and Outlook.
- Accessibility: `lang="en"`, `role="presentation"` on layout tables, body text ≥14px (footer 12px minimum), all text colours below meet 4.5:1 on their backgrounds.

## Tokens
| Token | Value | Use |
|---|---|---|
| Ink | `#2B1620` | headings, body text on light |
| Muted | `#6E545C` | body copy, meta |
| Label | `#A9909A` | small caps labels (12px+, bold only) |
| Maroon | `#8C1F52` | buttons, footer, accents |
| Pink | `#F3489B` | eyebrows, code box border |
| Pink tint | `#FBE3EE` | code box, callout |
| Cream | `#FFF7F1` | info panel, button text |
| Footer text | `#F6D4E4` | secondary text on maroon |
| Border | `#F0E2DB` / `#F7EDE8` | dividers |
| Success | `#12805A` | discount/saving rows |
| Canvas | `#EDE4E0` | outer background behind the 600px card |

Type: eyebrow 12px/800/0.14em caps · H1 30px/700/1.15 · body 16px/1.6 · item title 16px/700 · meta 13px · labels 11–12px/800/0.12em caps · total 18px/800.

## Shell
1. Header: 30px top / 26px bottom padding, centred logo, 1px `#F0E2DB` bottom border.
2. Content blocks (in order per email), 48px side padding.
3. 44px spacer.
4. Footer (maroon): cream logo → links (Shop · Subscriptions · FAQ · Contact, 14px/700) → socials (13px) → "Questions? Reply to this email or write to hello@womanbloom.com" + "Woman Bloom · Malta" (12px). **Marketing emails only** also get the line "You're getting this because… Unsubscribe" (`{{ unsubscribe_url }}`). Replies go to a monitored inbox.

## Blocks
- **Hero:** eyebrow (pink) / title / body, centred, 40px top padding.
- **Button:** maroon pill, 16px/700 cream text, 16×34px padding, 28px top margin.
- **Code:** 2px dashed pink border, pink tint fill, 16px radius; code in monospace 26px/700/0.14em maroon; note 13px muted below.
- **Step tracker:** 4 steps (Ordered · Packed · On its way · Delivered). Done/current steps: maroon dot and bar; upcoming steps: `#E3D2CB` dot and `#F0E2DB` bar. Build as a 4-column table with a 3px line behind 14px dots.
- **Items:** caps heading + rule; each row has a 64px thumb, title and variant meta (`Citrus • 30 servings`), and price + qty right-aligned; `#F7EDE8` divider.
- **Totals:** label/value rows 15px muted; discount rows green with the code name; final row 18px/800 ink with 10px extra top space.
- **Info panel:** cream fill, 16px radius, 2-column grid (stacks on mobile), caps label + multi-line value.
- **Callout:** pink tint, 16px radius, centred title 17px/700 maroon + 14px body.
- **Small print:** 13px muted, centred.

## Emails
| # | Email | Template | Trigger | Marketing |
|---|---|---|---|---|
| 01 | Welcome · verify email | Custom (Flow) | New email in welcome takeover | No (transactional) |
| 02 | Welcome · your 10% code | Custom (Flow) | Verify link tapped; tag `customer-email-onboarding-discount-issued` | **Yes** |
| 03 | Account invite | Customer account invite | Invite / account created | No |
| 04 | Password reset | Customer password reset | Reset requested | No |
| 05 | Order confirmation | Order confirmation | Order placed | No |
| 06 | Shipping confirmation | Shipping confirmation | Fulfilled with tracking | No |
| 07 | Delivered | Delivered | Carrier delivered event | No |
| 08 | Order cancelled | Order canceled | Order cancelled | No |
| 09 | Refund issued | Refund | Refund created | No |
| 10 | Subscription confirmed | Sub app | Contract created | No |
| 11 | Upcoming order reminder | Sub app | 2 days before charge | No |
| 12 | Payment failed | Sub app (dunning) | Billing attempt failed; retry every 3 days, pause after 3 | No |
| 13 | Subscription cancelled | Sub app | Contract cancelled | No |
| 14 | Abandoned checkout | Abandoned checkout | 1h after abandoned checkout, consented only | **Yes** |

Subjects, preheaders, copy and variables per email are on each card in the canvas and are final copy unless the brand team edits them.

## Links
- Code email button → `/discount/{{ code }}?redirect=/collections/{{ goal }}` (auto-applies the code; the cart drawer shows it as applied).
- Delivered → product page with the subscription option preselected.
- Every manage/edit/skip link → the subscription app's customer portal (deep-link straight to the action where the app allows it).

## QA before launch
- Litmus / Email on Acid across Gmail (web, iOS, Android), Apple Mail (macOS, iOS), Outlook (365, Windows desktop, web), Yahoo.
- Send every Shopify template through Shopify's "Send test email", and check Liquid fallbacks: no first name, single item, 5+ items, discount + subscription saving together, free vs paid delivery.
- Check every link (UTM tags: `utm_source=email&utm_medium=transactional|marketing&utm_campaign=<email-id>`).
- Add these emails to the end-to-end test suite for the welcome flow (see `Developer notes.md`).
