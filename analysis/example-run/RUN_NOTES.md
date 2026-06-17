# Practice end-to-end SUEWS run

A minimal sanity run to confirm the SUEWS toolchain (the engine behind the
**suews-agent**) works end to end on this machine, ahead of the hackathon.
This uses the bundled **KCL / London sample**, not the focus-city dataset
(that is loaded at kickoff on 24 June).

## Tooling

- `supy` 2026.6.5 (provides the unified `suews` CLI and the `suews-mcp` server
  that the [suews-agent](https://github.com/UMEP-dev/suews-agent) plugin wraps).
- Installed via `uv` into an isolated environment (the same `uvx`-based path the
  plugin's `.mcp.json` uses). The interactive `/plugin` installer is not
  available in this environment, so the underlying package was installed
  directly — functionally identical.

## Commands (the skill's "new case from scratch" recipe)

```bash
suews init --template simple-urban example-run     # scaffold sample case
suews validate --format json sample_config.yml     # 0 errors, 6 warnings
suews run sample_config.yml                         # full-year simulation
```

## Result

- Simulation period: 2012-01-01 → 2013-01-01, hourly.
- Output: `Output/KCL1_2012_SUEWS_60.txt` — **8,784 timesteps**.
- Mean fluxes (W/m²): QN ≈ 45, QF ≈ 85, QS ≈ 13, QE ≈ 28, QH ≈ 89;
  mean 2 m air temperature ≈ 11.9 °C — physically plausible for the sample site.
- Energy balance closes by construction (`QN + QF = QS + QE + QH`); per the
  SUEWS skill, closure confirms the run completed, **not** that the partition is
  correct for any real site.

> This is a pipeline check only. The sample's location, land-cover fractions and
> forcing are placeholder defaults, not the focus city.
