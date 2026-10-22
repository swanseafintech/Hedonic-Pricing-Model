# Hedonic Pricing Model

Residential valuation of the 550 & 255 Hammersmith Road, London scheme using a hedonic (attribute-based) pricing model.

## Contents

| Path | Description |
| --- | --- |
| [`docs/hedonic-pricing-model.docx`](docs/hedonic-pricing-model.docx) | Report: what a hedonic pricing model is, an audit of the original valuation workbook, the revised model, value conclusions and sensitivity analysis. |
| [`models/hammersmith-road-model.xlsx`](models/hammersmith-road-model.xlsx) | Workbook pricing all 137 units with live Excel formulas driven by a single parameter block. |

## Workbook structure

- **Methodology** – evidence-based parameters (base prices, floor premium, ground-floor multiplier, balcony rate, aspect premiums, location multiplier), exposed as named ranges.
- **Unit Pricing** – per-unit schedule (floor, type, GIA, balcony, aspect) with computed price, £/psf and variance against the v1.0 flat pricing.
- **Summary** – unit counts and GDV totals.
- **Sensitivity** – impact of changes to the key assumptions (location haircut, floor premium, balcony area).

## Pricing formula

```
Price = Base × FloorFactor × AspectFactor + BalconySqm × BalRate   (then × LocMult at summary level)
```

- 1-bed: `FloorFactor = 1 + FloorPrem × floor`
- 2-bed: `FloorFactor = GroundMult` on Floor 1, otherwise `1 + FloorPrem × (floor − 1)`

To change an assumption, edit the value on the **Methodology** sheet; every unit and summary figure recalculates.
