---
title: Member 3
parent: ICON-ESM-ER
nav_order: 3
---

# ICON-ESM-ER, member 3

**Prefix:** `icon-esm-er.hist-1950.r3i1p1f1` (historical run only)

```python
ds = open_eerie("icon-esm-er.hist-1950.r3i1p1f1.ocean.gr025.2d_monthly_mean")
```

## Monthly means (0.25°)

| Field | Dataset ending |
| --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_monthly_mean` |
| Ocean 2D | `.ocean.gr025.2d_monthly_mean` |
| Ocean 2D, squared fields | `.ocean.gr025.2d_monthly_square` |
| Meridional overturning | `.ocean.gr025.moc_monthly_mean` |

## Daily means (0.25°)

| Field | Dataset ending |
| --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_daily_mean` (also `_max`, `_min`) |
| Ocean 2D | `.ocean.gr025.2d_daily_mean` |
| Ocean 3D (upper 5 levels) | `.ocean.gr025.5lev_daily_mean` |

No regridded 3D monthly or sub-daily data exists for this member. Variable names are the same as for [member 1](member-1).
