---
title: IFS-FESOM2-SR
nav_order: 3
has_children: true
---

# IFS-FESOM2-SR (AWI)

Coupled IFS atmosphere and eddy-rich FESOM2 ocean (NG5 mesh). Three ensemble members, all regridded to 0.25° (721 x 1440 points). Every dataset listed on these pages was checked on the DKRZ cloud on 12 October 2026.

## Time coverage

| Member | Experiment | Atmosphere monthly and daily | Atmosphere 6-hourly | Ocean |
| --- | --- | --- | --- | --- |
| [1](member-1) | hist-1950 | 1950-2014 | 1970-2014 | 1950-2014 |
| | highres-future-ssp245 | 2015-2070 | 2015-2070 | 2015-2050 |
| | eerie-control-1950 | 1950-2050 | 1971-2050 | 1950-2050 |
| [2](member-2) | hist-1950 | 1975-2014 | 1975-2014 | 1975-2014 (daily 2D only) |
| | highres-future-ssp245 | 2015-2030 | 2015-2030 | 2015-2030 (daily 2D only) |
| [3](member-3) | hist-1950 | 1975-2014 | 1975-2014 | 1975-2014 (daily 2D only) |
| | highres-future-ssp245 | 2015-2030 | 2015-2030 | Not available |

The control run uses constant 1950 forcing, so its years are model years.

## Atmosphere data needs one extra step

The 0.25° atmosphere datasets store the grid as a single `value` dimension (721 x 1440 = 1,038,240 points) instead of separate `lat` and `lon`. Reshape them with this function before plotting or selecting regions:

```python
import numpy as np
import xarray as xr

def to_latlon(da):
    """Reshape an IFS 0.25 deg field from (..., value) to (..., lat, lon)."""
    lat = np.linspace(90, -90, 721)        # grid starts at 90N
    lon = np.arange(1440) * 0.25           # 0 to 359.75E (the file stores 180-359.75 as negative values)
    data = da.data.reshape(da.shape[:-1] + (721, 1440))
    coords = {d: da[d] for d in da.dims[:-1]}
    return xr.DataArray(data, dims=da.dims[:-1] + ("lat", "lon"),
                        coords={**coords, "lat": lat, "lon": lon},
                        name=da.name, attrs=da.attrs)

ds = open_eerie("ifs-fesom2-sr.hist-1950.v20240304.atmos.gr025.2D_monthly_avg")
t2m = to_latlon(ds["mean2t"])
```

Ocean datasets already have `lat` and `lon` and need no reshaping.

## Variables

The [Variables](variables) page lists every variable with its description and units. Atmosphere variables are identical across all members and experiments; ocean variables differ slightly and are listed per dataset on the member pages.

**Reference:** Ghosh et al. (2026), [doi:10.5194/egusphere-2026-1289](https://doi.org/10.5194/egusphere-2026-1289).
