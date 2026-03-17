# Fine Wine Diversification: Analysis & Report Brief

## Objective

Produce two reports (with supporting analysis notebooks) exploring whether fine wine is a good portfolio diversifier, with emphasis on heterogeneity within fine wine and why Liv-ex index-based analysis alone is misleading.

### Source material

| What | Path |
|---|---|
| WineFi's original diversification report | `projects/correlation-diversification/winefi-diversification-report.md` |
| Third-party rebuttals to analyse | `projects/correlation-diversification/rebuttals-to-analyse.md` |

---

## Deliverables

### Report 1 — Internal

- Audience: WineFi team only.
- Purpose: balanced, nuanced analysis of every point raised in the rebuttals. What did they get right? What did they get wrong? What does the data say?
- LWIN codes and database references are fine here.

### Report 2 — External (website / client-facing)

- Audience: WineFi clients and public.
- Purpose: indirect rebuttal (never name or reference the rebuttal authors). Official company stance on fine wine as a diversifier and its relative performance vs other asset classes, especially in downturns.
- Tone: accessible, well-sourced, not overly technical, but rigorous enough to withstand counter-arguments.
- **No LWIN codes, no database table names, no internal tooling references.** Use wine names and plain descriptions only.
- Keep plots simple and clean.

### Shared requirements for both reports

- Format: Markdown files with images referenced inline.
- Every plot must be saved as a PNG under `projects/correlation-diversification/images/` (subdirs allowed, e.g. `images/currency/`).
- Every image must have a caption that explains the data, fits within the image, and has no overlapping text or titles.
- ALL ARGUMENTS MUST CRITIQUED FOR FACTUAL ACCURACY

---

## Central Thesis to Explore

> "Even if Liv-ex indices have shown periods of correlation with equities, certain wines do not — asset selection is key."

Key points:

1. **Liv-ex indices are biased.** The Liv-ex 100 and 1000 track the *most liquid* fine wines. These are the most responsive to broader market moves. Using them as a proxy for "the fine wine market" is convenient but not representative.
2. **Fine wine is highly heterogeneous.** Correlation with equities, and overall returns, vary by region, producer, vintage, and liquidity. Broader indices (Liv-ex 1000) and regional indices (e.g. Burgundy 150) have historically shown lower equity correlation than the Liv-ex 100.
3. **Static correlations are misleading.** Illiquidity, appraisal-based pricing, and non-synchronous trading smooth wine prices and bias correlations downward. Rolling correlations give a more realistic (low but unstable) picture.
4. **Resilience during stress.** In the 2008 crisis the Liv-ex 100 fell ~17% vs S&P 500 ~36%, recovering to prior highs by 2010 (equities: 2013). The question is not "do wine prices fall?" but "by how much relative to other assets, and how hard is it to exit?"
5. **Liquidity vs price.** Reduced trading volume does not necessarily mean lower transaction prices. Sellers holding firm on reserve prices in a downturn is a feature, not a bug.
6. **Currency matters.** GBP is the baseline currency for fine wine pricing. Changes in sterling relative to USD and EUR are a major driver of apparent price moves — just as currency is a consideration when investing in international property. Dismissing the currency dimension of wine investment is unjustified.
7. **Heterogeneity case studies.** Show specific wines that were resilient during downturns (e.g. Salon — LWIN7 `1807626`, Dom Pérignon — `1082656`) vs those that fell sharply (e.g. Lafite — `1011872`). Analyse what this says about selection-dependent diversification.
8. **Burgundy 150 in 2008.** Compare its drawdown to S&P 500 (currency-adjusted) and FTSE 100.
9. **Fine wine is not a guaranteed safe haven.** We are not claiming that. The claim is that disciplined, data-led selection can deliver low-correlation diversification benefits.


**This should be our public stance more or less:**
Fine wine shouldn’t be viewed as a perfect hedge, but it can play a valuable role as a structural diversifier. While liquidity and price discovery can tighten in downturns, transaction prices tend to be more robust than equities and ultimately - as a tangible asset with its own demand drivers - fine wine can help build a more resilient portfolio that isn’t fully tied to traditional financial cycles.
---

## Analysis Approach

### Notebooks

Write across multiple notebooks, each tightly focused on one topic. You define the structure of `projects/correlation-diversification/`. Save important aggregated datasets alongside images.

### Time period

~2000 onwards (when Liv-ex indices begin).

### Vintage filter

Only include wines with vintage >= 1980.

### Comparison assets

Use **total return** indices (wine yields no dividends, so price-only indices for equities would be an unfair comparison):

```python
import yfinance as yf

sp500 = yf.download("^SP500TR", start="2000-01-01")["Close"]   # S&P 500 Total Return
ftse  = yf.download("CUKX.L",  start="2000-01-01")["Close"]    # FTSE 100 Total Return (GBP)
gold  = yf.download("GC=F",    start="2000-01-01")["Close"]     # Gold
```

### Liv-ex index data

- Historical index returns: `projects/correlation-diversification/data/liv-ex_index_history.csv`
- Liv-ex 1000 components (2020–2025): `projects/correlation-diversification/data/25-02-11_lx1000_components_2020-2025.csv` (links to LWIN11s)
- Use heterogeneity *between* Liv-ex sub-indices to show that even among the most liquid wines, correlation to equities varies.

### Building custom indices from wine data

- Use latent price data (see database section below) as the source — do **not** re-model sparse trades.
- Use LWIN11 (wine-vintage) level data; derive LWIN7 (wine label) level indices as needed.
- **Index construction must account for new wines joining over time.** Only a wine's appreciation/depreciation *after* its first appearance should contribute to the index. Chain-link or similar methodology required.
- Move beyond Liv-ex indices: build your own trade-based indices and compare. Start with the most liquid LWIN7s/LWIN11s, then explore less liquid wines — acknowledging and addressing the liquidity-bias.
- Reference leading academic research on fine wine price tracking and sparse-asset index construction.

### Example wines to consider using (LWIN7 wine label level)
- Filter out all vintages older than 1980 firstly!
- Use these first 3: Salon (LWIN7: 1807626), Domaine de la Romanée-Conti, Échezeaux (LWIN7: 1028658) and Lafite (LWIN7: 1011872) as a core 3:
  - Salon (LWIN7: 1807626) 
  - Domaine de la Romanée-Conti, Échezeaux (LWIN7: 1028658)
  - Lafite (LWIN7: 1011872).
- Others to consider especiallty when showing heterogeneity:
  - Soldera Case Basse, Toscana	(1226504)
  - Jacques Selosse, Millesime	(1226155)
  - Domaine Armand Rousseau, Chambertin Grand Cru	(1057005)
  - Sassicaia, Tenuta San Guido, Bolgheri	(1102037)
  - Masseto, Toscana	(1160743)
  - Domainen Arnoux-Lachaux (1018783)
  - Chateau Figeac Premier Grand Cru (1009769)


---

## Environment & Dependencies

**Use [uv](https://docs.astral.sh/uv/) — no pip, no `requirements.txt`.**

```bash
uv sync                        # create/update venv, install all deps
uv add <package>               # add a new dependency (keeps lockfile in sync)
uv run jupyter notebook        # run notebooks with project interpreter
```

The project is managed with `pyproject.toml` and `uv.lock`.

---

## Database Connection (MotherDuck)

```python
import duckdb
conn = duckdb.connect("md:")   # picks up motherduck_token from env
```

The `motherduck_token` env var is pre-set. Always use fully qualified table names (`database.schema.table`).

**First step in any notebook:** run the schema query below to discover columns before writing analysis queries. Never assume column names.

```python
df = conn.execute("""
    SELECT column_name, data_type
    FROM information_schema.columns
    WHERE table_schema = 'mrt'
      AND table_catalog = 'winefi'
      AND table_name = 'mrt_unified_trades_tbvm'
""").df()
```

```python
df_latent = conn.execute("""
    SELECT column_name, data_type
    FROM information_schema.columns
    WHERE table_schema = 'ml'
      AND table_catalog = 'dev_winefi_raf'
      AND table_name = 'ml_latent_prices_historic'
""").df()
```

### Performance rules

- Never `SELECT *` without `LIMIT` — tables have tens of millions of rows.
- Push aggregation and filtering into SQL; only pull aggregated results into pandas.
- Use `LIMIT` during development; remove for final analysis.

### LWIN key system

All database joins depend on understanding LWINs:

| Key | Name | Digits | Description | Example |
|-----|------|--------|-------------|---------|
| 1 | LWIN7 | 7 | Wine label (not producer) | `1011872` (Lafite) |
| 2 | LWIN11 | 11 | LWIN7 + vintage year | `10118722010` |
| 3 | LWIN16 | 16 | LWIN11 + bottle size (zero-padded) | `1011872201000750` |
| 4 | LWIN18 | 18 | LWIN11 + pack size + bottle size (zero-padded) | `101187220101200750` |

### Tables

**a. Latent prices (continuous time series)**

```
dev_winefi_raf.ml.ml_latent_prices_historic
```

| Column | Description |
|--------|-------------|
| `lwin11` | Wine-vintage identifier |
| `yyyymm` | Year-month |
| `price_latent` | MCMC-modelled latent trade price (state-space model, Gibbs sampler, Kalman filtering/smoothing) |
| `region` | Wine region |

This is already a continuous time series derived from sparse trades. **Use this for all return calculations and custom index building.** Do not re-model sparse trades yourself.

**b. Unified trades (raw transactions)**

```
winefi.ml.ml_unified_trades_tbvm
```

Cleaned historic trade data (outliers removed, sources unified). Use for analysing trade quantity, value, and volume patterns — not for return calculations.

### Currency

All database prices are in **GBP** unless stated otherwise. Pay careful attention to currency at all times when comparing to USD-denominated assets.

---

## Plot Palette

Use only these colours across all notebooks and reports:

| Hex | Name |
|-----|------|
| `#9437ff` | Purple |
| `#83D483` | Mantis |
| `#FFD166` | Sunglow |
| `#F78C6B` | Coral |
| `#4D87D0` | Blue |
| `#EF476F` | Red |
| `#06D6A0` | Emerald |
| `#C23FB7` | Pink/Purple |
| `#4A4A68` | Slate |

---

## Completion Checklist

- [ ] **Internal report** (Markdown): addresses each rebuttal point with data-backed analysis.
- [ ] **External report** (Markdown): client-ready, no internal references, well-sourced, simple plots.
- [ ] All images saved as PNGs under `projects/correlation-diversification/images/`.
- [ ] Every image has a non-overlapping caption explaining the data.
- [ ] All image file references in reports point to existing files.
- [ ] All factual claims triple-checked for accuracy.
- [ ] All images committed to git.
- [ ] Notebooks are segmented by topic and clearly named.
