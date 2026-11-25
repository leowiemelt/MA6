# Bikeshare demand dataset

Daily Capital Bikeshare counts, 2011-2012. We forecast `cnt` (total daily
rides) from calendar, weather, and lagged-demand features.

## Non-negotiable rules
- **Never** put `casual` or `registered` in a feature set:
  `casual + registered == cnt` exactly. `src/config.py` lists these and
  the other excluded columns with the reason for each.
- **Never** split this data randomly. Use `src.train.temporal_split`.
  Train = 2011, valid = H1 2012, test = H2 2012. Never tune on test.
- Report the mean baseline and the persistence baseline (yesterday's
  count) alongside every model score.