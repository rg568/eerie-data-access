---
title: Home
nav_order: 1
---

# EERIE km-scale coupled model data

This site lists the EERIE coupled simulations regridded to a common **0.25° regular lat-lon grid**, for every model and ensemble member, at monthly, daily and 6-hourly frequency. Regridded data is the easiest to work with and compare across models, so it is what this guide focuses on.

## Do I need a DKRZ account?

**No.** All regridded data on this site is served openly by the [DKRZ km-scale cloud](https://km-scale-cloud.dkrz.de). You can stream it with xarray from your laptop or any cluster, without logging in. A DKRZ account is only needed for the native-grid (full resolution) output and a few extra fields; see [On Levante](levante).

## Quick start

```python
import xarray as xr

def open_eerie(dataset_id):
    url = f"https://km-scale-cloud.dkrz.de/datasets/{dataset_id}/kerchunk"
    return xr.open_dataset(url, engine="zarr", chunks="auto", zarr_format=2)

ds = open_eerie("ifs-fesom2-sr.hist-1950.v20240304.ocean.gr025.2D_monthly_avg")
sst = ds["avg_tos"].sel(time=slice("1980", "2014"))
```

Pick a model and ensemble member in the menu on the left to find the dataset id you need. [Getting started](getting-started) has more on opening and subsetting the data.

## What is available

| Model | Member | Monthly | Daily | 6-hourly |
| --- | --- | --- | --- | --- |
| [IFS-FESOM2-SR](ifs-fesom/) | [1](ifs-fesom/member-1) | Atmosphere and ocean, 2D and 3D | Atmosphere and ocean, 2D and 3D | Atmosphere, 2D and 3D |
| | [2](ifs-fesom/member-2), [3](ifs-fesom/member-3) (1975-2030) | Atmosphere, 2D and 3D | Atmosphere 2D and 3D, ocean 2D | Atmosphere, 2D and 3D |
| [ICON-ESM-ER](icon/) | [1](icon/member-1) | Atmosphere and ocean, 2D and 3D | Atmosphere and ocean, 2D and 3D | Atmosphere, 2D and 3D (plus hourly 2D) |
| | [2](icon/member-2), [3](icon/member-3) (1975-2014) | Atmosphere and ocean, 2D | Atmosphere 2D, ocean 2D and upper 6 levels | None |
| [IFS-NEMO-ER](ifs-nemo) | 1 | Atmosphere and ocean, 2D and 3D, sea ice | Control run only | On Levante only |

**Experiments:** `hist-1950` (historical, from 1950), `highres-future-ssp245` (SSP2-4.5, from 2015) and `eerie-control-1950` (constant 1950 forcing). Time coverage differs between models and members; each model page has a coverage table.

## Other sources

A CMOR-standardised subset of the Phase 1 simulations is also published on ESGF ([DKRZ node](https://esgf-metagrid.cloud.dkrz.de)), with Met Office data at CEDA. Use it when you need citable files with CMIP-style metadata. The release is described on [Zenodo (record 17465311)](https://zenodo.org/records/17465311).

HadGEM3-GC5E (Met Office) output is published at CEDA and on ESGF.

## Contact and acknowledgement

Questions or missing data: open an [issue](https://github.com/rg568/eerie-data-access/issues) or email Rohit Ghosh (rohit.ghosh@awi.de).

When using the data, please acknowledge the EERIE project (EU Horizon Europe) and DKRZ for data hosting. For IFS-FESOM, cite Ghosh et al. (2026), [doi:10.5194/egusphere-2026-1289](https://doi.org/10.5194/egusphere-2026-1289).
