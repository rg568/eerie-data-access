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

## Monthly means (0.25°)

| Field | Dataset ending |
| --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_monthly_mean` |
| Ocean 2D | `.ocean.gr025.2d_monthly_mean` |
| Ocean 2D, squared fields | `.ocean.gr025.2d_monthly_square` |

## Daily means (0.25°)

| Field | Dataset ending |
| --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_daily_mean` (also `_min`) |
| Ocean 2D | `.ocean.gr025.2d_daily_mean` |
| Ocean 3D (upper 5 levels) | `.ocean.gr025.5lev_daily_mean` |

No regridded 3D monthly or sub-daily data exists for this member. Variable names are the same as for [member 1](member-1).
