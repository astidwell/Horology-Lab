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

**Formex Essence Ceramica Skeleton COSC — Stradale Viola, 41 mm**

Data file: [`data/measurements/formex-essence-ceramica-skeleton-viola.csv`](data/measurements/formex-essence-ceramica-skeleton-viola.csv)

Factory COSC data: [`data/certificates/formex-essence-ceramica-skeleton-viola-cosc.md`](data/certificates/formex-essence-ceramica-skeleton-viola-cosc.md)

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
