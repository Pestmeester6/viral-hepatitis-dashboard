# Data sources and replacement guide

The dashboard reads these CSV files directly at page load. Files retain all original WHO columns and observations; only filenames and line endings have been standardized. An exact duplicate mortality-rate upload was omitted. The initial 15 files contain 7,393 unique observations across 26 indicators.

## Publish updated data

1. Download the new WHO export for the same indicator group.
2. Replace the corresponding CSV in this folder, keeping the filename below exactly unchanged. GitHub: open the file → edit/upload its replacement → commit to `main`.
3. Keep the standard WHO CSV headers and UTF-8 encoding. Do not replace the header with a title or explanatory text. Numeric values must retain decimal points and no thousands separators in `FactValueNumeric`; human-readable formatting belongs in `Value`.
4. Preserve previous years in the replacement file if you want to retain trend charts. A latest-year-only export will remove historical observations for that file. For grouped files, retain all listed indicators, not only HBV or HCV.
5. After committing, wait for GitHub Pages to finish publishing and reload the dashboard. It fetches the manifest and CSVs without browser caching; no HTML rebuild or manual data embedding is needed.

For a new filename, add or edit its `path` entry in [manifest.json](manifest.json). The `description` and `indicators` fields document the file; actual indicator names and values come from the CSV itself. Do not add the same source twice. Update related numerator, denominator and coverage exports together when available. The app refuses missing required columns, invalid numeric values and malformed CSV rows rather than silently showing partial results.

## Stable filenames

| File | Indicator group |
| --- | --- |
| [treatment-coverage-among-diagnosed.csv](treatment-coverage-among-diagnosed.csv) | treatment coverage among diagnosed |
| [mortality-rate.csv](mortality-rate.csv) | mortality rate |
| [hbsag-prevalence-and-carriers-by-age.csv](hbsag-prevalence-and-carriers-by-age.csv) | hbsag prevalence and carriers by age |
| [antenatal-hbv-treatment.csv](antenatal-hbv-treatment.csv) | antenatal hbv treatment |
| [hbv-hcv-population-prevalence.csv](hbv-hcv-population-prevalence.csv) | hbv hcv population prevalence |
| [hbv-hcv-diagnosed-counts.csv](hbv-hcv-diagnosed-counts.csv) | hbv hcv diagnosed counts |
| [diagnosis-coverage.csv](diagnosis-coverage.csv) | diagnosis coverage |
| [hbv-treatment-counts.csv](hbv-treatment-counts.csv) | hbv treatment counts |
| [treatment-coverage-among-infected.csv](treatment-coverage-among-infected.csv) | treatment coverage among infected |
| [antenatal-hbsag-testing.csv](antenatal-hbsag-testing.csv) | antenatal hbsag testing |
| [hbv-hcv-infected-population.csv](hbv-hcv-infected-population.csv) | hbv hcv infected population |
| [mortality-counts.csv](mortality-counts.csv) | mortality counts |
| [new-infections.csv](new-infections.csv) | new infections |
| [antenatal-hbsag-positivity.csv](antenatal-hbsag-positivity.csv) | antenatal hbsag positivity |
| [hcv-treatment-counts.csv](hcv-treatment-counts.csv) | hcv treatment counts |

## Source format

Required columns: `IndicatorCode`, `Indicator`, `ParentLocation`, `SpatialDimValueCode`, `Location`, `Period`, `Dim1 type`, `Dim1`, `Dim2`, `FactValueNumeric`. Keep all original columns, including `Value`, uncertainty bounds, sources, comments and data nature. CSV parsing supports quoted commas, escaped quotation marks and embedded newlines. Blank numeric values remain missing; zero is retained.

Initial provenance: user-supplied WHO indicator exports, including Global Hepatitis Report 2026 and related series. No values have been corrected or replaced with external estimates. Peru's HCV discrepancy is flagged only while the relevant original 2024 counts remain present. Verify those source values before epidemiological interpretation.
