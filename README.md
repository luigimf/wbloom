# Woman Bloom: developer handoff

Custom Shopify theme for Woman Bloom (women's supplements, Malta). No purchased theme: every component is a custom section or block, editable in the Theme Editor and built on one shared design language.

## What's here
| Folder | Contents |
|---|---|
| `prototype/` | `index.html`: the full clickable prototype (single file, open it in a browser). `assets/` holds the campaign banner images it swaps per breakpoint. Deploy both together. |
| `emails/` | `preview.html`: all 14 emails in a browsable viewer. `templates/`: one email-client-safe HTML file per email. `README.md`: full email spec. |
| `docs/` | One folder per work area, each with `frontend.md` and `backend.md`. |
| `brand-assets/` | Logos (SVG, every lockup and colour) and Figtree fonts (variable TTF, OFL licence). |

## Work areas (`docs/`)
01 Foundations · 02 Header & footer · 03 Homepage · 04 Collection · 05 Product page · 06 Cart drawer · 07 Subscriptions page · 08 About, FAQ & contact · 09 Welcome discount flow · 10 Email notifications

## Using the prototype
- The Tweaks panel isn't in the exported file. The breakpoint preview and visitor-state switch only exist in the design tool; resize the browser to see the responsive behaviour.
- All copy is final unless marked otherwise. Product data, prices, reviews and customer names are sample content.
- Image placeholders show the art-direction brief for each crop (ratio + subject). In Shopify each becomes an image picker, with that brief as the help text.

## Non-negotiables
- **Theme Editor first:** every section exposes its copy, images, links, colours (from the palette) and block order as settings. No hard-coded copy.
- **Linked text is underlined**, in every text setting (see 01 Foundations).
- **Inline styles in the prototype are not the build.** Turn the values into CSS custom properties and a component stylesheet.
- **Test automation:** the welcome discount and subscription flows are multi-step customer journeys. Budget for end-to-end tests and a regression suite before launch (see 09).

## Owners / open items
- Legal (Branka Media): T&Cs and Privacy Policy must cover the welcome flow's data capture and marketing consent.
- Subscription app not chosen yet: Shopify Subscriptions, Recharge or Seal. This affects 05, 06, 07 and 10.
- Courier / delivery workflow decides which shipping emails ship (see 10).
