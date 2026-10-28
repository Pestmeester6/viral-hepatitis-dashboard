# Dashboard

Open `index.html` in a current browser. It is self-contained with no external dependencies or data requests.

## GitHub Pages

To publish: Settings → Pages → Deploy from a branch → main → / (root) → Save. GitHub will show the deployed URL. Pages deployment has not been verified.

## Contents and interpretation

16 uploaded WHO CSV exports; 7,574 input records; 181 exact duplicates removed; 7,393 unique observations; 26 indicators. Includes country rankings, trends, searchable/sortable tables, uncertainty bounds and filtered CSV export.

Country-reported and modelled estimates, age groups and population strata are selected separately. Missing values remain missing; zero remains zero. Medians are unweighted country medians, not regional or global estimates. No rates or counts are summed across countries. Multi-year periods remain selectable but are excluded from single-year trend charts. Lines connect observed years without imputation. Bounds are displayed without assuming a confidence level. Source indicator wording and numeric inequality prefixes are preserved.

Data include Global Hepatitis Report 2026 and related series, with some observations through 2025. These are national hepatitis data, not municipal or SINASC records.

Validation passed: decompression round trip, observation-key uniqueness, JavaScript syntax, initial rendering, country search, indicator and stratum controls. Full visual browser QA was not performed.
