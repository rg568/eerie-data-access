---
title: Member 3
parent: IFS-FESOM2-SR
nav_order: 3
---

# IFS-FESOM2-SR, member 3

Every dataset id is the prefix below followed by the ending in the tables.

**Prefix:** `ifs-fesom2-sr.<exp>.r3i1p1f1`, with `<exp>` = `hist-1950` or `highres-future-ssp245`

```python
ds = open_eerie("ifs-fesom2-sr.hist-1950.r3i1p1f1.atmos.gr025.2D_monthly_avg")
```

## Monthly means (0.25°)

| Field | Dataset ending |
| --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_monthly_avg` (also `_max`, `_min`) |
| Atmosphere 3D (pressure levels) | `.atmos.gr025.3D_monthly_avg` |
| Ocean 2D | Not provided as monthly; average the daily data (below) with `ds.resample(time="1MS").mean()` |
| Ocean 3D | Not available for this member |

## Daily means (0.25°)

| Field | Dataset ending |
| --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_daily_avg` (also `_max`, `_min`) |
| Atmosphere 3D (pressure levels) | `.atmos.gr025.3D_daily_avg` |
| Ocean 2D | `.ocean.gr025.2D_daily_avg` |

## 6-hourly (0.25°)

| Field | Dataset ending |
| --- | --- |
| Atmosphere 2D, instantaneous | `.atmos.gr025.2D_6hourly_instant` |
| Atmosphere 2D, accumulated | `.atmos.gr025.2D_6hourly_accumulated` |
| Atmosphere 3D (pressure levels) | `.atmos.gr025.3D_6hourly` |

Variable names are the same as for [member 1](member-1).

Monthly ocean 2D files for the historical run also exist on Levante; see [On Levante](../levante).

**Note:** for `highres-future-ssp245`, daily ocean output of member 3 is not yet on the cloud. If you need it, open an [issue](https://github.com/rg568/eerie-data-access/issues).
