# 03 Homepage: frontend

Order: Hero → Perks ribbon → Shop our best sellers → The range (category tiles) → Bundle spotlight ("The three that work hardest together") → Every woman blooms (shoppable reels) → Real people, real results → Email capture → Footer.

## Hero slider
- Desktop: **fixed 16:7 ratio** whatever the copy length. Content is left-aligned with the nav's first link, with generous negative space on the right. Tablet: stacked layout with the image space on top. Mobile: fixed 10:16 ratio, image top, copy bottom.
- Slides change on dot or arrow click with a side-slide animation (new slide enters from the direction of travel, 0.52s) and autoplay every 8s. Arrows use the standard nav buttons, aligned to the content edges.
- Each slide: eyebrow, H1, body, primary + secondary CTA, desktop/tablet/mobile images.

## Perks ribbon
- Maroon band with 3 items (icon in a cream circle + text): Save 15% on every subscription order · Free shipping across Malta & Gozo · 5 stars from women of all ages, shapes and sizes. 3-up on desktop and tablet, stacked on mobile, with smaller text and icons below desktop.

## Shop our best sellers
- **Infinite carousel**, full page width. Desktop shows 4 cards; tablet shows 2.3 and mobile 1.4, with the focused card centred. Edge mask fade on both sides. Standard nav arrows overlaid on the flanks. Paging is an infinite loop with a 0.5s ease-out slide in both directions (render one buffer card on each side so it never jumps).
- Card: square pack shot (whole image links to the PDP), title, price, then a CTA row with More info + quantity + Add to bag.

## The range
- Category tiles: Beauty, Gut health, Energy, Strength, Daily essentials (+ Bundles). White caption bar under each image. Each tile links to the filtered collection.

## Bundle spotlight
- Full-bleed image with a copy panel. Separate desktop 16:9, tablet 4:5 and mobile 9:16 images. CTA "Shop the Beauty Edit" (no price in the CTA).

## Every woman blooms (reels)
- Infinite carousel: 5 per view on desktop, 2.3 on tablet, 1.4 on mobile. Cards are 9:16 posters with the creator handle. Standard nav arrows centred vertically on the flanks, edge mask fade. Hover lift stays inside the mask.
- Tap opens the reel viewer:
  - **Desktop:** modal with the 9:16 video left and the product panel right, 18px radius. Product rows show image → title → price with View + Add to bag. View swaps the panel to a mini-PDP (image, title, price, meta, flavour, quantity, Add to bag, More info). The panel scrolls inside its own height and never grows the modal.
  - **Tablet/mobile:** full-height 9:16 column, swipe up/down between reels with an animated hint. Products sit in one card (stacked thumbnails, count, names truncated to 2 lines, "View products") → sheet listing the products → product detail sheet.
  - Videos autoplay muted, looped and `playsinline` as soon as the viewer opens, restart from 0 on every change, and have a play/pause control. Closing or going to a product resets all viewer state (no leftover panel).

## Real people, real results
- Dark (ink) section, one column of testimonials: square lifestyle photo, large quote (cream), name + "Verified Buyer" tick, then the product row (thumbnail → PDP, title, price, More info outline button, Add to bag in white). Photo sits beside the text on tablet and up, stacked on mobile.
