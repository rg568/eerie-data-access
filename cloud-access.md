---
title: "A: Stream without Levante"
nav_order: 2
---

# Route A: stream regridded data without a Levante account

The DKRZ [km-scale cloud](https://km-scale-cloud.dkrz.de) (formerly eerie.cloud) serves EERIE output over HTTP as Zarr. Any machine with Python and internet access can open it lazily and download only the subset it needs. Alongside the native grids, data is provided on the common 0.25° regular grid for inter-model comparison.

Browse the datasets in the STAC browser: [EERIE collection](https://discover.dkrz.de/external/stac2.cloud.dkrz.de/fastapi/collections/eerie?.language=en).

Dataset ids use the same names as the Levante catalogue, joined by dots and without the `dkrz.disk.model-output.` prefix. For example, the Levante entry `dkrz.disk.model-output.icon-esm-er.highres-future-ssp245.v20240618.atmos.native.mon` is the cloud dataset `icon-esm-er.highres-future-ssp245.v20240618.atmos.native.mon`. Use the [Catalogue keys](catalogue-keys) page to find the entry you need, then search for it in the dataset list below.

## Find and open a regridded dataset

```python
import requests, xarray as xr

base = "https://km-scale-cloud.dkrz.de/datasets"
ids = requests.get(base).json()

# list regridded (gr025) datasets for one model
print([d for d in ids if "gr025" in d and "ifs-fesom2-sr" in d])

ds = xr.open_dataset(f"{base}/<dataset_id>/kerchunk",
                     engine="zarr", chunks="auto", zarr_format=2)

# subset first, then load
sub = ds["<var>"].sel(time=slice("1975", "2014")).load()
```

The same datasets are also reachable through the intake catalogue with `cat["dkrz.cloud"]` (requires `intake<2`).

## Practical notes

- Use the `/kerchunk` endpoint by default. The `/zarr` endpoint rechunks and compresses on the server and is better on slow connections.
- The server allows about 200 concurrent requests per client IP and 60 per dataset; beyond that it returns HTTP 429. Limit parallel requests:

  ```python
  import aiohttp
  so = {"client_kwargs": {"connector": aiohttp.TCPConnector(limit=2)}}
  ds = xr.open_dataset(url, engine="zarr", storage_options=so)
  ```

- Always subset in time and space before `.load()`. `ds.nbytes` shows the uncompressed size.
- Environment: `xarray`, `zarr`, `dask`, `aiohttp`, `requests` (plus `pystac` for STAC, `eccodes` for GRIB-backed datasets).
- Full walkthrough with datatree, STAC and intake examples: [easy.gems: The km-scale cloud by DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_online.html).

If a dataset returns HTTP 403, it is not yet released on the cloud. Open an issue and I can check whether it can be shared by another route.
