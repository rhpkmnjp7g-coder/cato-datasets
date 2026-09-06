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

Each row carries a `page` column linking the CatoAppeals page that explains it.

## Licence

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
Reproduce in whole or in part, commercially included, with attribution:

> CatoAppeals, *[dataset title]*, https://www.catoappeals.com/data

## Regenerating

These CSVs are generated in the CatoAppeals repository (`npm run build:appeal-index-csv` and
siblings) and copied here unchanged. Do not edit them by hand; open an issue instead.
