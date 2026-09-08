# Cato open datasets

Open data on parking enforcement and appeals, published by [CatoAppeals](https://www.catoappeals.com)
and mirrored here so it can be cloned, cited and forked. Every file is a republication of figures
a public body published itself, re-derived from the source workbooks and checked row by row.
No figure is derived, modelled or estimated.

Catalogue, methodology and source notes: **https://www.catoappeals.com/data**

| File | What it is | Source | Rows |
| --- | --- | --- | --- |
| `london-parking-appeal-outcomes-2024-25.csv` | Parking PCNs issued, appeals received and decided, share allowed and share not contested, for all 33 London boroughs | London Tribunals, Environment and Traffic Adjudicators annual statistics | 33 |
| `parking-appeal-index-2024-25.csv` | Coverage map: every civil enforcement authority in England and Wales; the 336 outside London read "not published" because the Traffic Penalty Tribunal publishes no per-authority figures | London Tribunals; Traffic Penalty Tribunal | 369 |
| `parking-finance-england-2024-25.csv` | What each English council took in parking charges and penalties and spent enforcing them | MHCLG revenue outturn (RO2) 2024-25 | 347 |
| `pcn-contravention-codes.csv` | Every PCN contravention code on the national list, official wording, plain-English meaning, family, level, camera-enforceability | London Councils PCN contravention code list v7.0, effective 31 May 2022 | 84 |
| `nederland-parkeerfeitcodes-2025-2026.csv` | Dutch parking feitcodes with legal basis, 2026 tariff, 2025 case counts and average amount | CJIB "Instroom feitgecodeerde zaken 2025"; Wahv bijlage on wetten.overheid.nl, in force 01-01-2026 | 52 |
| `australia-parking-fines.csv` | Parking offences for **six** jurisdictions (NSW, ACT, VIC, TAS, QLD, SA) with legislation, section, offence code and amount. WA and the NT publish no machine-readable catalogue and are omitted rather than estimated. | Each state's own schedule or penalty-notice dataset, named per row | 700 |

Each row carries a link to the CatoAppeals page that explains it: `page` in every file
except the Dutch feitcodes, where the column is named `pagina`.

## Reading the data

**Two kinds of absence, and they mean different things.**

- **`not published`** — the source body publishes no figure. This is a fact about the
  source, not a gap in this dataset, and it is never a zero. In
  `parking-appeal-index-2024-25.csv` all 336 authorities outside London read
  `not published` in every statistical column, because the Traffic Penalty Tribunal
  publishes national totals only. A real zero is written `0`, and both appear in
  `parking-finance-england-2024-25.csv` — treat them as distinct.
- **An empty cell** — the column does not apply to that row. In
  `australia-parking-fines.csv`, `penalty_units` and `amount_basis` are empty for
  NSW, the ACT and South Australia because those jurisdictions legislate parking
  fines as fixed dollar amounts rather than as multiples of a penalty unit.
  `amount_aud` is populated for all 700 rows.

**Coverage you should know about before analysing:**

| Column | Populated | Note |
| --- | --- | --- |
| `parking-appeal-index` statistical columns | 33 / 369 | Only London publishes per-authority outcomes |
| `parking-finance` on-street | 226 / 347 | |
| `parking-finance` penalty charge income | 183 / 347 | |
| `parking-finance` bus lane | 65 / 347 | Most authorities outside London have no bus lane enforcement powers |

Four rows in `parking-finance-england-2024-25.csv` have no ONS code because they are
joint arrangements rather than single authorities: the North and South Essex Parking
Partnerships, North Gloucestershire, and King's Lynn and West Norfolk acting under
authority delegated by Norfolk County Council.

**Provenance.** `parking-appeal-index`, `london-parking-appeal-outcomes`,
`parking-finance-england` and `australia-parking-fines` carry a per-row `source`
column. `pcn-contravention-codes` and `nederland-parkeerfeitcodes` do not — each is a
single-source file, and its source is the one named in the table above.

## Licence

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
Reproduce in whole or in part, commercially included, with attribution:

> CatoAppeals, *[dataset title]*, https://www.catoappeals.com/data

## Regenerating

These CSVs are generated in the CatoAppeals repository and copied here unchanged.
Do not edit them by hand; open an issue instead.

| File | Generator |
| --- | --- |
| `parking-appeal-index-2024-25.csv`, `london-parking-appeal-outcomes-2024-25.csv` | `npm run build:appeal-index-csv` |
| `parking-finance-england-2024-25.csv` | `npm run build:parking-finance-csv` |
| `pcn-contravention-codes.csv` | `npm run build:code-csv` |
| `australia-parking-fines.csv` | `npm run build:au-fines-csv` |
| `nederland-parkeerfeitcodes-2025-2026.csv` | `npm run build:nl-feitcodes-csv` |
