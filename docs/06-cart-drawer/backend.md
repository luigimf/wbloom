# 06 Cart drawer: backend / Shopify

- Cart AJAX API: `/cart.js`, `/cart/add.js`, `/cart/change.js`. Re-render the drawer via the Section Rendering API (`sections=cart-drawer`) after every mutation.
- Selling plan on a line: `item.selling_plan_allocation`. Saving = `compare_at_price - price` per allocation.
- Applied discounts: `cart.cart_level_discount_applications` / `item.line_level_discount_allocations`. Show the code title from `discount_application.title`.
- Free-delivery threshold comes from theme settings and must match the Shopify shipping rate rule (free over €45, Malta & Gozo).
- Recommendations: Recommendations API based on the first line item, excluding items already in the cart. Fall back to the best-sellers collection.
