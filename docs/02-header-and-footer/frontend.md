# 02 Header & footer: frontend

## Announcement bar
- Continuous left-scrolling marquee, pink #F3489B background, white text, ✦ before and after each message. Pauses on hover. Messages are blocks (arbitrary count). Linked messages are underlined.

## Desktop nav (≥1024px)
- 3-column grid: links left (Best sellers · Shop · Bundles), **logo centred in its own column** (never a flex child, so it stays centred), actions right.
- Labels are 14px/700 uppercase with 0.04em tracking. The active/open item turns maroon with a pink underline.
- Each of Best sellers / Shop / Bundles opens **its own dropdown** on hover: a link column + 3 promo cards (image, title, sub). Shop's links are the health goals: Beauty, Gut health, Energy, Strength, Daily essentials, All products.
- Right side: **"✦ Get 10% off" pill** (anonymous visitors only, soft pink fill with maroon text; reads "10% off" under 1200px; see 09), search icon, Bag pill (maroon, "Bag · {count}").

## Mobile/tablet nav (<1024px)
- 3-column grid with equal outer columns: hamburger left, logo centred, search + bag right.
- Drawer: 10% row on top (anonymous only), then Best sellers, Shop (goals nested and indented flush with the parent label), Bundles, About, Subscriptions.

## Search
- Icon opens a compact panel (desktop: 440px wide, anchored top-right; mobile: full width with 10px inset) over a dimmed backdrop. It has an input, "Popular searches" chips, and live results (thumbnail, title, price). Esc and the backdrop close it.

## Email capture (above every footer, on every page)
- "Join the Bloom Club" band with an inline email field and button. Success state replaces the form. Uses the same consent copy as 09.

## Footer
- Maroon background, large icon mark, link columns (Shop, Help, About, Subscriptions page), socials, legal line. Linked text is underlined.
