---
title: Known pitfalls
nav_order: 8
---

# Known pitfalls

- **Dataset names differ between experiments.** ICON in particular renames some datasets between `hist-1950` and `highres-future-ssp245`. Use the tables on the member pages or list the ids (see [Getting started](getting-started)).
- **Variable names differ between models.** SST is `avg_tos` in IFS-FESOM, `to` in ICON and `tos` in IFS-NEMO and HadGEM3.
- **Subset first.** 3D daily and 6-hourly datasets are very large. Select time, region and levels before `.load()`, and check `.nbytes`.
- **IFS-NEMO members 2 and 3** start in 1975; some historical files contain earlier data, so apply `.sel(time=slice("1975", None))`.
- **ICON members 2 and 3:** check time stamps; some output is stamped at the end of the averaging period.
- **Signs and units:** FESOM mixed-layer depth `avg_mlotst030` is stored negative-down; IFS wind stress `metss` is already in Pa (mean rate).
- **IFS-FESOM eerie-control-1950** follows a 50-year spin-up under 1950 forcing, so its model year 1950 is not the observed 1950 state.
- **Many files on Levante:** with hundreds of monthly files, `open_mfdataset(parallel=True, combine="by_coords")` can run out of memory. A sorted file list with `combine="nested"` and `parallel=False` is reliable.

## Sources

- [easy.gems: The km-scale cloud by DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_online.html)
- [easy.gems: How to work with EERIE data on DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_dkrz.html)
- [eerie-project/intake_catalogues](https://github.com/eerie-project/intake_catalogues)
- [Publication of EERIE Phase 1 Simulations (Zenodo)](https://zenodo.org/records/17465311)
