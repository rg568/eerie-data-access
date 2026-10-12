---
title: On Levante
nav_order: 7
---

# Working on Levante

You only need Levante for:

- **Native-grid output** at full model resolution (IFS octahedral grid, FESOM NG5 mesh, ICON triangular grid, NEMO ORCA12)
- **IFS-NEMO-ER daily and sub-daily** data for `hist-1950`, and members 2 and 3
- **Processed IFS-FESOM ocean files** listed below

Everything on the other pages can also be streamed on Levante itself with `open_eerie()`.

## Access

Register at the DKRZ user portal ([luv.dkrz.de](https://luv.dkrz.de)), then request membership of project bm1344 and let me know so the request can be approved.

## Intake catalogue

```python
import intake
cat = intake.open_catalog(
    "https://raw.githubusercontent.com/eerie-project/intake_catalogues/main/eerie.yaml")
```

Cloud dataset ids translate to Levante catalogue keys as follows:

| Data | Levante key |
| --- | --- |
| IFS-FESOM and ICON, member 1 | `dkrz.disk.model-output.` + cloud id |
| IFS-FESOM, members 2 and 3 | `dkrz.disk.phase2-model-output.` + cloud id |
| IFS-NEMO-ER | `dkrz.disk.CMOR.ifs-nemo-er.<exp>.v20250516.gr025.<table>` (no `atmos`) |
| Native grid, member 1 | replace `gr025` with `native` in the member 1 key |

```python
# Regridded, same data as the cloud
ds = cat["dkrz.disk.model-output.ifs-fesom2-sr.hist-1950.v20240304.ocean.gr025.2D_monthly_avg"].to_dask()

# Native FESOM mesh, full resolution
ds = cat["dkrz.disk.model-output.ifs-fesom2-sr.hist-1950.v20240304.ocean.native.3D_monthly_avg"].to_dask()

# Browse one level at a time
list(cat["dkrz.disk.model-output.icon-esm-er.hist-1950.v20240618.atmos"])
```

ICON members 2 and 3 are catalogued on Levante on the native grid only; use the cloud ids for their regridded data. Background: [easy.gems: How to work with EERIE data on DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_dkrz.html).

## Processed IFS-FESOM ocean files

Regridded 0.25° NetCDF files I maintain, readable with `xr.open_mfdataset`:

| Member | Content | Path |
| --- | --- | --- |
| 1 | Ocean 2D monthly, 1950-2014 | `/work/bm1344/a270228/Phase1-HIST-FESOM/monthly/2d/` |
| 2 | Ocean 2D monthly, historical | `/work/bm1344/a270228/Phase2-HIST-ENS1-FESOM/` |
| 3 | Ocean 2D monthly, historical | `/work/bm1344/a270228/Phase2-HIST-ENS2-FESOM/` |
| 1 | Ocean 3D monthly, one file per year, 1950-2014 | `/work/bm1344/a270228/Phase1-HIST-FESOM/remapped_025deg_monmean/<var>/` |
| 1 | Same, SSP245 to 2050 | `/work/bm1344/a270228/Phase1-SSP245-FESOM/remapped_025deg_monmean/<var>/` |

Note the folder offset: `ENS1` is member 2 and `ENS2` is member 3.
