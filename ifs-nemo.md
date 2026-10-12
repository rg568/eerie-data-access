---
title: IFS-NEMO-ER
nav_order: 5
---

# IFS-NEMO-ER (BSC)

Coupled IFS atmosphere and NEMO ocean (1/12°). Data is provided as CMOR tables on the 0.25° grid (721 x 1440, with `lat` and `lon`), so 2D and 3D variables of one realm and frequency share a dataset. Member 1 is on the cloud; members 2 and 3 are on Levante only. Checked on the DKRZ cloud on 12 October 2026.

**Prefix:** `ifs-nemo-er.<exp>.v20250516.atmos.gr025` (the `atmos` part appears in every id, including the ocean tables)

```python
ds = open_eerie("ifs-nemo-er.hist-1950.v20250516.atmos.gr025.Omon")
```

## Time coverage

| Experiment | Tables | Coverage |
| --- | --- | --- |
| hist-1950 | `Amon`, `Omon`, `SImon` | 1950-2014, complete |
| highres-future-ssp245 | `Amon`, `Omon`, `SImon`, `HROmon` | 2015 to mid-2050, 420 time steps; about 6 months are missing, so check `ds.time` |
| eerie-control-1950 | `day`, `Oday`, `HROday` | 2015-2030 (model years) |

## Monthly means (0.25°)

| Table | Content | Variables |
| --- | --- | --- |
| `Amon` | Atmosphere | 2D: `tas`, `tasmax`, `tasmin`, `ts`, `ps`, `psl`, `uas`, `vas`, `sfcWind`, `tauu`, `tauv`, `hurs`, `pr`, `prc`, `prsn`, `evspsbl`, `prw`, `clt`, `hfls`, `hfss`, `rlds`, `rlut`, `rlutcs`, `rsds`, `rsdt`, plus `clivi` in hist-1950 only. 3D on 19 pressure levels: `ta`, `ua`, `va`, `wap`, `zg`, `hus`, `hur` |
| `Omon` | Ocean | 2D: `tos`, `sos`, `zos`, `mlotst`, `hfds`, `wfo`. 3D on 75 depth levels: `thetao`, `so` |
| `SImon` | Sea ice | `siconc`, `sithick`, `sivol` |
| `HROmon` (ssp245 only) | Ocean vertical velocity | `wo` (75 levels) |

## Daily means (0.25°)

On the cloud, daily data exists for `eerie-control-1950` only:

| Table | Content | Variables |
| --- | --- | --- |
| `day` | Atmosphere | `tas`, `pr`, `uas`, `vas`, `clt`, `hfls`, `hfss` |
| `Oday` | Ocean surface | `tos`, `sos` |
| `HROday` | Upper ocean | 2D: `mlotst`, `zos`. 3D on 5 levels: `thetao`, `so`, `uo`, `vo` |

Daily and sub-daily tables for `hist-1950` (`day`, `Oday`, `Eday`, `HRday`, `HROday`, `6hrPlevPt`, `HR6hr`, `E1hr`) are available through the Levante catalogue; see [On Levante](levante).

## Units

Variables follow CMIP conventions: `tos` and `thetao` in °C, `sos` and `so` in 0.001 (practical salinity), `siconc` in %, `clt` in %, fluxes in W m⁻², precipitation and evaporation in kg m⁻² s⁻¹.
