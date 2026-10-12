---
title: ICON-ESM-ER
nav_order: 4
has_children: true
---

# ICON-ESM-ER (MPI-M)

Coupled ICON atmosphere and eddy-rich ICON-O ocean. Three ensemble members, regridded to 0.25° (721 x 1440 points, with `lat` and `lon` ready to use). Every dataset on these pages was checked on the DKRZ cloud on 12 October 2026.

## Time coverage

| Member | Experiment | Coverage | Notes |
| --- | --- | --- | --- |
| [1](member-1) | hist-1950 | 1950-2014 | Hourly data 2005-2014 only; eddy terms 1950-1970 |
| | highres-future-ssp245 | 2015-2050 | |
| | eerie-control-1950 | 1950-2050 | Daily pressure levels 2000-2026 only |
| [2](member-2) | hist-1950 | 1975-2014 | Some time steps missing; daily 5-level ocean 1975-2001 only |
| [3](member-3) | hist-1950 | 1975-2014 | Some time steps missing; daily 5-level ocean 1975-2001 only |

Members 2 and 3 have no future scenario on the cloud. Their monthly series are a few months short of complete (for example 474 and 461 of 480 months for ocean 2D), so check `ds.time` for gaps before computing climatologies or trends.

**Time stamps:** some ICON output is stamped at the end of the averaging period (6-hourly ssp245 data ends on 2051-01-01, for example). Check the stamps before grouping by month or day.

**Variable names.** Atmosphere uses CMIP-like names (`tas`, `pr`, `ua`, `ta`); ocean uses ICON names (`to` for temperature in °C, `so` for salinity, `u`, `v`, `w`). The [Variables](variables) page lists all of them with descriptions and units. Variable sets are the same in all members and experiments.

**Watch out:** ICON dataset names differ between experiments (for example `plev19_monthly_mean` in hist-1950 but `plev19_1mth_mean` in highres-future-ssp245). The member pages list both.
