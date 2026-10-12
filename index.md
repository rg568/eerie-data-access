---
title: Home
nav_order: 1
---

# EERIE km-scale coupled model data

Most users only need EERIE coupled model output regridded to the common 0.25° regular lat-lon grid (gr025). That can be streamed from anywhere without a DKRZ account (Route A). Levante access (Route C) is needed for the full archive and for derived fields that are not public, such as 3D ocean fields remapped from the FESOM NG5 mesh.

| Need | Route | Account needed |
| --- | --- | --- |
| Regridded monthly 2D/3D fields for exploration or analysis | [A: DKRZ km-scale cloud](cloud-access) | None |
| Standardised, citable CMOR files (Phase 1 priority variables) | [B: ESGF](esgf) | None for download |
| Full archive, all members, derived fields | [C: Levante](levante) | DKRZ account in project bm1344 |

For the exact catalogue entry to call for 2D and 3D, atmosphere and ocean monthly means of each model, see [Catalogue keys](catalogue-keys).

**Models:** IFS-FESOM2-SR (AWI), IFS-NEMO-ER (BSC), ICON-ESM-ER (MPI-M), HadGEM3-GC5E-HH (Met Office).

**Experiments:** `hist-1950` (1950-2014), `highres-future-ssp245` (2015-2050), `eerie-control-1950`. HadGEM3 uses `historical` and `ssp245`.

## Contact

Questions about access or derived fields: open an [issue](https://github.com/rg568/eerie-data-access/issues) or email Rohit Ghosh (rohit.ghosh@awi.de).

## Acknowledgement

When using the data, please acknowledge the EERIE project (EU Horizon Europe) and DKRZ for data hosting. For IFS-FESOM, cite Ghosh et al. (2026), [doi:10.5194/egusphere-2026-1289](https://doi.org/10.5194/egusphere-2026-1289).
