# paycheck-tax-data

Over-the-air tax data for the Paycheck Calculator iOS app.

The app ships with a bundled copy of this file and checks
`https://kirillmageria.github.io/paycheck-tax-data/tax-data.json`
once a day. A downloaded file is applied only if its `version` is newer
than the current one and it passes parsing and semantic validation.

Format notes:

- All monetary and rate values are **strings**, never JSON numbers —
  they are parsed as `Decimal` and must not round-trip through `Double`.
- `version` is `"<year>.<revision>"` (e.g. `2026.2`); bump the revision
  on every data correction within a year.
