# SUEWS Hackathon — Practice Setup

This is a **practice repository** for the [SUEWS Community Hackathon](https://community.suews.io/t/welcome-to-the-suews-community-hackathon-24-june/69)
(24 June 2026, UCL East), created from the
[`UMEP-dev/suews-hackathon-template`](https://github.com/UMEP-dev/suews-hackathon-template).
It exists to confirm the full pipeline works ahead of the day — repo, SUEWS
toolchain, and this public GitHub Pages site. The real focus-city analysis is
built on the day, when the dataset and heat-to-risk bridge are released.

## Setup check — passed ✅

| Step | Result |
|------|--------|
| Repo created from template | ✅ public, cloned locally |
| SUEWS toolchain installed | ✅ `supy` 2026.6.5 (the engine the [suews-agent](https://github.com/UMEP-dev/suews-agent) wraps) |
| End-to-end sample run | ✅ full-year run, 8,784 hourly timesteps |
| GitHub Pages | ✅ this page |

## The end-to-end run

Using the bundled **KCL / London sample** (a placeholder, *not* the focus
city), the standard `suews init → validate → run` recipe produced a full year
(2012) of hourly output. Mean surface energy-balance fluxes:

| Term | Mean (W/m²) | |
|------|------------|---|
| `QN` | 45 | net radiation |
| `QF` | 85 | anthropogenic heat |
| `QS` | 13 | storage heat |
| `QE` | 28 | latent heat |
| `QH` | 89 | sensible heat (residual) |

Mean 2 m air temperature ≈ **11.9 °C** — physically plausible for the sample
site. Details and commands: [`analysis/example-run/RUN_NOTES.md`](https://github.com/geunhyekim2025/suews-hackathon-practice/blob/main/analysis/example-run/RUN_NOTES.md).

> The energy balance closes by construction; closure confirms the run
> completed, **not** that the partition is correct for any real site.

## On the day, this page will tell the story

- The question asked of the focus city.
- How SUEWS was configured via the suews-agent.
- The heat-hazard result and the socio-economic risk indicator.
- Where the hazard-to-indicator bridge holds, and where it breaks.

> Judged on **Policy relevance & honest bridging** and **Presentation quality**. It must remain public.

## Citing SUEWS

- Järvi, L., Grimmond, C.S.B. & Christen, A. (2011). *Journal of Hydrology*, 411(3–4), 219–237. https://doi.org/10.1016/j.jhydrol.2011.10.001
- Ward, H.C., Kotthaus, S., Järvi, L. & Grimmond, C.S.B. (2016). *Urban Climate*, 18, 1–32. https://doi.org/10.1016/j.uclim.2016.05.001
