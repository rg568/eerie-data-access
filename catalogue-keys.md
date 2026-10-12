---
title: Catalogue keys
parent: "C: Levante"
nav_order: 1
---

# Catalogue keys for monthly means

All keys below were checked against the [eerie-project/intake_catalogues](https://github.com/eerie-project/intake_catalogues) repository on 12 October 2026. Each key is used as

```python
ds = cat["<key>"].to_dask()
```

Replace `<exp>` with `hist-1950`, `highres-future-ssp245` or `eerie-control-1950`. "3D" means pressure levels for the atmosphere and depth levels for the ocean. All fields are on the 0.25° regular grid unless stated.

## IFS-FESOM2-SR (member r1)

Prefix: `dkrz.disk.model-output.ifs-fesom2-sr.<exp>.v20240304`

| Realm | 2D monthly mean | 3D monthly mean |
| --- | --- | --- |
| Atmosphere | `<prefix>.atmos.gr025.2D_monthly_avg` | `<prefix>.atmos.gr025.3D_monthly_avg` |
| Ocean | `<prefix>.ocean.gr025.2D_monthly_avg` | `<prefix>.ocean.gr025.3D_monthly_avg` |

Available for all three experiments. `hist-1950` also has `ocean.gr025.2D_monthly_avg_mlotst030` (mixed-layer depth) and `ocean.gr025.AMOC`. Native-grid versions replace `gr025` with `native`.

Example:

```python
sst = cat["dkrz.disk.model-output.ifs-fesom2-sr.hist-1950.v20240304.ocean.gr025.2D_monthly_avg"].to_dask()
```

## ICON-ESM-ER (member r1)

Prefix: `dkrz.disk.model-output.icon-esm-er.<exp>.v20240618`

The 2D entries share a name across experiments, but the 3D entries do not:

| Realm | 2D monthly mean | 3D: `hist-1950` | 3D: `highres-future-ssp245` | 3D: `eerie-control-1950` |
| --- | --- | --- | --- | --- |
| Atmosphere | `<prefix>.atmos.gr025.2d_monthly_mean` | `atmos.gr025.plev19_monthly_mean` | `atmos.gr025.plev19_1mth_mean` | `atmos.gr025.plev19_monthly_mean` |
| Ocean | `<prefix>.ocean.gr025.2d_monthly_mean` | `ocean.gr025.ml_monthly_mean` | `ocean.gr025.model-level_monthly_mean` | `ocean.gr025.ml_1mth_mean` |

Ocean SST is variable `to`. Vertical velocity has its own 3D entry (`ml_monthly_w_mean` in `hist-1950`).

Example:

```python
ua = cat["dkrz.disk.model-output.icon-esm-er.hist-1950.v20240618.atmos.gr025.plev19_monthly_mean"].to_dask()
```

## IFS-NEMO-ER (member r1)

IFS-NEMO-ER is catalogued through its CMOR tables, where 2D and 3D variables sit in the same table.

Prefix: `dkrz.disk.CMOR.ifs-nemo-er.<exp>.v20250516.gr025`

| Realm | Monthly mean (2D and 3D) | Typical variables |
| --- | --- | --- |
| Atmosphere | `<prefix>.Amon` | `tas`, `psl` (2D); `ua`, `ta` on pressure levels (3D) |
| Ocean | `<prefix>.Omon` | `tos`, `zos` (2D); `thetao`, `so` (3D) |
| Sea ice | `<prefix>.SImon` | `siconc` |

`Omon` and `SImon` exist for `hist-1950` and `highres-future-ssp245`; `eerie-control-1950` has `Amon` only.

## CMOR tables for IFS-FESOM2-SR and ICON-ESM-ER

The same CMOR route exists for the other two models, useful when you want identical variable names across models:

| Model | Prefix | Tables |
| --- | --- | --- |
| IFS-FESOM2-SR | `dkrz.disk.CMOR.ifs-fesom2-sr.<exp>.v20240304.gr025` | `Amon`, `Omon`, `SImon`, `HROmon` (hist-1950, ssp245) |
| ICON-ESM-ER | `dkrz.disk.CMOR.icon-esm-er.<exp>.v20240618.gr025` | `Amon`, `Omon`, `SImon`, `HRAmon`, `HROmon` (all three experiments) |
| HadGEM3-GC5E-HH | `dkrz.disk.CMOR.HadGEM3-GC5E-HH.<exp>.v20250409.gr1` | `Amon` only; `<exp>` is `historical` or `ssp245` |

HadGEM3 ocean output is catalogued on the JASMIN side (`cat["jasmin"]`, `cat["jasmin_badc"]`) and published at CEDA.

## Additional ensemble members (r2, r3)

| Model | Catalogued | Key |
| --- | --- | --- |
| IFS-FESOM2-SR | Atmosphere, gr025 | `dkrz.disk.phase2-model-output.ifs-fesom2-sr.<exp>.<member>.atmos.gr025.2D_monthly_avg` (and `3D_monthly_avg`), `<exp>` = `hist-1950` or `highres-future-ssp245` |
| IFS-FESOM2-SR | Ocean | Not catalogued; see [Processed data](processed-data) |
| ICON-ESM-ER | Native grid only | `dkrz.disk.phase2-model-output.icon-esm-er.hist-1950.<member>.ocean.native.2d_monthly_mean` (also `atmos.native.2d_monthly_mean`) |
| IFS-NEMO-ER | Not catalogued | CMOR files under `/work/bm1344/DKRZ/CMOR/EERIE/HighResMIP/BSC/IFS-NEMO-ER/` |

`<member>` is `r2i1p1f1` or `r3i1p1f1`. For regridded ICON r2/r3 or FESOM ocean r2/r3, open an issue.
