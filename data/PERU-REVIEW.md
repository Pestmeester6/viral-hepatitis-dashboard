# Peru HCV source review — 28 October 2026

## Finding

The uploaded country-reported 2024 records contain 3,440,210 people living with chronic HCV and 9.92% general-population prevalence. These values are present in the original CSVs; they were not caused by dashboard number formatting or aggregation. They should not be accepted as reliable national estimates.

MINSA's [16 July 2024 publication](https://www.gob.pe/institucion/minsa/noticias/989700-minsa-realizo-campanas-gratuitas-para-promover-el-diagnostico-oportuno-contra-las-hepatitis-b-y-c) reports an estimated **34,111 people with hepatitis C**. Its [2025 resource-planning document](https://cdn.www.gob.pe/uploads/document/file/6100430/5396086-6-criterios-de-programacion-2025-dpvih-1-27.pdf?v=1711152283), published in 2024, separately cites a national estimate of **33,035 people with chronic HCV** and **0.1%** general-population prevalence. These support a burden in the tens of thousands, not millions. These publications do not establish a replacement value with the same WHO indicator definition and reference period.

The separate uploaded WHO-modelled series is **65,290 including people cured**, bounds **41,985–67,822**, in 2024. It is not interchangeable with current active HCV infections. No decimal-point or unit correction has been inferred.

## Dashboard treatment

- Original CSV values remain unchanged for audit.
- `data-quality.json` excludes only the two exact country/indicator/year/value matches from charts, rankings, medians, focus cards and the country narrative.
- The full table marks the disputed observations as excluded. Expand the country's source observations or open the CSVs to inspect the original values.
- Filtered CSV exports retain the source numeric values and add `DataQualityStatus`, `DataQualityReason` and `DataQualityReference` columns. Do not include excluded rows in analysis.
- Other Peru indicators, including the distinct modelled including-cured series, remain available under their own definitions.

## Future data updates

Replace the source CSVs normally. The exclusions match exact original values; changed values do not inherit these flags automatically. Review new source values and revise `data-quality.json` as needed. An unflagged value means only that no current exclusion rule matched; it is not a certification of validity.
