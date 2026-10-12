---
title: ICON-ESM-ER
nav_order: 4
has_children: true
---

# ICON-ESM-ER (MPI-M)

Coupled ICON atmosphere and eddy-rich ICON-O ocean. Three ensemble members, regridded to 0.25°.

| Member | Experiments | Monthly | Daily | Sub-daily |
| --- | --- | --- | --- | --- |
| [Member 1](member-1) (`v20240618`) | hist-1950, highres-future-ssp245, eerie-control-1950 | Atmosphere and ocean, 2D and 3D | Atmosphere and ocean, 2D and 3D | Atmosphere 6-hourly 2D and 3D, hourly 2D |
| [Member 2](member-2) (`r2i1p1f1`) | hist-1950 | Atmosphere and ocean, 2D | Atmosphere 2D, ocean 2D and upper 5 levels | None |
| [Member 3](member-3) (`r3i1p1f1`) | hist-1950 | Atmosphere and ocean 2D, MOC | Atmosphere 2D, ocean 2D and upper 5 levels | None |

**Variable names.** Atmosphere uses CMIP-like names (`pr`, `clt`, `ua`, `ta`); ocean uses ICON names (`to` for temperature, `so` for salinity, `u`, `v`).

**Watch out:** ICON dataset names are not always the same between experiments (for example `plev19_monthly_mean` in hist-1950 but `plev19_1mth_mean` in highres-future-ssp245). The member pages list both.
