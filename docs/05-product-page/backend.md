# 05 Product page: backend / Shopify

- Template `templates/product.json` with blocks: gallery, title, rating (reviews app), price, description, variant picker, selling-plan picker, quantity, buy buttons, accordions (blocks: title + richtext or page/metafield source), standards strip, related products.
- **Selling plans:** whichever subscription app is chosen must expose a selling plan group "Subscribe & save 15%" with 30/45/60-day plans. The picker reads `product.selling_plan_groups`. One-time is the default unless `?plan=subscribe` is present.
- Accordion content from metafields: `custom.ingredients`, `custom.how_to_use`. Shipping & returns comes from a shared page.
- Related products: Shopify Recommendations API (`/recommendations/products.json?intent=complementary`), with a fallback to the same goal.
- Structured data: Product JSON-LD with offers, aggregateRating (from the reviews app) and brand.
