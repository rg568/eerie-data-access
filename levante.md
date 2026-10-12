---
title: "C: Levante"
nav_order: 4
has_children: true
---

# Route C: working on Levante

Working next to the data on Levante needs a DKRZ user account that is a member of project bm1344. Register at the DKRZ user portal ([luv.dkrz.de](https://luv.dkrz.de)), then request membership of bm1344 and let me know so the request can be approved.

On Levante, all EERIE model output is reached through the intake catalogue rather than by file path:

```python
import intake
cat = intake.open_catalog(
    "https://raw.githubusercontent.com/eerie-project/intake_catalogues/main/eerie.yaml")

# Entries can be addressed with a dotted path from the top level
ds = cat["dkrz.disk.model-output.icon-esm-er.hist-1950.v20240618.ocean.gr025.2d_monthly_mean"].to_dask()

# Browse one level at a time when you are unsure of a key
list(cat["dkrz.disk.model-output.ifs-fesom2-sr.hist-1950.v20240304"])
```

Sub-catalogues under `dkrz`:

| Entry | Use |
| --- | --- |
| `dkrz.disk.model-output` | Raw output on Levante disk, member r1 of each model |
| `dkrz.disk.phase2-model-output` | Additional ensemble members (r2, r3) |
| `dkrz.disk.CMOR` | CMOR-standardised tables (Amon, Omon, SImon), the files that go to ESGF |
| `dkrz.cloud` | Same datasets streamed from the km-scale cloud, for use outside Levante |
| `dkrz.archive` | Data on tape only |

The exact entries for each model are on the [Catalogue keys](catalogue-keys) page. Background: [easy.gems: How to work with EERIE data on DKRZ](https://easy.gems.dkrz.de/simulations/EERIE/eerie_data-access_dkrz.html).
