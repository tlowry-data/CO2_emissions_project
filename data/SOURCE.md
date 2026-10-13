# Data Source

**Original dataset:** OWID CO2 and Greenhouse Gas Emissions data
https://github.com/owid/co2-data (`owid-co2-data.csv`)
**License:** CC BY 4.0 — Our World in Data. Attribution: Our World in Data,
based on the Global Carbon Project and other sources (see the OWID repo's own
`README.md` for full source-by-source attribution).
**Fetched:** 2026-08-04, from `https://raw.githubusercontent.com/owid/co2-data/master/owid-co2-data.csv`.

## How `co2_emissions_2022.csv` was derived

The full file is ~50,000 rows (every country/region × every year back to 1750)
and 79 columns — too wide for a first-week "small dataset" exercise. This
snapshot keeps it small and honest, not simplified in a way that hides real
data-quality issues:

- **Filtered to `year == 2022`** — the most recent year with broad
  `co2`/`population`/`gdp` coverage (2023-2024 rows exist but `gdp` is
  entirely absent for them in the source file).
- **Kept 6 columns**: `country`, `iso_code`, `year`, `population`, `gdp`,
  `co2`. No rows dropped beyond the year filter — all 254 entities the source
  reports for 2022 are here, including the aggregate/region rows (see below).
- No values were invented, imputed, or corrected — missing values are exactly
  as blank in the source.
