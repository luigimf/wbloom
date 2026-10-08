# 01 Foundations: frontend

## Colour tokens
| Token | Hex | Use |
|---|---|---|
| --wb-ink | #2B1620 | text, dark buttons |
| --wb-muted | #6E545C | body copy, meta |
| --wb-label | #A9909A | small-caps labels (bold only) |
| --wb-maroon | #8C1F52 | primary buttons, accents, footer |
| --wb-maroon-dark | #6E1740 | primary hover |
| --wb-pink | #F3489B | announcement bar, highlights, link hover |
| --wb-pink-tint | #FBE3EE | soft fills, chips, 10% pill |
| --wb-cream | #FFF7F1 | page background, light text on dark |
| --wb-surface | #FEFDFD / #FFFFFF | section and card fills |
| --wb-sand | #FBF4F0 | alternate section fill |
| --wb-border | #F0E2DB (#E3D2CB for controls) | dividers, inputs |
| --wb-success | #12805A | savings, discount rows |
Text contrast is ≥ 4.5:1 everywhere. Never use alpha-muted text on photos.

## Type
- **Figtree**: body, UI and all section headings (H1/H2 Bold 700). Weights 400–800.
- **Sora**: secondary display (mobile menu items, select accents). Audit usage and ship only the weights still referenced.
- Self-host as WOFF2 with TTF fallback, `font-display: swap`, preload Figtree 400 + 700. Variable sources are in `brand-assets/fonts/`.
- Scale: use `clamp()` with `vw`, matching the prototype's min/max values. H1 hero ≈ 38→64px, H2 section ≈ 30→48px, body 15→18px, labels 11–12px/800/0.12–0.16em caps. Mobile body text is never below 16px in inputs (stops iOS zooming in).
- `text-wrap: pretty` on headings and paragraphs.

## Breakpoints
| | width | page padding | nav |
|---|---|---|---|
| Mobile | < 640px | 20px | hamburger drawer |
| Tablet | 640–1023px | 28px | hamburger drawer |
| Desktop | ≥ 1024px | 40px (max content 1280–1400px) | full nav + dropdowns |

## Components (global)
- **Buttons:** pill (999px radius). Primary is maroon with a cream label (hover #6E1740); secondary is outline ink/maroon; light is cream on dark. Min height 44px on touch.
- **Carousel nav buttons (site standard):** 52px white circle, 1.5px border rgba(43,22,32,0.22), ink arrow ← →; on hover, fill #FBE3EE with a maroon border. Used by the hero, best sellers and reels.
- **Edge fade:** carousels that bleed full-width use a CSS `mask-image` linear gradient (≈9% each side on desktop, 5.5% tablet, 13% mobile), not an overlay div, so hover lifts stay inside the mask.
- **Hover lift:** cards translateY(-4px) + shadow 0 14px 26px -14px rgba(43,22,32,0.34), 180ms.
- **Linked text:** any text setting that contains a link renders it underlined (offset 3px, thickness 1.5px), inherits the surrounding colour, and turns pink #F3489B on hover.
- **Radii:** cards 20px, media 16–22px, chips/buttons 999px, sheets 18–24px.
- **Scrollbars** are hidden on touch rails (`scrollbar-width: none`); content still scrolls.
- **Motion:** 180–500ms, ease `cubic-bezier(0.33,1,0.68,1)` for slides and `(0.4,0,0.2,1)` for accordions. Respect `prefers-reduced-motion`.
