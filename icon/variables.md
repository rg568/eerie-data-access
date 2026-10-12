---
title: Variables
parent: ICON-ESM-ER
nav_order: 4
---

# ICON-ESM-ER variables

Read from the dataset metadata on the DKRZ cloud on 12 October 2026. Descriptions follow the stored long names; where a file has none, the variable name is self-explanatory or marked as such. Units are as stored. Which variable is in which dataset is listed on the member pages. Variable sets are identical across experiments and members.

## Atmosphere

Pressure-level datasets (`plev19_*`) use 19 levels: 1000, 925, 850, 700, 600, 500, 400, 300, 250, 200, 150, 100, 70, 50, 30, 20, 10, 5, 1 hPa (coordinate `plev_2`, in Pa). The 6-hourly `pl_*` datasets use 4 levels: 850, 700, 500, 250 hPa (coordinate `plev`).

| Variable | Description | Units |
| --- | --- | --- |
| `cli` | Specific cloud ice content | kg kg⁻¹ |
| `clivi` | Cloud ice path | kg m⁻² |
| `cllvi` | Cloud liquid water path | kg m⁻² |
| `clt` | Total cloud cover | m2 m⁻² |
| `clw` | Specific cloud water content | kg kg⁻¹ |
| `evspsbl` | Evaporation | kg m⁻² s⁻¹ |
| `gpsm` | Geopotential above surface | m² s⁻² |
| `hfls` | Latent heat flux | W m⁻² |
| `hfss` | Sensible heat flux | W m⁻² |
| `hur` | Relative humidity | 1 |
| `hus` | Specific humidity | kg kg⁻¹ |
| `hus2m` | Specific humidity at 2 m | kg kg⁻¹ |
| `pr` | Precipitation flux | kg m⁻² s⁻¹ |
| `prw` | Water vapour path | kg m⁻² |
| `ps` | Surface pressure | Pa |
| `psl` | Mean sea level pressure | Pa |
| `qrvi` | Rain path | kg m⁻² |
| `rlds` | Surface downwelling long-wave radiation | W m⁻² |
| `rldscs` | Surface downwelling clear-sky long-wave radiation | W m⁻² |
| `rlus` | Surface upwelling long-wave radiation | W m⁻² |
| `rlut` | TOA outgoing long-wave radiation | W m⁻² |
| `rlutcs` | TOA outgoing clear-sky long-wave radiation | W m⁻² |
| `rsds` | Surface downwelling short-wave radiation | W m⁻² |
| `rsdscs` | Surface downwelling clear-sky short-wave radiation | W m⁻² |
| `rsdt` | TOA incident short-wave radiation | W m⁻² |
| `rsus` | Surface upwelling short-wave radiation | W m⁻² |
| `rsuscs` | Surface upwelling clear-sky short-wave radiation | W m⁻² |
| `rsut` | TOA outgoing short-wave radiation | W m⁻² |
| `rsutcs` | TOA outgoing clear-sky short-wave radiation | W m⁻² |
| `sfcwind` | 10 m wind speed | m s⁻¹ |
| `ta` | Air temperature | K |
| `tas` | 2 m temperature | K |
| `tasmax` | Maximum 2 m temperature | K |
| `tasmin` | Minimum 2 m temperature | K |
| `tauu` | Zonal surface momentum flux | N m⁻² |
| `tauv` | Meridional surface momentum flux | N m⁻² |
| `ts` | Surface temperature | K |
| `ua` | Zonal wind | m s⁻¹ |
| `uas` | Zonal wind at 10 m | m s⁻¹ |
| `va` | Meridional wind | m s⁻¹ |
| `vas` | Meridional wind at 10 m | m s⁻¹ |
| `wa` | Vertical velocity | m s⁻¹ |

## Ocean and sea ice

3D monthly fields (`ml_*`, `model-level_*`) are on 72 model levels from 1 m to about 5816 m (vertical velocity on 73 interfaces). The daily "5lev" datasets hold 6 levels: 1, 50.5, 201.8, 617.1, 997.9, 1451.7 m (coordinate `depth`). Ocean temperature `to` is in °C.

| Variable | Description | Units |
| --- | --- | --- |
| `FrshFlux_IceSalt` | Salt volume flux due to sea ice change | psu m s⁻¹ |
| `FrshFlux_TotalIce` | Freshwater flux due to sea ice change | m s⁻¹ |
| `Qbot` | Conductive heat flux at ice-ocean interface | W m⁻² |
| `Qtop` | Energy flux available for surface melting | W m⁻² |
| `Wind_Speed_10m` | Wind speed at 10 m | m s⁻¹ |
| `atmos_fluxes_FrshFlux_Evaporation` | No long name in file | m s⁻¹ |
| `atmos_fluxes_FrshFlux_Precipitation` | No long name in file | m s⁻¹ |
| `atmos_fluxes_FrshFlux_Runoff` | No long name in file | m s⁻¹ |
| `atmos_fluxes_FrshFlux_SnowFall` | No long name in file | m s⁻¹ |
| `atmos_fluxes_HeatFlux_Latent` | No long name in file | W m⁻² |
| `atmos_fluxes_HeatFlux_LongWave` | No long name in file | W m⁻² |
| `atmos_fluxes_HeatFlux_Sensible` | No long name in file | W m⁻² |
| `atmos_fluxes_HeatFlux_ShortWave` | No long name in file | W m⁻² |
| `atmos_fluxes_HeatFlux_Total` | No long name in file | W m⁻² |
| `atmos_fluxes_stress_x` | No long name in file | Pa |
| `atmos_fluxes_stress_xw` | No long name in file | Pa |
| `atmos_fluxes_stress_y` | No long name in file | Pa |
| `atmos_fluxes_stress_yw` | No long name in file | Pa |
| `conc` | Sea ice concentration | fraction |
| `delhi` | Change in ice mean thickness due to thermodynamic effects | m |
| `delhs` | Change in mean snow thickness due to thermodynamic melting | m |
| `heatOceI` | Heat flux to ocean from ice growth | W m⁻² |
| `heatOceW` | Heat flux to ocean from the atmosphere | W m⁻² |
| `heat_content_seaice` | No long name in file | J m⁻² |
| `heat_content_snow` | Heat content of snow | J m⁻² |
| `heat_content_total` | No long name in file | J m⁻² |
| `hi` | Sea ice thickness | m |
| `hs` | Snow thickness | m |
| `ice_u` | Zonal sea ice velocity | m s⁻¹ |
| `ice_v` | Meridional sea ice velocity | m s⁻¹ |
| `mlotst` | Mixed layer depth (sigma-t criterion) | m |
| `mlotst10` | Mixed layer depth (sigma-t criterion, 10 m reference) | m |
| `newice` | New ice growth in open water | m |
| `rsdoabsorb` | Short-wave energy absorbed in each ocean layer | W m⁻² |
| `sea_level_pressure` | Sea level pressure | Pa |
| `snow_to_ice` | Snow transformed to ice | m |
| `so` | Sea water salinity | psu |
| `ssh` | Sea surface height | m |
| `stretch_c` | z-star surface stretch factor | 1 |
| `to` | Sea water potential temperature (top level = SST) | °C |
| `u` | Zonal ocean velocity | m s⁻¹ |
| `v` | Meridional ocean velocity | m s⁻¹ |
| `w` | Vertical ocean velocity | m s⁻¹ |
| `verticallyTotal_mass_flux_e` | Vertically integrated mass flux | kg s⁻¹ |

## Other datasets

- `eddy_monthly_mean` (member 1): eddy flux terms on 72 levels, such as `uT`, `vT`, `wT`, `uS`, `vS`, `uu`, `vv`, `uv`, `sigma0`.
- `moc_monthly_mean` (member 3): overturning streamfunctions `atlantic_moc`, `pacific_moc`, `global_moc` and the matching basin heat and salt transports.
- `mon` (member 3, atmosphere and ocean): global-mean monitoring time series such as `tas_gmean` and `radtop_gmean`.
- `pfull_*` and `pfull_phalf_*` (member 1): pressure on the 90 model levels.
