# Fine Wine Diversification Report — Follow-Up Brief (Agent Prompt)

## Purpose

Apply the following changes and fixes to the existing **correlation-diversification** project. Base requirements, data sources, and report goals are in the **original brief**: `docs/requirements/wine-divsersification-report-original.md`. **Read that first** for full context; this document lists only the follow-up tasks.

**Prerequisites:** Treat the project as already started. Verify existing notebooks run locally and that all images are saved under `projects/correlation-diversification/images`.

---

## Environment: use uv (reproducible runs)

**Use [uv](https://docs.astral.sh/uv/) for Python and dependencies.** This keeps environments identical for you and for agents and avoids "works on my machine" failures.

- From repo root: `uv sync` to create/update the venv and install dependencies (including dev / Jupyter).
- Run notebooks: use the project interpreter (e.g. select the venv in your IDE, or `uv run jupyter notebook`).
- Do **not** use `pip install -r requirements.txt`; the project is managed with `pyproject.toml` and `uv.lock`. Any new dependency must be added with `uv add <package>` so the lockfile stays in sync.

---

## 0. Major change: wine price indices (overrides original)

**Do not** build your own trade-based indices at the wine label level. Use pre-made **latent trade price** data at LWIN11 (wine–vintage) level to derive LWIN7 (wine label) level indices.

- **Source:** `dev_winefi_raf.ml.ml_latent_prices_historic`
- **Meaning:** `price_latent` is an MCMC-modelled latent trade price series (state-space model with Gibbs sampler and Kalman filtering/smoothing) that turns sparse trade data into continuous time series.

```sql
SELECT
  lwin11,
  yyyymm,
  price_latent,
  region
FROM dev_winefi_raf.ml.ml_latent_prices_historic
```

Use this table to build LWIN7-level indices instead of computing them from raw trades.

---

## 1. Equity returns: use total return, not price only

Replace all equity index comparisons with **accumulator** (or equivalent) total-return series—e.g. accumulator ETFs or total-return indices—so dividends are included. All return comparisons must use **total returns**, not price-only series.

---

## 2. Plots and image export

- Confirm **every** plot referenced in either report is saved as a PNG.
- All images must live under: `report-for-me/projects/correlation-diversification/images` (and subdirs as needed, e.g. `images/currency/`).
- Fix any references that point to missing files.

---

## 3. Bug fix: missing image

The file `../images/currency/05_brexit_equity_wine_comparison.png` is referenced but not saved. Find the notebook that produces this plot and fix the export so the PNG is written to the correct path under `projects/correlation-diversification/images`.

---

## 4. External report: no LWIN or internal DB references

- **External report:** Do not reference LWIN codes (e.g. LWIN7, LWIN11) or any internal database objects (e.g. MotherDuck, `winefi.ml.ml_unified_trades_tbvm`). Use wine names and high-level descriptions only.
- **Internal report:** LWIN and database references are allowed.

---

## 5. Plot styling: colour palette

Fix colours in the figure saved as `04b_covid_multiwindow_comparison.png` so they match the standard project palette:

- `#9437ff` (purple), `#83D483` (mantis), `#FFD166` (sunglow), `#F78C6B` (coral), `#4D87D0` (blue), `#EF476F` (red), `#06D6A0` (emerald), `#C23FB7` (pink/purple), `#4A4A68` (slate).

---

## 6. Heterogeneity section: filters and wine choice

**Section:** "The Heterogeneity Insight: Not All Wine Diversifies Equally"

- Apply a **1980 vintage minimum** filter for trades included in this analysis.
- In the **3-wine comparison** at the start of the section:
  - **Remove:** Dom Pérignon (LWIN7: 1082656, all vintages).
  - **Add instead:** Domaine de la Romanée-Conti, Echezeaux Grand Cru (LWIN7: 1028658).

---

## 7. GFC deep-dive: rebase to 100

In **"GFC Deep-Dive: Six Additional High-Profile Wines"**, the rebasing to 100 at the start of the plotted period is not working. Fix the chart so each series is rebased to 100 at the start of the plotted window.

---

## 8. Liquidity section: simplify

The plot and analysis in **"Liquidity: An Honest Assessment"** are too complex. Redo with a simpler, more approachable explanation and visual.

---

## Completion checklist

- [ ] Latent price source used for LWIN7 indices; no custom trade-based index built at label level.
- [ ] Equity comparisons use total-return (accumulator) series.
- [ ] Every plot referenced in either report is saved as a PNG under `projects/correlation-diversification/images`.
- [ ] `05_brexit_equity_wine_comparison.png` is generated and saved; bug fixed.
- [ ] External report contains no LWIN or internal DB references.
- [ ] `04b_covid_multiwindow_comparison.png` uses the standard palette.
- [ ] Heterogeneity: 1980 vintage minimum applied; DRC Echezeaux (1028658) in 3-wine comparison instead of Dom Pérignon (1082656).
- [ ] GFC deep-dive chart correctly rebased to 100.
- [ ] Liquidity section simplified.
- [ ] All notebooks run locally when executed in order.
