# 04 Collection (Shop): frontend

- Page header with title and intro, then a filter bar:
  - **Goal** row: All, Beauty, Gut health, Energy, Strength, Daily essentials, Bundles.
  - **Format** row: Any, Powder, Capsules, Sticks & tins. Sort sits after the format pills, right-aligned on desktop and on its own full-width row on mobile.
  - Pills never break mid-label (`white-space: nowrap`) and wrap with the row indent kept. On mobile each row stacks its label above the pills.
- **Sort:** a dropdown styled to the system (not a cycling button) with Default, Price Low → High, Price High → Low, Newest. On Default, bundles pin to the top of "All products".
- Result count shown next to sort.
- **Grid:** fixed columns per breakpoint (desktop 4, tablet 3, mobile 2). Cards keep their breakpoint size and never stretch to fill a short row. Generous row gap.
- **Card:** square image (whole image → PDP), title, price, then one meta line "Citrus • 30 servings". "Unflavoured" is left out, so that line shows only "30 servings". Bundles show "Bundle • 3 products · Save €15". No flavour swatches or variant pill (variants are listed as separate products). Then Add to bag.
- Empty filter state: short message + "Clear filters".
