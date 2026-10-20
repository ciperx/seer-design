# Seer — Electric Foundation, six interfaces

Design submission for the Seer rebrand brief (poidh mainnet bounty #38). Six connected interfaces,
one shared market primitive, one visual language.

## The six demos

| # | Interface | Live demo | What it is |
|---|-----------|-----------|------------|
| 1 | Seer homepage | https://ciperx.github.io/seer-design/ | The protocol beneath the applications: the map, the layer stack, entry points |
| 2 | Seer app (explorer) | https://ciperx.github.io/seer-design/app.html | Etherscan-equivalent over every Seer market: filter, book ladder, sparkline, positions, order panel |
| 3 | Deep | https://ciperx.github.io/seer-design/deep.html | Many-outcome liquidity venue: cumulative depth curve, execution model, LP tranches |
| 4 | Futarchy | https://ciperx.github.io/seer-design/futarchy.html | Conditional markets on PIP-27, the decision memo, KPI definition, resolution steps |
| 5 | Opportunity markets | https://ciperx.github.io/seer-design/opportunity.html | Board of competing submissions, market-implied favourite, spread, back-this-design panel |
| 6 | Risk pricing — "Soundings" | https://ciperx.github.io/seer-design/risk.html | Risk compared across protocols: modelled LGD, market-implied probability, depth score, caveats |

Preview poster (2×3 thumbnails of all six): https://ciperx.github.io/seer-design/preview.html

## Design rationale (short)

The brief asks for six interfaces that still read as one ecosystem. Two decisions carry that:

1. **One substrate, one grammar.** Near-black background with a faint 88px grid, hairline borders,
   mono for every number, sans for prose. Cyan (`#35e0ff`) means *information* (prices, depth,
   market estimates); volt lime (`#c8ff3c`) means *action* (the one primary button per view, the
   active nav pill). Nothing else is coloured, so a trader can move between surfaces without
   relearning where to look.
2. **Each surface answers one question, in the same layout rhythm.** Every page opens with an
   eyebrow + one statement, then a stat strip, then the working surface: for the app a table and a
   book, for Deep a depth curve, for Futarchy two conditional prices, for Opportunity a selection
   board, for Soundings a risk ladder. Same skeleton, different instrument.

## Deliberate departures from the EF brand kit

- **Sharper substrate.** EF sits on a lighter, softer base; here the base is `#05070a` with the grid
  at 35% opacity. At six interfaces the eye needs one calm plane — glow and grids do the depth work
  instead of panels.
- **Two accents, strict roles.** The kit treats cyan and lime as a palette; we assign them fixed
  meanings (information vs action) and forbid them elsewhere. That is what keeps the family
  coherent when a view gets dense.
- **Mono as a first-class typeface, not a garnish.** Anything a user might compare, copy or verify —
  prices, probabilities, bps, addresses, timestamps — is set in mono. Prose stays in sans. It is a
  readability decision for financial screens.
- **Numbers with provenance.** Where the kit shows a value, we show the value *and* how it was
  reached (source, window, caveat block). On a product about market estimates, an unqualified number
  is a bug.
- **Money language kept cold.** No promise of safety, no "insured", no risk scores dressed as truth.
  Soundings states plainly: market estimates, not insurance.

## Build notes

- Static HTML + one shared stylesheet (`assets/ef.css`). No build step, no frameworks, no CDN,
  no external fonts, no remote images — the pages render identically offline.
- Interactive panels (order sizing, depth inputs, row selection) are vanilla JS that only recompute
  displayed figures locally; nothing here touches a network or moves funds.
- Every page was rendered and reviewed in a real browser at desktop and mobile widths during build.
