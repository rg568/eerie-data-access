---
title: Processed data
parent: "C: Levante"
nav_order: 2
---

# Processed IFS-FESOM data (maintained by Rohit Ghosh)

These directories hold IFS-FESOM ocean output that I have processed from the native NG5 mesh to the 0.25° regular grid, including members and 3D fields not in the catalogue. They are regular NetCDF, readable with `xr.open_mfdataset`.

| Member | Content | Path |
| --- | --- | --- |
| r1 | Ocean 2D monthly (e.g. `avg_tos`), 1950-2014 | `/work/bm1344/a270228/Phase1-HIST-FESOM/monthly/2d/` |
| r2 | Ocean 2D monthly, historical | `/work/bm1344/a270228/Phase2-HIST-ENS1-FESOM/` |
| r3 | Ocean 2D monthly, historical | `/work/bm1344/a270228/Phase2-HIST-ENS2-FESOM/` |
| r1 | Ocean 3D monthly on 0.25°, one file per year (e.g. `avg_so`, `avg_von`), 1950-2014 | `/work/bm1344/a270228/Phase1-HIST-FESOM/remapped_025deg_monmean/<var>/` |
| r1 | Same, SSP245 to 2050 | `/work/bm1344/a270228/Phase1-SSP245-FESOM/remapped_025deg_monmean/<var>/` |

Note the folder offset: `ENS1` is member r2 and `ENS2` is member r3. 3D fields exist for r1 only so far.
