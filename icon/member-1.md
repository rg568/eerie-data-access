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

**Coverage:** hist-1950 1950-2014; highres-future-ssp245 2015-2050; eerie-control-1950 1950-2050. Descriptions and units are on the [Variables](variables) page.

## Monthly means (0.25°)

| Field | hist-1950 | highres-future-ssp245 | Variables |
| --- | --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_monthly_mean` | same | 33 fields: `tas`, `tasmax`, `tasmin`, `ts`, `ps`, `psl`, `uas`, `vas`, `sfcwind`, `tauu`, `tauv`, `pr`, `evspsbl`, `prw`, `clt`, `clivi`, `cllvi`, `hur`, `hus2m`, `hfls`, `hfss`, `rlds`, `rldscs`, `rlus`, `rlut`, `rlutcs`, `rsds`, `rsdscs`, `rsdt`, `rsus`, `rsuscs`, `rsut`, `rsutcs` |
| Atmosphere 3D (19 pressure levels) | `.atmos.gr025.plev19_monthly_mean` | `.atmos.gr025.plev19_1mth_mean` | `ta`, `ua`, `va`, `wa`, `hus`, `hur`, `gpsm`, `cli`, `clw` |
| Ocean 2D | `.ocean.gr025.2d_monthly_mean` | same | 39 fields: `to` and `so` (top level), `ssh`, `mlotst`, `mlotst10`, sea ice (`conc`, `hi`, `hs`, `ice_u`, `ice_v`, `newice`, ...), surface heat and freshwater fluxes ([full list](variables#ocean-and-sea-ice)) |
| Ocean 2D, squared fields | `.ocean.gr025.2d_monthly_square` | same | `to`, `ssh`, `mlotst`, `mlotst10` |
| Ocean 3D (72 levels) | `.ocean.gr025.ml_monthly_mean` | `.ocean.gr025.model-level_monthly_mean` | `to`, `so`, `u`, `v`, `rsdoabsorb` |
| Ocean 3D vertical velocity | `.ocean.gr025.ml_monthly_w_mean` | `.ocean.gr025.model-level_monthly_mean_vertical` | `w` |
| Vertically integrated mass flux | `.ocean.gr025.2d_monthly_mean_vertical` | same | `verticallyTotal_mass_flux_e` |
| Eddy flux terms (72 levels, 1950-1970) | `.ocean.gr025.eddy_monthly_mean` | Not available | `uT`, `vT`, `wT`, `uS`, `vS`, `uu`, `vv`, `uv`, `sigma0`, ... |

For eerie-control-1950, the endings are as for hist-1950 except ocean 3D: `.ocean.gr025.ml_1mth_mean` and `.ocean.gr025.ml_1mth_mean_w`.

## Daily means (0.25°)

| Field | hist-1950 | highres-future-ssp245 | Variables |
| --- | --- | --- | --- |
| Atmosphere 2D | `.atmos.gr025.2d_daily_mean` | same | 21 fields: `tas`, `ts`, `ps`, `psl`, `uas`, `vas`, `sfcwind`, `pr`, `evspsbl`, `prw`, `qrvi`, `clt`, `hur`, `hus2m`, `hfls`, `hfss`, `rlds`, `rlus`, `rlut`, `rsds`, `rsus` |
| Atmosphere 2D, maxima | `.atmos.gr025.2d_daily_max` | same | `tas`, `sfcwind`, `hur` |
| Atmosphere 2D, minima | `.atmos.gr025.2d_daily_min` | same | `tas`, `hur` |
| Atmosphere 3D (19 pressure levels) | `.atmos.gr025.plev19_daily_mean` | `.atmos.gr025.plev19_1d_mean` | `ta`, `ua`, `va`, `wa`, `hus`, `hur`, `gpsm` |
| Ocean 2D | `.ocean.gr025.2d_daily_mean` | same | 34 fields: `to`, `so`, `u`, `v` (top level), `ssh`, `mlotst`, `mlotst10`, sea ice and surface fluxes |
| Ocean 2D, squared SST | `.ocean.gr025.2d_daily_square` | same | `to` |
| Ocean 3D (6 levels, 1-1452 m) | `.ocean.gr025.5lev_daily_mean` | same | `to`, `so`, `u`, `v` |
| Ocean vertical velocity (6 levels) | `.ocean.gr025.5lev_daily_w_mean` | `.ocean.gr025.5lev_daily_mean_vertical` | `w` |

The control run has the same daily datasets as hist-1950, except vertical velocity in `.ocean.gr025.5lev_daily_mean_w`; its daily pressure levels cover only 2000-2026, and it has an extra daily SST dataset for 1991-2041 (`.ocean.gr025.2d_daily_mean_sst_50year`, variable `sst`).

## 6-hourly and hourly

| Field | hist-1950 | highres-future-ssp245 | Variables |
| --- | --- | --- | --- |
| Atmosphere 2D, 6-hourly instantaneous | `.atmos.gr025.2d_6hourly_inst` | `.atmos.gr025.2d_6hr_inst` | `hus2m`, `psl`, `ts`, `uas`, `vas` |
| Atmosphere 2D, 6-hourly mean | `.atmos.gr025.2d_6hourly_mean` | `.atmos.gr025.2d_6hr_mean` | `pr` |
| Atmosphere 3D, 6-hourly instantaneous (850, 700, 500, 250 hPa) | `.atmos.gr025.pl_6hourly_inst` | `.atmos.gr025.pl_6hr_inst` | `ta`, `ua`, `va`, `wa`, `hus`, `gpsm` |
| Atmosphere 2D, hourly (0.1° grid, 2005-2014) | `.atmos.gr025.2d_hourly_mean`, `.atmos.gr025.2d_hourly_inst` | Not available | `pr` (mean), `rlut` (instantaneous) |

The control run has no 6-hourly or hourly data on the cloud. The hourly datasets are on a 0.1° grid (1800 x 3600) despite the `gr025` label.
