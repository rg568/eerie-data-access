---
title: IFS-NEMO-ER
nav_order: 5
---

# IFS-NEMO-ER (BSC)

Coupled IFS atmosphere and NEMO ocean (1/12°). Data is provided as CMOR tables on the 0.25° grid, so 2D and 3D variables of one realm and frequency share a dataset. Member 1 is on the cloud; members 2 and 3 are on Levante only.

**Prefix:** `ifs-nemo-er.<exp>.v20250516.atmos.gr025` (the `atmos` part appears in every id, including the ocean tables)

```python
ds = open_eerie("ifs-nemo-er.hist-1950.v20250516.atmos.gr025.Omon")
```

## Monthly means (0.25°)

| Table | Content | Example variables | Experiments |
| --- | --- | --- | --- |
| `Amon` | Atmosphere, 2D and pressure levels | `tas`, `pr`, `clt`, `hfls`, `hfss`, `hus`, `hur` | hist-1950, highres-future-ssp245 |
| `Omon` | Ocean, 2D and depth levels | `tos`, `sos`, `zos`, `mlotst`, `thetao`, `so` | hist-1950, highres-future-ssp245 |
| `SImon` | Sea ice | `siconc`, `sithick`, `sivol` | hist-1950, highres-future-ssp245 |
| `HROmon` | Additional ocean diagnostics | | highres-future-ssp245 |

## Daily and sub-daily (0.25°)

On the cloud, daily data exists for `eerie-control-1950` only:

| Table | Content | Example variables |
| --- | --- | --- |
| `day` | Atmosphere | `tas`, `pr`, `uas`, `vas`, `hfls`, `hfss` |
| `Oday` | Ocean | `tos`, `sos` |
| `HROday` | Additional ocean diagnostics | |

Daily and sub-daily tables for `hist-1950` (`day`, `Oday`, `Eday`, `HRday`, `HROday`, `6hrPlevPt`, `HR6hr`, `E1hr`) are available through the Levante catalogue; see [On Levante](levante).
