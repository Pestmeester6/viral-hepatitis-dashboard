# Viral hepatitis dashboard

Country-level WHO hepatitis explorer with region/country filters, top-15 comparisons, labelled trends, a complete all-year table, source bounds and CSV downloads. Country overviews summarize all available indicators using fixed data-grounded sentences, not a live AI service.

## Update data

Replace a descriptively named CSV in [`data/`](data/) while keeping its name and WHO headers. The dashboard loads these files directly; no rebuild or changes to `index.html` are required. Preserve historical years to retain trends. See the [file list and replacement guide](data/README.md).

## Run

Use GitHub Pages, or serve the repository locally with `python -m http.server 8000` and open `http://localhost:8000`. Opening `index.html` directly as a local file will not load the CSVs.

GitHub Pages setup: Settings → Pages → Deploy from a branch → main → / (root) → Save.

## Interpretation and validation

All years and both reported/modelled values appear in the data table. Population strata remain separate. Comparison bars use each country's latest available value and label its year; these years may differ. Missing observations are explicit. Rates are not summed. Trend series keep data natures separate and show each year/value; two endpoints describe change rather than an annual trend. See [DASHBOARD.md](DASHBOARD.md).

The initial 15 unique source files contain 7,393 observations and 26 indicators. Functional validation covers CSV loading/quoting, observation parity, region-country linkage, summaries, Peru source flags, and both trend endpoints. Full visual browser QA has not been performed.
