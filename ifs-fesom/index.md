---
title: IFS-FESOM2-SR
nav_order: 3
has_children: true
---

# IFS-FESOM2-SR (AWI)

Coupled IFS atmosphere and eddy-rich FESOM2 ocean (NG5 mesh). Three ensemble members, all regridded to 0.25°.

| Member | Experiments | Monthly | Daily | 6-hourly |
| --- | --- | --- | --- | --- |
| [Member 1](member-1) (`v20240304`) | hist-1950, highres-future-ssp245, eerie-control-1950 | Atmosphere and ocean, 2D and 3D | Atmosphere and ocean, 2D and 3D | Atmosphere, 2D and 3D |
| [Member 2](member-2) (`r2i1p1f1`) | hist-1950, highres-future-ssp245 | Atmosphere, 2D and 3D | Atmosphere 2D and 3D, ocean 2D | Atmosphere, 2D and 3D |
| [Member 3](member-3) (`r3i1p1f1`) | hist-1950, highres-future-ssp245 | Atmosphere, 2D and 3D | Atmosphere 2D and 3D, ocean 2D (historical only) | Atmosphere, 2D and 3D |

**Variable names.** Ocean fields carry an `avg_` prefix (`avg_tos`, `avg_thetao`). Atmosphere fields use IFS short names; monthly and daily means of rates start with `m` (`msshf`, `metss`), and 3D monthly fields are `mt`, `mu`, `mv`, `mw`, `mz`, `mq`, `mr` on pressure levels.

**Reference:** Ghosh et al. (2026), [doi:10.5194/egusphere-2026-1289](https://doi.org/10.5194/egusphere-2026-1289).
