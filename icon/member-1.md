---
title: Member 1
parent: ICON-ESM-ER
nav_order: 1
---

# ICON-ESM-ER, member 1

Every dataset id is the prefix below followed by the ending in the tables. Where the ending differs between experiments, both are given.

**Prefix:** `icon-esm-er.<exp>.v20240618`, with `<exp>` = `hist-1950`, `highres-future-ssp245` or `eerie-control-1950`

```python
ds = open_eerie("icon-esm-er.hist-1950.v20240618.ocean.gr025.ml_monthly_mean")
```

## Monthly means (0.25°)

| Field | hist-1950 | highres-future-ssp245 | Example variables |
| --- | --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_monthly_mean` | same | `pr`, `clt`, `hfls`, `hfss`, `evspsbl` |
| Atmosphere 3D (19 pressure levels) | `.atmos.gr025.plev19_monthly_mean` | `.atmos.gr025.plev19_1mth_mean` | `ta`, `ua`, `va`, `wa`, `hus` |
| Ocean 2D | `.ocean.gr025.2d_monthly_mean` | same | `to` (SST), surface heat and freshwater fluxes |
| Ocean 3D (model levels) | `.ocean.gr025.ml_monthly_mean` | `.ocean.gr025.model-level_monthly_mean` | `to`, `so`, `u`, `v` |

Also available: ocean vertical velocity (`ml_monthly_w_mean` in hist-1950, `model-level_monthly_mean_vertical` in highres-future-ssp245) and, for hist-1950, eddy terms (`.ocean.gr025.eddy_monthly_mean`).

## Daily means (0.25°)

| Field | hist-1950 | highres-future-ssp245 |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_daily_mean` (also `_max`, `_min`) | same |
| Atmosphere 3D (19 pressure levels) | `.atmos.gr025.plev19_daily_mean` | `.atmos.gr025.plev19_1d_mean` |
| Ocean 2D | `.ocean.gr025.2d_daily_mean` | same |
| Ocean 3D (upper 5 levels) | `.ocean.gr025.5lev_daily_mean` | same |

## 6-hourly and hourly (0.25°)

| Field | hist-1950 | highres-future-ssp245 |
| --- | --- | --- |
| Atmosphere 2D, 6-hourly mean | `.atmos.gr025.2d_6hourly_mean` | `.atmos.gr025.2d_6hr_mean` |
| Atmosphere 2D, 6-hourly instantaneous | `.atmos.gr025.2d_6hourly_inst` | `.atmos.gr025.2d_6hr_inst` |
| Atmosphere 3D, 6-hourly instantaneous | `.atmos.gr025.pl_6hourly_inst` | `.atmos.gr025.pl_6hr_inst` |
| Atmosphere 2D, hourly | `.atmos.gr025.2d_hourly_mean`, `.atmos.gr025.2d_hourly_inst` | Not available |

For `eerie-control-1950`, list the available endings with the snippet in [Getting started](../getting-started).
