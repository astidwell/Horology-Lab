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

## GitHub logging workflow

Owner-approved standing instruction (2026-08-27): treat future watch drift reports as instructions to update this repository, not merely acknowledge them in chat.

1. Read the current repository state and identify the active watch/run before editing.
2. Treat reported signed offsets as cumulative unless the owner explicitly says otherwise.
3. Resolve ambiguous signs or conflicting readings before saving. Keep corrections auditable in the notes; do not treat a corrected typo as an actual observation.
4. Preserve the CSV schema. Leave unreported wear hours and manual winding blank rather than fabricating zeros. Distinguish stated wear routine from independently confirmed daily behavior.
5. Use the known local date and time zone. If the normal measurement time is assumed, identify that assumption in the row notes and qualify rates accordingly; ask when timing is materially uncertain.
6. Preserve unrelated records and commit the measurement plus any necessary active-experiment summary update.
7. Verify the remote commit and saved values. Only say "logged" or "updated GitHub" after the write succeeds; otherwise state that the reading remains pending.
8. Do not publish serial numbers or other unnecessary identifying details from certificates by default.
