# Horology Lab

A practical timing lab for Aaron's mechanical watches.

## Purpose

Track real-world mechanical watch drift over multi-day runs and distinguish:
- cumulative offset from reference time
- average daily rate
- wrist-worn behavior vs resting-position behavior
- consistency (precision) from simple headline accuracy

## Current collection

See [`data/watches.csv`](data/watches.csv).

## Active experiment

**Tudor Black Bay Ceramic (BBC), reference 79210CNU**

- Baseline: 2026-08-24, 10:10 PM CDT; offset 0 seconds against time.gov.
- Planned duration: 7-14 days, using the same wrist-worn routine as Viola.
- [Measurement CSV](data/measurements/tudor-black-bay-ceramic.csv)
- [Factory METAS results](data/certificates/tudor-black-bay-ceramic-metas.md)

Latest reading: **+7 seconds cumulative** on Day 3 (2026-08-27). Sequence: 0, +2, +4, +7 seconds. At the assumed daily 10:10 PM schedule, interval rates are +2, +2, +3 s/day and the overall rate is **+2.33 s/day**. The last two timestamps use the usual schedule and were not separately confirmed; see row notes. Rates are provisional on that basis.

The observed average is 1.78 s/day lower than the factory +4.11 s/day result. Conditions differ, and three days are too few to establish long-term stability.

## Completed experiment

**Formex Essence Ceramica Skeleton COSC - Stradale Viola, 41 mm**

- [Measurements](data/measurements/formex-essence-ceramica-skeleton-viola.csv)
- [Factory COSC data](data/certificates/formex-essence-ceramica-skeleton-viola-cosc.md)

Completed 2026-08-23: -28 seconds over seven days, averaging -4.00 s/day.

## Measurement protocol

1. Use one stable reference clock for the entire run (phone/network time or another trusted synchronized source).
2. At the baseline observation, record the watch's offset in seconds. If the watch is freshly synchronized, record `0`.
3. Measure at roughly the same time each day for seven days. Exact 24-hour spacing is not required because rate is calculated from elapsed time.
4. Do **not** reset the watch during a run unless intentionally ending the experiment.
5. Record meaningful context: approximate wear hours, overnight/rest position, whether it stopped, winding/resetting, and unusual conditions.
6. Keep signed offsets consistent: positive = watch ahead of reference; negative = watch behind.

## Rate math

For observations `i-1` and `i`:

`interval_rate_spd = (offset_i - offset_(i-1)) / elapsed_days`

Across the full experiment:

`average_rate_spd = (last_offset - baseline_offset) / total_elapsed_days`

This avoids pretending every reading happened exactly 24 hours apart.

## Why this matters

A mechanical watch can be accurate by luck while being imprecise, or consistently fast/slow while being very precise. The useful question is not only “how many seconds did it gain?” but also “does it behave predictably across wear and rest conditions?”
