---
title: Member 1
parent: IFS-FESOM2-SR
nav_order: 1
---

# IFS-FESOM2-SR, member 1

Every dataset id is the prefix below followed by the ending in the tables.

**Prefix:** `ifs-fesom2-sr.<exp>.v20240304`, with `<exp>` = `hist-1950`, `highres-future-ssp245` or `eerie-control-1950`

```python
ds = open_eerie("ifs-fesom2-sr.hist-1950.v20240304.ocean.gr025.3D_monthly_avg")
```

## Monthly means (0.25°)

| Field | Dataset ending | Example variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_monthly_avg` | `msshf`, `metss`, `mtcw` |
| Atmosphere 3D (pressure levels) | `.atmos.gr025.3D_monthly_avg` | `mt`, `mu`, `mv`, `mw`, `mz`, `mq` |
| Ocean 2D | `.ocean.gr025.2D_monthly_avg` | `avg_tos`, `avg_sos`, `avg_zos`, `avg_siconc`, `avg_mlotst125` |
| Ocean 3D (depth levels) | `.ocean.gr025.3D_monthly_avg` | `avg_thetao`, `avg_so`, `avg_uoe`, `avg_von`, `avg_wo` |
| AMOC streamfunction | `.ocean.gr025.AMOC` | |

Also available: monthly maxima and minima of 2D atmosphere fields (`2D_monthly_max`, `2D_monthly_min`), and for `hist-1950` the mixed-layer depth with a 0.03 kg/m³ criterion (`.ocean.gr025.2D_monthly_avg_mlotst030`).

## Daily means (0.25°)

| Field | Dataset ending | Example variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_daily_avg` (also `_max`, `_min`) | `mmsl`, `mblh`, `metss` |
| Atmosphere 3D (pressure levels) | `.atmos.gr025.3D_daily_avg` | |
| Ocean 2D | see below | `avg_tos`, `avg_sos`, `avg_siconc`, `avg_mlotst030` |
| Ocean 3D (depth levels) | `.ocean.gr025.3D_daily_avg` | |

Daily ocean 2D endings depend on the experiment:

| Experiment | Dataset ending |
| --- | --- |
| hist-1950 | `.ocean.gr025.2D_daily_avg_1950-2014` (or the shorter `_2000-2014`) |
| highres-future-ssp245 | `.ocean.gr025.2D_daily_avg` |
| eerie-control-1950 | `.ocean.gr025.2D_daily_avg_1950-2050` (or `_1984-2050`, `_2000-2050`) |

## 6-hourly (0.25°)

| Field | Dataset ending | Example variables |
| --- | --- | --- |
| Atmosphere 2D, instantaneous | `.atmos.gr025.2D_6hourly_instant` | `skt`, `sst`, `tcwv`, `10si` |
| Atmosphere 2D, accumulated | `.atmos.gr025.2D_6hourly_accumulated` | |
| Atmosphere 3D (pressure levels) | `.atmos.gr025.3D_6hourly` | `t`, `u`, `v`, `w`, `z`, `q` |
