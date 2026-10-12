---
title: HadGEM3-GC5E
nav_order: 6
---

# HadGEM3-GC5E (Met Office)

Two resolutions are available: `HadGEM3-GC5E-HH` and `HadGEM3-GC5E-LL`; this page uses HH, and LL ids follow the same pattern. The DKRZ cloud holds monthly atmosphere fields on a regular grid (`gr1`).

**Dataset ids:** `HadGEM3-GC5E-HH.<exp>.v20250409.gr1.<table>`, with `<exp>` = `historical` or `ssp245`

| Table | Content | Example variables |
| --- | --- | --- |
| `Amon` | Monthly atmosphere | `tas`, `pr`, `clt`, `sfcWind`, `uas`, `vas` |
| `AmonExtremes` | Monthly extremes | |

```python
ds = open_eerie("HadGEM3-GC5E-HH.historical.v20250409.gr1.Amon")
```

HadGEM3 ocean output is published at CEDA and on ESGF.
