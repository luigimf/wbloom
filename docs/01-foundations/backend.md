# 01 Foundations: backend / Shopify

- **Theme settings (settings_schema.json):** logo (horizontal, stacked, icon × berry/cream/pink), favicon, social URLs (Instagram, TikTok, Facebook), contact email, free-delivery threshold (default €45), subscription discount % (default 15), welcome discount % (default 10).
- **Colour settings** are restricted to the palette in frontend.md. Expose them as `color_scheme` groups, not free pickers.
- **Fonts** live in theme `assets/` (WOFF2 + TTF). No Google Fonts request in production.
- **Metafields** used across the site (product): `custom.goal` (list: beauty, gut, energy, strength, daily), `custom.format` (powder, capsule, stick), `custom.servings` (int), `custom.short_description`, `custom.popularity` (int, for "Best sellers" sort), `custom.badge` (text), `custom.accent_color` (colour, used for placeholder/thumbnail fills).
- **Bundles:** model as their own products (or a bundles app), with `custom.bundle_items` (product list) and `custom.bundle_saving` (money).
- **Markets:** EUR, Malta + Gozo primary. EU delivery is calculated at checkout.
- **Performance budget:** LCP < 2.5s on 4G mobile. Responsive `srcset` on every image, lazy-load below the fold, no render-blocking third-party scripts.
