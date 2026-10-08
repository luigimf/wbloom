# 02 Header & footer: backend / Shopify

- Announcement bar: section with `message` blocks (richtext, inline links allowed) and a speed setting.
- Menus: `main-menu` (Best sellers, Shop, Bundles) plus per-item dropdown settings in the header section (link list + up to 3 promo-card blocks: image, title, subtitle, link). The footer uses its own link lists.
- Search: Shopify Predictive Search API (`/search/suggest.json?resources[type]=product`) for live results. Popular searches come from a settings list (text + URL).
- 10% pill visibility: render only when `customer` is nil **and** there's no prior-login cookie (see 09). Logged-in and returning visitors never see it.
- Email capture: Shopify customer form (`{% form 'customer' %}`) with `contact[tags]=newsletter` and `accepts_marketing`. Success is shown with `form.posted_successfully?`.
