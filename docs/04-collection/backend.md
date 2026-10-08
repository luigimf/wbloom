# 04 Collection: backend / Shopify

- Use **Shopify Search & Discovery** filters on product metafields `custom.goal` and `custom.format`, rendered as pills via the Storefront filtering API (`filter.p.m.custom.goal=…`). Changing a filter updates the URL so filtered states can be shared.
- Sort maps to `sort_by`: Default → `manual` (merchandised, with bundles pinned first in the collection), `price-ascending`, `price-descending`, `created-descending`.
- Variants: the brief is to list every variant as its own card at store level. Either split flavours into separate products, or render variants as cards from `product.variants` in the collection grid. Decide before content entry.
- Meta line source: first flavour option value (omit if "Unflavoured") + `custom.servings`. Bundles use `custom.bundle_items.size` + `custom.bundle_saving`.
- Pagination: 24 per page with a "Load more" button (Section Rendering API), not infinite scroll.
