---
title: Member 2
parent: ICON-ESM-ER
nav_order: 2
---

# ICON-ESM-ER, member 2

**Prefix:** `icon-esm-er.hist-1950.r2i1p1f1` (historical run only)

```python
ds = open_eerie("icon-esm-er.hist-1950.r2i1p1f1.ocean.gr025.2d_monthly_mean")
```

**Coverage:** 1975-2014. The monthly series contain 479 of 480 months (atmosphere) and 474 of 480 (ocean), so check `ds.time` for gaps. Variables are the same as in [member 1](member-1); descriptions are on the [Variables](variables) page.

## Monthly means (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_monthly_mean` | Same 33 fields as member 1 |
| Ocean 2D | `.ocean.gr025.2d_monthly_mean` | Same 39 fields as member 1 |
| Ocean 2D, squared fields | `.ocean.gr025.2d_monthly_square` | `to`, `ssh`, `mlotst`, `mlotst10` |

## Daily means (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_daily_mean` | Same 21 fields as member 1 |
| Atmosphere 2D, minima | `.atmos.gr025.2d_daily_min` | `tas`, `hur` |
| Ocean 2D | `.ocean.gr025.2d_daily_mean` | Same 34 fields as member 1 |
| Ocean 2D, squared SST | `.ocean.gr025.2d_daily_square` | `to` |
| Ocean 3D (6 levels, 1-1452 m) | `.ocean.gr025.5lev_daily_mean` | `to`, `so`, `u`, `v`; 1975-2001 only, with gaps (8368 days) |

No regridded 3D monthly, pressure-level or sub-daily data exists for this member.
