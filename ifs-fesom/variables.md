---
title: Variables
parent: IFS-FESOM2-SR
nav_order: 4
---

# IFS-FESOM2-SR variables

Read from the dataset metadata on the DKRZ cloud on 12 October 2026. Atmosphere variables are the same for all members and experiments. Units are as stored in the files.

## Atmosphere 2D means

In `2D_monthly_avg` and `2D_daily_avg` (43 variables).

| Variable | Description | Units |
| --- | --- | --- |
| `cprate` | Mean convective precipitation rate | m s⁻¹ |
| `erate` | Evaporation | m of water equivalent s⁻¹ |
| `m10u` | Time-mean 10 metre U wind component | m s⁻¹ |
| `m10v` | Time-mean 10 metre V wind component | m s⁻¹ |
| `m2d` | Time-mean 2 metre dewpoint temperature | K |
| `m2sh` | Time-mean 2 metre specific humidity | kg kg⁻¹ |
| `mblh` | Time-mean boundary layer height | m |
| `mci` | Time-mean sea ice area fraction | (0 - 1) |
| `mean10ws` | Mean of 10 metre wind speed | m s⁻¹ |
| `mean2t` | Mean 2 metre temperature | K |
| `meantcc` | Mean total cloud cover | (0 - 1) |
| `metss` | Mean eastward turbulent surface stress | N m⁻² |
| `mhcc_frac` | Time-mean high cloud cover | (0 - 1) |
| `mlcc_frac` | Time-mean low cloud cover | (0 - 1) |
| `mmcc_frac` | Time-mean medium cloud cover | (0 - 1) |
| `mmsl` | Time-mean mean sea level pressure | Pa |
| `mntss` | Mean northward turbulent surface stress | N m⁻² |
| `mrort` | Mean runoff rate | m s⁻¹ |
| `msd_m` | Time-mean snow depth | m of water equivalent |
| `msdwlwrf` | Mean surface downward long-wave radiation flux | W m⁻² |
| `msdwswrf` | Mean surface downward short-wave radiation flux | W m⁻² |
| `mskt` | Time-mean skin temperature | K |
| `mslhf` | Mean surface latent heat flux | W m⁻² |
| `msnlwrf` | Mean surface net long-wave radiation flux | W m⁻² |
| `msnlwrfcs` | Mean surface net long-wave radiation flux, clear sky | W m⁻² |
| `msnswrf` | Mean surface net short-wave radiation flux | W m⁻² |
| `msnswrfcs` | Mean surface net short-wave radiation flux, clear sky | W m⁻² |
| `msp` | Time-mean surface pressure | Pa |
| `msror` | Mean surface runoff rate | m s⁻¹ |
| `msshf` | Mean surface sensible heat flux | W m⁻² |
| `mssror` | Mean sub-surface runoff rate | m s⁻¹ |
| `msst` | Time-mean sea surface temperature | K |
| `mtciw` | Time-mean total column cloud ice water | kg m⁻² |
| `mtclw` | Time-mean total column liquid water | kg m⁻² |
| `mtcw` | Time-mean total column water | kg m⁻² |
| `mtcwv` | Time-mean total column vertically-integrated water vapour | kg m⁻² |
| `mtdwswrf` | Mean top downward short-wave radiation flux | W m⁻² |
| `mtnlwrf` | Mean top net long-wave radiation flux | W m⁻² |
| `mtnlwrfcs` | Mean top net long-wave radiation flux, clear sky | W m⁻² |
| `mtnswrf` | Mean top net short-wave radiation flux | W m⁻² |
| `mtnswrfcs` | Mean top net short-wave radiation flux, clear sky | W m⁻² |
| `mtsfr` | Mean total snowfall rate | m of water equivalent s⁻¹ |
| `tprate` | Mean total precipitation rate | m s⁻¹ |

## Atmosphere 2D maxima and minima

In `2D_monthly_max`, `2D_monthly_min`, `2D_daily_max` and `2D_daily_min`.

| Variable | Description | Units |
| --- | --- | --- |
| `mx2t` | Maximum 2 metre temperature (monthly maximum dataset) | K |
| `mn2t` | Minimum 2 metre temperature (monthly minimum dataset) | K |
| `mx2t24` | Maximum 2 metre temperature in the past 24 hours (daily maximum dataset) | K |
| `mn2t24` | Minimum 2 metre temperature in the past 24 hours (daily minimum dataset) | K |
| `10fg` | Maximum 10 metre wind gust (daily and monthly maximum datasets) | m s⁻¹ |

## Atmosphere 2D, 6-hourly instantaneous

In `2D_6hourly_instant` (22 variables), values at the time stamp.

| Variable | Description | Units |
| --- | --- | --- |
| `10si` | 10 metre wind speed | m s⁻¹ |
| `10u` | 10 metre U wind component | m s⁻¹ |
| `10v` | 10 metre V wind component | m s⁻¹ |
| `2d` | 2 metre dewpoint temperature | K |
| `2sh` | 2 metre specific humidity | kg kg⁻¹ |
| `2t` | 2 metre temperature | K |
| `blh` | Boundary layer height | m |
| `ci` | Sea ice area fraction | (0 - 1) |
| `hcc` | High cloud cover | (0 - 1) |
| `i10fg` | Instantaneous 10 metre wind gust | m s⁻¹ |
| `lcc` | Low cloud cover | (0 - 1) |
| `mcc` | Medium cloud cover | (0 - 1) |
| `msl` | Mean sea level pressure | Pa |
| `sd` | Snow depth | m of water equivalent |
| `skt` | Skin temperature | K |
| `sp` | Surface pressure | Pa |
| `sst` | Sea surface temperature | K |
| `tcc` | Total cloud cover | (0 - 1) |
| `tciw` | Total column cloud ice water | kg m⁻² |
| `tclw` | Total column cloud liquid water | kg m⁻² |
| `tcw` | Total column water | kg m⁻² |
| `tcwv` | Total column vertically-integrated water vapour | kg m⁻² |

## Atmosphere 2D, 6-hourly accumulated

In `2D_6hourly_accumulated` (22 variables). Each value is the total over the preceding 6 hours; divide by 21600 s to convert to a rate (for example J m⁻² to W m⁻²).

| Variable | Description | Units |
| --- | --- | --- |
| `cp` | Convective precipitation | m |
| `e` | Evaporation | m of water equivalent |
| `ewss` | Time-integrated eastward turbulent surface stress | N m⁻² s |
| `nsss` | Time-integrated northward turbulent surface stress | N m⁻² s |
| `ro` | Runoff | m |
| `sf` | Snowfall | m of water equivalent |
| `slhf` | Surface latent heat flux | J m⁻² |
| `sro` | Surface runoff | m |
| `sshf` | Surface sensible heat flux | J m⁻² |
| `ssr` | Surface net short-wave (solar) radiation | J m⁻² |
| `ssrc` | Surface net short-wave (solar) radiation, clear sky | J m⁻² |
| `ssrd` | Surface short-wave (solar) radiation downwards | J m⁻² |
| `ssro` | Sub-surface runoff | m |
| `str` | Surface net long-wave (thermal) radiation | J m⁻² |
| `strc` | Surface net long-wave (thermal) radiation, clear sky | J m⁻² |
| `strd` | Surface long-wave (thermal) radiation downwards | J m⁻² |
| `tisr` | TOA incident short-wave (solar) radiation | J m⁻² |
| `tp` | Total precipitation | m |
| `tsr` | Top net short-wave (solar) radiation | J m⁻² |
| `tsrc` | Top net short-wave (solar) radiation, clear sky | J m⁻² |
| `ttr` | Top net long-wave (thermal) radiation | J m⁻² |
| `ttrc` | Top net long-wave (thermal) radiation, clear sky | J m⁻² |

## Atmosphere 3D

On 19 pressure levels: 1, 5, 10, 20, 30, 50, 70, 100, 150, 200, 250, 300, 400, 500, 600, 700, 850, 925, 1000 hPa (coordinate `level`).

Monthly and daily means (`3D_monthly_avg`, `3D_daily_avg`):

| Variable | Description | Units |
| --- | --- | --- |
| `mq` | Time-mean specific humidity | kg kg⁻¹ |
| `mr` | Time-mean relative humidity | % |
| `mt` | Time-mean temperature | K |
| `mu` | Time-mean U component of wind | m s⁻¹ |
| `mv` | Time-mean V component of wind | m s⁻¹ |
| `mw` | Time-mean vertical velocity | Pa s⁻¹ |
| `mz` | Time-mean geopotential | m² s⁻² |

6-hourly instantaneous (`3D_6hourly`):

| Variable | Description | Units |
| --- | --- | --- |
| `q` | Specific humidity | kg kg⁻¹ |
| `r` | Relative humidity | % |
| `t` | Temperature | K |
| `u` | U component of wind | m s⁻¹ |
| `v` | V component of wind | m s⁻¹ |
| `w` | Vertical velocity | Pa s⁻¹ |
| `z` | Geopotential | m² s⁻² |

## Ocean 2D

Stored with a singleton `lev` dimension; use `.squeeze("lev")`. Which variables are in which dataset is listed on each member page.

| Variable | Description | Units |
| --- | --- | --- |
| `avg_tos` | Sea surface temperature | K |
| `avg_sos` | Sea surface practical salinity | g kg⁻¹ |
| `avg_zos` | Sea surface height | m |
| `avg_mlotst030` | Mixed layer depth, sigma-theta criterion 0.03 kg m-3 | m |
| `avg_mlotst125` | Mixed layer depth, sigma-theta criterion 0.125 kg m-3 | m |
| `avg_siconc` | Sea ice area fraction | fraction |
| `avg_sithick` | Sea ice thickness | m |
| `avg_sisnthick` | Snow thickness over sea ice | m |
| `avg_sigrowth` | Sea ice growth | m s⁻¹ |
| `avg_siue` | Eastward sea ice velocity | m s⁻¹ |
| `avg_sivn` | Northward sea ice velocity | m s⁻¹ |

## Ocean 3D

In `3D_monthly_avg` (69 depth levels, 2.5 to 6175 m) and `3D_daily_avg` (7 levels: 2.5, 12.5, 97.5, 195, 600, 950, 1415 m). Coordinate `lev`, in metres.

| Variable | Description | Units |
| --- | --- | --- |
| `avg_thetao` | Sea water potential temperature | K |
| `avg_so` | Sea water practical salinity | g kg⁻¹ |
| `avg_uoe` | Eastward sea water velocity | m s⁻¹ |
| `avg_von` | Northward sea water velocity | m s⁻¹ |
| `avg_wo` | Upward sea water velocity | m s⁻¹ |

## AMOC

In `AMOC`: `atlantic_moc`, Atlantic meridional overturning streamfunction in Sv, on 70 depths and 235 latitudes, monthly.
