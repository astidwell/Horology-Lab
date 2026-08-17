# Measurement Protocol

## Sign convention

- `+` offset: watch is ahead of reference.
- `-` offset: watch is behind reference.

## Recommended seven-day run

Record a baseline and then one reading per day for seven days. Keep the watch running continuously and avoid setting it during the experiment.

For each observation, capture:
- local timestamp
- reference source
- signed offset in seconds
- estimated wrist-wear hours since prior reading
- rest position (dial up, dial down, crown up, crown down, 12 up, 6 up, mixed/unknown)
- manual winding, if any
- notes about unusual use or interruptions

## Interpretation

The lab should eventually report:
- total cumulative drift
- average seconds/day over the full run
- interval seconds/day between observations
- best/worst daily interval
- range and standard deviation of interval rates
- behavior grouped by rest position when enough data exists

Do not confuse COSC/METAS test conditions with wrist performance. This experiment measures the assembled watch in Aaron's actual use, which is exactly why it is interesting.
