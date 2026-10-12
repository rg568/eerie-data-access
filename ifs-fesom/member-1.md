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

**Coverage:** hist-1950 1950-2014; highres-future-ssp245 2015-2070 (atmosphere) and 2015-2050 (ocean); eerie-control-1950 1950-2050. 6-hourly atmosphere starts in 1970 (hist-1950) and 1971 (eerie-control-1950).

Atmosphere fields need reshaping to lat-lon; see [the IFS-FESOM page](./). Descriptions and units of all variables are on the [Variables](variables) page.

## Monthly means (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_monthly_avg` | 43 surface and top-of-atmosphere fields, e.g. `mean2t`, `msst`, `tprate`, `mmsl`, `msshf`, `mslhf`, `metss`, `mntss`, `mtnlwrf` ([full list](variables#atmosphere-2d-means)) |
| Atmosphere 2D, maxima | `.atmos.gr025.2D_monthly_max` | `mx2t`, `10fg` |
| Atmosphere 2D, minima | `.atmos.gr025.2D_monthly_min` | `mn2t` |
| Atmosphere 3D (19 pressure levels, 1-1000 hPa) | `.atmos.gr025.3D_monthly_avg` | `mt`, `mu`, `mv`, `mw`, `mz`, `mq`, `mr` |
| Ocean 2D | `.ocean.gr025.2D_monthly_avg` | `avg_tos`, `avg_sos`, `avg_zos`, `avg_mlotst125`, `avg_siconc`, `avg_sithick`, `avg_sisnthick`, `avg_siue`, `avg_sivn`; ssp245 and control also `avg_mlotst030`, `avg_sigrowth` |
| Ocean 2D, hist-1950 extra | `.ocean.gr025.2D_monthly_avg_mlotst030` | `avg_mlotst030` (1974-2014) |
| Ocean 3D (69 depth levels, 2.5-6175 m) | `.ocean.gr025.3D_monthly_avg` | `avg_thetao`, `avg_so`, `avg_uoe`, `avg_von`, `avg_wo` |
| AMOC streamfunction | `.ocean.gr025.AMOC` | `atlantic_moc` (Sv, depth x latitude; control covers 1950-2014) |

## Daily means (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2D_daily_avg` | Same 43 fields as monthly ([full list](variables#atmosphere-2d-means)) |
| Atmosphere 2D, maxima | `.atmos.gr025.2D_daily_max` | `mx2t24`, `10fg` |
| Atmosphere 2D, minima | `.atmos.gr025.2D_daily_min` | `mn2t24` |
| Atmosphere 3D (19 pressure levels, 1-1000 hPa) | `.atmos.gr025.3D_daily_avg` | `mt`, `mu`, `mv`, `mw`, `mz`, `mq`, `mr` |
| Ocean 3D (7 levels: 2.5, 12.5, 97.5, 195, 600, 950, 1415 m) | `.ocean.gr025.3D_daily_avg` | `avg_thetao`, `avg_so`, `avg_uoe`, `avg_von`, `avg_wo` (ssp245: `avg_wo` is in `.ocean.gr025.3D_daily_avg_w`) |

Daily ocean 2D is split differently in each experiment:

| Experiment | Dataset ending | Variables |
| --- | --- | --- |
| hist-1950 | `.ocean.gr025.2D_daily_avg_1950-2014` | `avg_tos`, `avg_sos`, `avg_zos`, `avg_mlotst125`, `avg_siconc`, `avg_sithick`, `avg_sisnthick`, `avg_siue`, `avg_sivn` |
| | `.ocean.gr025.2D_daily_avg_2000-2014` | `avg_mlotst030`, `avg_sigrowth` |
| highres-future-ssp245 | `.ocean.gr025.2D_daily_avg` | All 11 ocean 2D variables |
| eerie-control-1950 | `.ocean.gr025.2D_daily_avg_1950-2050` | Same 9 as hist-1950 |
| | `.ocean.gr025.2D_daily_avg_1984-2050` | `avg_mlotst030` |
| | `.ocean.gr025.2D_daily_avg_2000-2050` | `avg_sigrowth` |

## 6-hourly (0.25°)

| Field | Dataset ending | Variables |
| --- | --- | --- |
| Atmosphere 2D, instantaneous | `.atmos.gr025.2D_6hourly_instant` | 22 fields: `2t`, `2d`, `2sh`, `10u`, `10v`, `10si`, `i10fg`, `msl`, `sp`, `skt`, `sst`, `ci`, `blh`, `sd`, `tcc`, `lcc`, `mcc`, `hcc`, `tcw`, `tcwv`, `tclw`, `tciw` |
| Atmosphere 2D, accumulated | `.atmos.gr025.2D_6hourly_accumulated` | 22 fields: `tp`, `cp`, `sf`, `e`, `ro`, `sro`, `ssro`, `sshf`, `slhf`, `ssr`, `ssrd`, `ssrc`, `str`, `strd`, `strc`, `tsr`, `tsrc`, `ttr`, `ttrc`, `tisr`, `ewss`, `nsss` |
| Atmosphere 3D (19 pressure levels, 1-1000 hPa) | `.atmos.gr025.3D_6hourly` | `t`, `u`, `v`, `w`, `z`, `q`, `r` (instantaneous) |

Accumulated fields are totals over each 6-hour step (m for water, J m⁻² for energy); divide by 21600 s to get rates.
