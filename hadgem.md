---
title: HadGEM3-GC5E
nav_order: 6
---

# HadGEM3-GC5E (Met Office)

The DKRZ cloud holds monthly near-surface atmosphere fields for `HadGEM3-GC5E-HH`, on a regular 0.25° grid (721 x 1440, with `lat` and `lon`) despite the `gr1` label. The same datasets exist for `HadGEM3-GC5E-LL`; replace `HH` with `LL` in the ids. Checked on the DKRZ cloud on 12 October 2026.

**Dataset ids:** `HadGEM3-GC5E-HH.<exp>.v20250409.gr1.<table>`

| Experiment | Coverage |
| --- | --- |
| `historical` | 1850-2014 |
| `ssp245` | 2015-2099 |

| Table | Content | Variables |
| --- | --- | --- |
| `Amon` | Monthly means | `tas`, `pr`, `clt`, `sfcWind`, `uas`, `vas` |
| `AmonExtremes` | Monthly extremes | `tasmax`, `tasmin` |

```python
ds = open_eerie("HadGEM3-GC5E-HH.historical.v20250409.gr1.Amon")
```

No ocean or higher-frequency HadGEM3 data is on the DKRZ cloud; HadGEM3 ocean output is published at CEDA and on ESGF.
