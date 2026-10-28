# Peru HCV review — uploaded files only

User-approved decision, 28 October 2026: use **65,290** for the dashboard's Peru 2024 HCV count. The erroneous **9.92% prevalence is withheld**. No replacement percentage has been calculated.

## Uploaded records

- `hbv-hcv-infected-population.csv`: `HEPATITIS_HCV_LIVINGWITH_NUM`, Peru, 2024, original country-reported value **3,440,210**.
- Same file: `HEPATITIS_HCV_LIVINGWITH_CRD_NUM`, Peru, 2024, modelled value **65,290**, bounds **41,985–67,822**. This definition includes people cured.
- `hbv-hcv-population-prevalence.csv`: original country-reported prevalence **9.92%**.
- `hbv-hcv-diagnosed-counts.csv`: **450** diagnosed including cured; `diagnosis-coverage.csv`: **0.69%**. Calculation: 450 / 65,290 × 100 = 0.6892%.
- `hcv-treatment-counts.csv`: **177** cumulatively treated; `treatment-coverage-among-infected.csv`: **0.27%**. Calculation: 177 / 65,290 × 100 = 0.2711%.

These checks support internal consistency of the 65,290 denominator. They do not establish an active-infection count independently of the including-cured definition. The original prevalence/count pair is internally conflicting with that adopted series; the files do not establish an exact corrected prevalence.

## Implementation

The source CSVs remain unchanged. `data-quality.json` applies an exact-match correction only while the original count and approved reference record are present. The displayed count uses 65,290 and the reference record's modelled nature, bounds and source. A visible annotation identifies it as an adopted estimate including cured people. It is never added to the separate including-cured indicator.

The raw count, value and data nature are preserved in `OriginalFactValueNumeric`, `OriginalValue` and `OriginalDataNature`; `ReferenceIndicatorCode` records the donor series. CSV exports include these fields plus quality status and explanation. The erroneous prevalence remains excluded. If source files change, the exact-match rules must be reviewed; no arbitrary decimal adjustment or external estimate is used.
