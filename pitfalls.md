---
title: Known pitfalls
nav_order: 5
---

# Known pitfalls

- **Catalogue keys differ between models and experiments.** Browse with `list(cat[...])` rather than guessing; ICON 3D entries in particular change name between experiments (see [Catalogue keys](catalogue-keys)).
- **FESOM member numbering:** processed folders are offset by one. `Phase2-HIST-ENS1-FESOM` is member r2 and `Phase2-HIST-ENS2-FESOM` is member r3.
- **IFS-NEMO r2/r3:** some historical files contain data before 1975; apply `.sel(time=slice("1975", None))`.
- **Regular vs native grid:** gr025 entries are already regular lat-lon. Only native IFS atmosphere output needs unstacking to lat-lon; never apply that to ocean fields.
- **Signs and units:** FESOM mixed-layer depth `avg_mlotst030` is stored negative-down; IFS wind stress `metss`/`mntss` is already in Pa (mean rate).
- **IFS-FESOM control-1950** follows a 50-year spin-up under 1950 forcing, so its model year 1950 is not the observed 1950 state.
- **Large file sets:** with about 480 monthly files, `open_mfdataset(parallel=True, combine="by_coords")` can run out of memory. A sorted file list with `combine="nested"` and `parallel=False` is reliable.

## Sources

- [eerie-project/intake_catalogues](https://github.com/eerie-project/intake_catalogues)
- [easy.gems: The km-scale cloud by DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_online.html)
- [easy.gems: How to work with EERIE data on DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_dkrz.html)
- [Publication of EERIE Phase 1 Simulations (Zenodo)](https://zenodo.org/records/17465311)
