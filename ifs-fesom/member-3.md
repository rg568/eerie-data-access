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

**Coverage:** hist-1950 1975-2014; highres-future-ssp245 2015-2030 (atmosphere only). This member starts in 1975, not 1950.

Atmosphere fields need reshaping to lat-lon; see [the IFS-FESOM page](./). Descriptions and units of all variables are on the [Variables](variables) page.

## Monthly means (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_monthly_avg` | Same 43 fields as member 1 ([full list](variables#atmosphere-2d-means)) |
| Atmosphere 2D, maxima | `.atmos.gr025.2D_monthly_max` | `mx2t`, `10fg` |
| Atmosphere 2D, minima | `.atmos.gr025.2D_monthly_min` | `mn2t` |
| Atmosphere 3D (19 pressure levels, 1-1000 hPa) | `.atmos.gr025.3D_monthly_avg` | `mt`, `mu`, `mv`, `mw`, `mz`, `mq`, `mr` |
| Ocean 2D | Not provided as monthly | Average the daily data with `ds.resample(time="1MS").mean()` |
| Ocean 3D | Not available for this member | |

## Daily means (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_daily_avg` | Same 43 fields as monthly |
| Atmosphere 2D, maxima | `.atmos.gr025.2D_daily_max` | `mx2t24`, `10fg` |
| Atmosphere 2D, minima | `.atmos.gr025.2D_daily_min` | `mn2t24` |
| Atmosphere 3D (19 pressure levels, 1-1000 hPa) | `.atmos.gr025.3D_daily_avg` | `mt`, `mu`, `mv`, `mw`, `mz`, `mq`, `mr` |
| Ocean 2D | `.ocean.gr025.2D_daily_avg` | `avg_tos`, `avg_sos`, `avg_zos`, `avg_mlotst030`, `avg_mlotst125`, `avg_siconc`, `avg_sithick`, `avg_sisnthick`, `avg_sigrowth`, `avg_siue`, `avg_sivn` (hist-1950 1975-2014 only; not available for highres-future-ssp245) |

## 6-hourly (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D, instantaneous | `.atmos.gr025.2D_6hourly_instant` | Same 22 fields as member 1 ([full list](variables#atmosphere-2d-6-hourly-instantaneous)) |
| Atmosphere 2D, accumulated | `.atmos.gr025.2D_6hourly_accumulated` | Same 22 fields as member 1 ([full list](variables#atmosphere-2d-6-hourly-accumulated)) |
| Atmosphere 3D (19 pressure levels, 1-1000 hPa) | `.atmos.gr025.3D_6hourly` | `t`, `u`, `v`, `w`, `z`, `q`, `r` |

Monthly ocean 2D files for the historical run also exist on Levante; see [On Levante](../levante).
