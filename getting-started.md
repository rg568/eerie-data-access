---
title: Getting started
nav_order: 2
---

# Getting started

## Open a dataset

Every dataset has an id such as `ifs-fesom2-sr.hist-1950.v20240304.ocean.gr025.2D_monthly_avg`. The model and member pages list the ids; this function opens any of them:

```python
import xarray as xr

def open_eerie(dataset_id):
    url = f"https://km-scale-cloud.dkrz.de/datasets/{dataset_id}/kerchunk"
    return xr.open_dataset(url, engine="zarr", chunks="auto", zarr_format=2)
```

Opening is lazy: only metadata is read until you call `.load()`, `.compute()` or plot.

## Subset before loading

```python
ds = open_eerie("icon-esm-er.hist-1950.v20240618.ocean.gr025.ml_monthly_mean")

# Temperature in the 40-70N band, 1980-2014
sub = ds["to"].sel(time=slice("1980", "2014"), lat=slice(40, 70))
print(sub.nbytes / 1e9, "GB")   # check the size first
sub = sub.load()
```

Check coordinate names, their order and the longitude convention (-180 to 180 or 0 to 360) with `print(ds)` first; they differ between models.

## List what exists

```python
import requests
ids = requests.get("https://km-scale-cloud.dkrz.de/datasets").json()

[d for d in ids if d.startswith("ifs-fesom2-sr.hist-1950.r2i1p1f1") and "gr025" in d]
```

You can also browse everything in the [STAC browser](https://discover.dkrz.de/external/stac2.cloud.dkrz.de/fastapi/collections/eerie?.language=en).

## Practical notes

- **Environment:** `xarray`, `zarr`, `dask`, `aiohttp`, `requests`. If an older zarr version complains about `zarr_format`, leave that argument out.
- **Rate limits:** the server allows about 200 parallel requests per client and 60 per dataset, then returns HTTP 429. If that happens, limit concurrency:

  ```python
  import aiohttp
  so = {"client_kwargs": {"connector": aiohttp.TCPConnector(limit=2)}}
  ds = xr.open_dataset(url, engine="zarr", chunks="auto", storage_options=so)
  ```

- **Slow connection:** replace `/kerchunk` with `/zarr` in the URL. The server then sends compressed chunks.
- **Intake:** the same datasets are in the EERIE intake catalogue under `cat["dkrz.cloud"]` (requires `intake<2`).
- Full DKRZ walkthrough: [easy.gems: The km-scale cloud by DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_online.html).
