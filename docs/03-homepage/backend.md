# 03 Homepage: backend / Shopify

Every block below is a section on `templates/index.json` and can be reordered and duplicated.
- **Hero:** blocks = slides (eyebrow, heading, body, CTA 1/2 label + link, image desktop/tablet/mobile, text colour scheme). Settings: autoplay seconds.
- **Perks ribbon:** blocks = perk (icon select from a fixed set, richtext).
- **Best sellers:** collection picker (default a `best-sellers` smart collection sorted by `custom.popularity`), product limit (default 8). Add to bag posts to `/cart/add.js` and opens the drawer.
- **Range:** blocks = tile (image, label, collection or filtered URL).
- **Bundle spotlight:** product picker (the bundle), heading, body, CTA label, three images.
- **Reels:** blocks = reel (video file or Shopify-hosted video, poster image, creator handle, products [product list]). Video ≤ 15MB, H.264 MP4 plus a WebM if possible, 1080×1920.
- **Testimonials:** blocks = review (photo, quote, name, product). Long-term this could be fed from a reviews app (Judge.me / Okendo); keep the block layout.
- Sample product data, prices and reviews in the prototype are placeholders and come from Shopify.
