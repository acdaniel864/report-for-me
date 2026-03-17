# Internal Rebuttal Analysis: Fine Wine as a Portfolio Diversifier

**Audience:** WineFi team only
**Date:** 2026-03-17
**Purpose:** Balanced, data-backed analysis of each third-party rebuttal argument. What did they get right? What did they get wrong? What does the data say?

---

## Executive Summary

The rebuttals from Wine Bourse and Sara Danese raise six substantive arguments, most of which converge on three overlapping themes: (1) GBP currency effects inflate apparent fine wine returns; (2) illiquidity makes fine wine dangerous to hold in crises; and (3) Liv-ex indices are a misleading benchmark. A rigorous assessment finds that **arguments 1, 4, and 6 contain genuine merit and must be acknowledged** — the currency dimension is real, and Liv-ex indices *are* biased benchmarks. However, the critics over-reach in two critical respects: first, acknowledging a currency component does not eliminate diversification value (every international asset carries currency exposure); and second, the very weakness of Liv-ex as a benchmark — its over-representation of liquid, market-sensitive wines — *supports* WineFi's core heterogeneity thesis. Arguments 2, 3, and 5 are weaker: illiquidity ≠ price collapse, the mis-selling argument targets bad actors rather than the asset class, and geopolitical risk affects wine *trade* more than secondary-market prices. The internal conclusion is clear: fine wine, when selected with discipline, remains a structurally sound diversifier. It is not a guaranteed safe haven, and we should never present it as one.

---

## Thesis Points Covered in This Report

The nine key thesis points from the requirements brief (`docs/requirements/wine-divsersification-report.md`) are addressed throughout. For quick reference:

| # | Point | Section |
|---|-------|---------|
| 1 | Liv-ex indices are biased toward liquid wines | Rebuttal 6 |
| 2 | Fine wine is highly heterogeneous | Rebuttal 6 + Rebuttal 2 |
| 3 | Static correlations are misleading | Rebuttal 6 |
| 4 | Resilience during stress (GFC, COVID, 2022) | Rebuttal 2 |
| 5 | Reduced trading volume ≠ lower transaction prices | Rebuttal 2 |
| 6 | Currency matters and should be disclosed | Rebuttals 1 & 4 |
| 7 | Heterogeneity case studies (Salon, DRC, Lafite) | Rebuttal 2 + Rebuttal 6 |
| 8 | Burgundy 150 in 2008 | Rebuttal 2 |
| 9 | Fine wine is not a guaranteed safe haven | All sections |

---

## Rebuttal 1: GBP Currency Illusion Inflates Apparent Returns

**Source:** Wine Bourse (LinkedIn post & blog), Sara Danese (LinkedIn post & blog)

**The claim:** Fine wine indices are quoted in GBP, but the underlying wines are overwhelmingly EUR-denominated assets. During periods of GBP weakness (2008, Brexit 2016, COVID), apparent index outperformance is largely a reflection of an embedded long-EUR/short-GBP position, not genuine asset resilience.

**Data cited by critics:**
- Liv-ex 1000 up 22% in GBP in 2016 vs only 5% in EUR — the 17pp gap was sterling depreciation
- Over 20 years the main Liv-ex index returned 3.6× in GBP, 3× in EUR, 2.6× in USD

---

### What they got right

The critics are factually correct on the numbers. The 2016 Brexit example is well-documented: EUR/GBP moved approximately 15–17% in a single year, and this mechanically flatters any GBP-denominated asset that is priced in EUR. The structural relationship `GBP return ≈ EUR asset return + ΔEUR/GBP` is arithmetically sound. Any fair comparison of fine wine to other asset classes must adjust for this currency effect — or at minimum, disclose it explicitly.

The cumulative return gap (3.6× GBP vs 2.6× USD over 20 years) is significant and should not be hand-waved away. For a USD-based investor, approximately 27% of the headline GBP return evaporates after currency adjustment.

![Cumulative returns of the Liv-ex 1000 expressed in GBP, USD, and EUR from 2004 to 2024. The GBP line sits persistently above the USD and EUR lines, reflecting embedded currency tailwinds during periods of sterling weakness.](../images/currency/01_cumulative_returns_gbp_usd_eur.png)

![Annual return decomposition showing the wine price return component and the FX contribution for each calendar year. Crisis years (2008, 2016) show large positive FX bars coinciding with GBP weakness.](../images/currency/02_annual_return_decomposition_price_vs_fx.png)

---

### What they got wrong

**The critics treat currency as a unique flaw in wine investment rather than a universal feature of international investing.** Every investor buying US equities, European real estate, or Japanese bonds takes on currency risk. A GBP-based investor in the S&P 500 Total Return index saw approximately 8pp of return eroded when the dollar weakened against sterling — a fact the critics themselves acknowledge in Rebuttal 4 (the S&P 500 analogy). Holding wine to a higher standard than equities is inconsistent.

**The critics conflate GBP reporting with GBP-denominated pricing.** Fine wine transacts on Liv-ex in GBP, but ultimate demand comes from global buyers. When sterling weakens, foreign buyers gain purchasing power in Liv-ex's GBP-priced market — which *supports* transaction prices. This is a feature: wine benefits from international demand diversification in a way that purely domestically priced assets do not. When sterling strengthens, this tailwind reverses — but so does the tailwind on any internationally priced asset (crude oil, gold, copper) quoted in USD.

**Currency does not eliminate diversification.** Even after full USD adjustment, the Liv-ex 1000 delivered 2.6× over 20 years — a positive real return — with demonstrated periods of price resilience during equity drawdowns. The diversification thesis does not require fine wine to be a currency-neutral asset; it requires it to be imperfectly correlated with equities, which the data supports (see Rebuttal 6).

---

### What the data says

![Wine price returns vs S&P 500 returns, both expressed in a common currency (GBP and USD). Even after FX adjustment, the wine price component shows resilience during the GFC and 2022 equity bear market.](../images/currency/04_wine_vs_sp500_fx_adjusted.png)

![Impact of sterling/euro and sterling/dollar moves on fine wine returns during three major crises: GFC (2008), Brexit (2016), and COVID (2020). Crisis periods show large FX contributions in GBP terms.](../images/currency/03_crisis_periods_gfc_covid_fx_impact.png)

The GFC analysis is instructive even after currency adjustment. The Liv-ex 100 fell approximately 17% from September 2008 to February 2009, versus the S&P 500 falling 36% over the same window. Even stripping the positive GBP/EUR FX move, the *underlying wine price* fell significantly less than equities. The diversification benefit in GFC was not purely a currency illusion — the wine asset itself was more resilient.

**Internal conclusion:** Accept the critics' currency point fully. All future WineFi analysis should present returns in multiple currencies (GBP, USD, EUR) and decompose FX contribution explicitly. Do not present GBP-only returns without this context. But currency exposure is not unique to wine, does not eliminate the asset class's diversification value, and should be reframed as a factor to manage rather than a fatal flaw.

---

## Rebuttal 2: Fine Wine is Too Illiquid and Risky to Hold During Crises

**Source:** Wine Bourse (LinkedIn post & blog), Sara Danese (blog)

**The claim:** Fine wine is highly illiquid with wide bid-offer spreads, non-income-generating, and traded in a largely unregulated environment. These are the opposite of what investors want during market stress. Fine wine is "the polar opposite of where people should be investing during times of crisis."

---

### What they got right

Liquidity genuinely contracts during risk-off environments. This is an empirical fact, and sellers who *need* to liquidate during a market crisis will face wider spreads and potentially longer time-to-execution than in normal conditions. This is a real risk that must be disclosed to investors.

The Oeno failure, referenced in Rebuttal 3, is a reminder that wine storage vehicles can have idiosyncratic structural risks. Investors must distinguish between physical fine wine (stored in bond) versus wine investment funds or platforms with their own solvency and operational risks.

---

### What they got wrong

**The critics conflate reduced trading volume with lower transaction prices — these are different things.** In a physical asset market like fine wine, sellers facing a downturn can simply choose *not to sell*. Unlike equities (where a fund facing redemptions must sell into the market), a direct owner of physical wine in bond can hold reserve prices. The bid-offer spread widening observed in crises reflects fewer willing sellers at current bids, not necessarily distressed selling at lower prices. This is actually an advantage for long-term holders: wine prices are "sticky downward" in a way that mark-to-market equity portfolios are not.

**The GFC and subsequent stress tests directly contradict the "polar opposite" claim.** The empirical record is unambiguous:

- **GFC (September 2008 – February 2009):** S&P 500 fell 36%, Liv-ex 100 fell 17%. The Liv-ex 100 returned to prior highs by early 2010; the S&P 500 did not recover until 2013.
- **COVID correction (January–March 2020):** S&P 500 fell 21%, Liv-ex 100 fell just 1%. Given the Liv-ex mid-price is bid-weighted and the correction was short-lived, this is a meaningful data point even if the window is brief.
- **2022 equity bear market (December 2021 – September 2022):** S&P 500 fell 24%, gold fell 9%, Liv-ex 100 *rose* 9%.

![Drawdown comparison across GFC: S&P 500 total return, FTSE 100, Liv-ex 100, and gold, indexed to September 2008. Wine's shallower drawdown and earlier recovery are clearly visible.](../images/correlation/04_gfc_drawdown_comparison.png)

The COVID window also merits careful interpretation:

![Multi-window analysis of the COVID correction, comparing wine and equity drawdowns across different lookback horizons. The Liv-ex 100's near-zero response at the 1-month window reflects a combination of pricing methodology and genuine bid resilience.](../images/correlation/04b_covid_multiwindow_comparison.png)

**The Burgundy 150 is even more instructive.** During the GFC, the Burgundy 150 showed a materially smaller drawdown than the Liv-ex 100 itself:

![Burgundy 150 index vs S&P 500 and FTSE 100 during 2007–2010, showing the Burgundy index's shallower drawdown and faster recovery.](../images/correlation/05_burgundy150_vs_sp500_ftse_2008.png)

![Bar chart comparing drawdown depths for Burgundy 150, Liv-ex 100, S&P 500, and FTSE 100 during GFC. Burgundy 150 bar is substantially smaller.](../images/correlation/06_burgundy150_gfc_bar_comparison.png)

**Heterogeneity is the key.** Even within the highly liquid DRC range alone, the spread between top and bottom performing wines from 2021 to 2026 was 52% on a mean-return basis. The choice of *which* wines to hold is the dominant variable. Wines like Salon (LWIN7: `1807626`) and DRC Échezeaux (LWIN7: `1028658`) have historically shown different drawdown profiles versus Lafite (LWIN7: `1011872`), which is more liquid, more widely traded, and more responsive to macro sentiment swings. Broadly, higher-liquidity wines (Lafite, First Growths in general) are more correlated with macro conditions; lower-liquidity, reputation-driven wines (Salon, niche Burgundy) tend to be more stable and less responsive to financial cycles.

---

### What the data says

Rolling correlation analysis confirms that fine wine is *not* persistently correlated with equities. The 1-year and 2-year rolling correlations fluctuate widely, including extended periods of near-zero or negative correlation:

![1-year rolling correlation of Liv-ex 100 with S&P 500, FTSE 100, Nikkei 225, gold, and MSCI World from 2004 to 2024. Correlation is low and unstable.](../images/correlation/02_rolling_correlations_vs_sp500.png)

The 3-year rolling correlation peaked above 0.5 only once — at the height of the 2008 financial crisis — and fell sharply thereafter. By contrast, rolling correlations between the S&P 500 and commodities, Nikkei, Hang Seng, or corporate bonds persistently hover at or above +0.5. Fine wine is a genuine outlier in this respect.

**Internal conclusion:** Illiquidity is a real risk and must be disclosed. But "illiquid" does not mean "price-collapsing" — price stickiness in downturns is partly a consequence of illiquidity, and the empirical record shows fine wine prices holding up far better than equities during major drawdowns. The "polar opposite of where people should be investing" claim is not supported by the data. Reframe this internally: illiquidity is a risk to *exit* speed, not necessarily a risk to *capital preservation*.

---

## Rebuttal 3: Diversification Claims Constitute Mis-Selling

**Source:** Wine Bourse (LinkedIn post & blog)

**The claim:** Presenting fine wine as a diversification play using GBP-denominated index charts during crisis periods is misleading. Because wine is unregulated, these practices go unchecked. The Oeno failure (investors lost 80%+ of capital) is cited as evidence.

---

### What they got right

There *have* been bad actors in the fine wine investment space. The Oeno collapse is real, and investors who relied on opaque fund structures or platforms without segregated custody did lose substantial capital. Regulatory gaps exist: fine wine is not a regulated financial product in the UK, and marketing practices that would be restricted under FCA rules are not subject to the same oversight.

If GBP-denominated charts are shown *without* disclosing the currency component, that is intellectually dishonest regardless of regulatory status.

---

### What they got wrong

**This argument is about bad actors in the industry, not about the underlying asset class.** Funds and platforms can fail without the asset itself being fraudulent or unsuitable. An investor holding physical wine in a regulated, segregated bond warehouse owns a real, tangible asset. The Oeno failure was a fund structure failure, not evidence that fine wine prices themselves are unreliable.

The critics use a single high-profile failure to impugn an entire asset class. This is equivalent to arguing that property investment is "mis-selling" because some buy-to-let overleveraging schemes failed, or that gold investment is "mis-selling" because some unregulated bullion schemes collapsed.

**The mis-selling argument also proves too much.** If using a GBP-denominated index chart is mis-selling, then so is using any single-currency presentation of an international asset. This standard would apply equally to presentations of US equities in USD to UK investors, or EUR-denominated European property returns.

---

### What the data says

This argument does not turn on data — it turns on industry conduct. The relevant WineFi response is:

1. **We use transparent, multi-currency analysis** (as now committed to internally following Rebuttal 1).
2. **We hold client assets in segregated, bonded storage** — the structure that failed in Oeno is not our structure.
3. **We advocate for better industry standards**, and we acknowledge that some operators in this space have provided misleading presentations.

**Internal conclusion:** Acknowledge the industry conduct issue without accepting that it taints WineFi or the asset class. Move past this argument quickly — it does not engage with the fundamental question of whether fine wine provides diversification. Our strongest response is transparency in our own analysis and communications.

---

## Rebuttal 4: Currency Exposure is a Risk Factor, Not a Feature

**Source:** Sara Danese (LinkedIn post & blog)

**The claim:** Investors holding wine are implicitly taking a currency position (long EUR, short their home currency). This is a real risk that should be understood and disclosed, not presented as a diversification benefit. The same currency dynamics that flatter GBP returns when sterling weakens will hurt returns when sterling strengthens.

**Data cited:** ~45% of Liv-ex trading is European, ~40% UK-based. Wine production inputs (labour, glass, cork, shipping) priced in EUR.

---

### What they got right

This argument is largely a restatement of Rebuttal 1, and the same concessions apply. Currency exposure is genuine, bidirectional, and should be disclosed. The input cost point is correct: as a primarily French and Italian product, fine wine's production economics are EUR-denominated, and that cost base flows through to pricing. The S&P 500 analogy is fair — a GBP investor buying US equities does take a USD/GBP bet.

The Danese breakdown of Liv-ex trading by geography (~45% European, ~40% UK) is directionally correct and useful context: European buyers are both the largest category of sellers and a significant portion of buyers. This means EUR/GBP and EUR/USD movements are structurally important to secondary market pricing.

---

### What they got wrong

**Currency exposure is not uniquely problematic for wine.** The Danese analogy to US equities *confirms* this: a GBP investor in the S&P 500 is also taking a directional USD/GBP bet. The fact that wine has EUR exposure and equities have USD exposure does not make wine uniquely risky — it makes both *different* from purely domestic UK assets. For a diversified UK investor, that distinction is actually useful: holding assets with different currency exposures (EUR via wine, USD via equities, GBP via domestic bonds/property) reduces overall portfolio FX concentration.

**The critics argue that currency exposure should be "disclosed, not presented as a diversification benefit."** This is a false dichotomy. Currency diversification *can* be both disclosed *and* valued as a portfolio consideration. A UK investor who runs their household budget in GBP but sources diversification returns partially from EUR-exposed assets is not being misled — they are holding a more diversified currency basket, which reduces the correlation of their total portfolio with any single economic zone.

**The risk is symmetric, and the critics focus only on the downside.** GBP weakness flatters returns; GBP strength hurts them. This is equally true of any USD or EUR asset held by a GBP-based investor. The critics correctly identify the downside scenario but do not acknowledge the hedging function that EUR exposure provides for a GBP-based investor during periods of sterling weakness — which historically have coincided with UK equity underperformance.

![Historical GBP/USD and GBP/EUR exchange rates from 2004 to 2024, illustrating periods of significant sterling depreciation (2008, 2016, 2022) that provided currency tailwinds for GBP-based wine holders.](../images/currency/06_gbp_usd_eur_historical.png)

![Brexit event study: GBP/EUR rate, Liv-ex 1000 GBP return, and Liv-ex 1000 EUR return around the June 2016 Brexit vote. The 17pp divergence in 2016 calendar-year returns is clearly attributable to the FX move.](../images/currency/05_brexit_event_study.png)

---

### What the data says

The Brexit data is the critics' strongest case and should be accepted as such. The 17pp gap between GBP and EUR returns in 2016 was the FX move, not wine price appreciation. Over 20 years, the cumulative return of the main Liv-ex index was approximately 3.6× in GBP, 3× in EUR, and 2.6× in USD. These are real differences and should always be presented together.

However, even the 2.6× USD return represents a positive real return over 20 years — a period that includes the GFC, the Bordeaux correction (2011–2016), and the post-2023 wine market correction. The currency-adjusted return, while materially lower than the GBP headline, is not zero.

**Internal conclusion:** Fully accept this argument at the level of disclosure obligation. Always decompose FX and wine price return components in analysis. Reframe currency exposure not as a feature to market, but as a structural characteristic to explain — and, for UK investors, as a source of EUR diversification that reduces dependence on GBP-denominated returns.

---

## Rebuttal 5: Fine Wine is Exposed to Geopolitical and Trade Policy Risk

**Source:** Sara Danese (blog)

**The claim:** Wine is vulnerable to tariffs and trade wars because it is economically marginal but politically convenient as a pressure tool. This geopolitical exposure undermines claims that wine is a store of value or hedge against political shocks.

**Data cited:** China's ban on Australian wine; Trump 200% tariff threat on Champagne and subsequent 15% tariffs; France: wine and spirits are the country's 3rd largest export category; VOS Selections Supreme Court case challenging IEEPA tariff authority; USD weakened ~10% since tariff announcements, creating a double whammy for US buyers.

---

### What they got right

The Australian wine case is real and material: China imposed tariffs of 116–218% on Australian wine in 2020, effectively banning it from the Chinese market. Australian fine wine prices and export revenues collapsed. This is a genuine example of secondary-market prices for a specific wine region being structurally impaired by geopolitical action.

The US tariff environment is a live risk. A 200% tariff on Champagne, even as a threat, would materially reduce US buyer demand for French sparkling wine, affecting the secondary market price of names like Salon (LWIN7: `1807626`), Dom Pérignon (`1082656`), and Krug. The 15% tariff already in effect adds approximately 15pp to the landed cost of French wine in the US, reducing demand at the margin. For luxury goods, the price elasticity of demand at the top end is lower, but it is not zero.

The structural point about wine being a politically convenient target is valid: wine is a high-profile luxury export from countries (France, Italy) that run trade surpluses with the US, making it a natural lever in trade negotiations.

---

### What they got wrong

**The critics conflate the wine *trade* with the secondary wine *market*.** Tariffs primarily affect new import flows — the direct purchasing of wine by consumers and restaurants in the target country. The secondary market (Liv-ex, auction, merchant-to-merchant) is a different channel. A US tariff on French wine directly harms French producers' export revenues and US consumer purchasing, but its effect on secondary prices for bottles *already in* UK or European storage is indirect and second-order (operating through reduced US demand for future allocations, which feeds back to secondary prices with a lag).

**The Australian case, while real, is not representative.** Australian wine producers were highly dependent on a single export market (China), lacked geographic diversification of demand, and faced a targeted ban rather than a broad tariff. French and Italian fine wine is consumed across the US, UK, Asia, and Europe — this geographic diversification of the demand base makes a single-country tariff far less damaging than it was for Australia.

**The critics claim geopolitical risk "undermines" the store of value thesis.** But geopolitical risk exists for virtually all asset classes: equities are exposed to sanctions, supply chain disruptions, and regulatory change; bonds are exposed to government default and inflation policy; real estate is exposed to planning policy and rent controls. Geopolitical risk specific to wine trade does not make wine uniquely unsuitable as a store of value — it means it should be weighted appropriately within a diversified portfolio, not excluded entirely.

**The tariff risk is also partially self-limiting.** The IEEPA tariff authority is currently being challenged in the courts (VOS Selections case). More importantly, major French wine and spirits exports — Champagne, Cognac, Bordeaux — are significant contributors to French GDP and employment. Any administration threatening 200% tariffs will face substantial diplomatic counter-pressure, including retaliatory measures on US exports. This is not zero risk, but it is mitigated political economy.

---

### What the data says

There is no clean data on the direct secondary market impact of tariff announcements — the causal chain from tariff to secondary price is indirect and noisy. The Australian ban on Chinese trade did ultimately reduce Australian wine prices globally through reduced demand and excess supply, but this played out over 2–3 years rather than immediately.

For French and Italian fine wine, the relevant observation is that despite the Trump first-term trade war (2018–2019), which included 25% tariffs on European wines priced above $14/bottle, Liv-ex index performance was not materially disrupted. Wine priced above approximately £1,000/12×75cl case — the typical WineFi investment threshold — is above the price band most affected by ad valorem import tariffs at moderate levels.

**Internal conclusion:** Geopolitical and tariff risk is real, particularly for producers heavily exposed to a single market or price-sensitive US import demand. It should be disclosed as a risk factor. However, the risk is materially different from the systemic financial risk (correlation with equity drawdowns) that the broader diversification argument addresses, and it is mitigated by geographic demand diversification, the physical storage chain, and the relative inelasticity of ultra-premium wine demand. Do not dismiss this risk — but do not conflate it with a fundamental flaw in the asset class's diversification properties.

---

## Rebuttal 6: Caution Against Presenting Wine as a Safe Haven Based on Index History

**Source:** Sara Danese (blog)

**The claim:** Because of their construction (EUR asset quoted in GBP), Liv-ex indices can look like they are rallying during sterling weakness. Using these indices to argue that "wine is going up" during crises is misleading. Wine should not be presented as a scarce store of value or hedge based solely on historical Liv-ex performance.

**Key quote:** "Anyone who imports or exports wine knows this instinctively. In periods of political instability and currency stress, wine does not behave like a safe haven."

---

### What they got right

This argument is the most technically credible of the six, and it actually *supports* WineFi's core thesis rather than undermining it.

The critique of Liv-ex indices as benchmarks is largely valid:

1. **Survivorship and selection bias:** Liv-ex 100 and 1000 track the most actively traded wines — the most liquid segment of the market. These wines are disproportionately Bordeaux-weighted (historically) and more responsive to macro sentiment than the broader market.
2. **Appraisal-based pricing:** Liv-ex mid-prices are based on live bids and offers, not necessarily executed trades. This creates smoother, less volatile price series than actual transactions would produce — which biases static month-on-month correlations *downward* (understating true correlation) while also making rolling-window analysis less noisy.
3. **Non-synchronous trading:** Because many wines trade infrequently, price updates are staggered. This creates the appearance of low correlation with daily-priced assets even when true economic correlation is higher.

The critics are correct that using an uncorrected static correlation matrix as "proof" of wine's diversification is intellectually lazy and potentially misleading:

![Static correlation heatmap showing month-on-month correlations between Liv-ex 100 and major asset classes. Wine shows very low correlations — but this is partly an artefact of illiquidity and appraisal pricing.](../images/correlation/01_static_correlation_heatmap.png)

---

### What they got wrong — and why this rebuttal helps WineFi

**The critics identify a flaw in the benchmark and stop there. The correct response is to move beyond the benchmark — which is exactly what WineFi's analysis does.**

Rolling correlations are a more honest analytical tool than static snapshots. They show that even on a longer-window basis, fine wine's correlation with equities is low, unstable, and genuinely different from the persistent correlations seen in commodities, international equities, and corporate bonds:

![3-year rolling correlation of Liv-ex 100 with S&P 500, FTSE 100, and gold. The correlation peaked above 0.5 only once (2008 GFC) — a level routinely exceeded by the S&P 500's rolling correlation with commodities, Nikkei, Hang Seng, and corporate bonds.](../images/correlation/03_lx1000_rolling_correlation_all_assets.png)

But more importantly: **the critique of Liv-ex indices as biased toward liquid, market-sensitive wines is the foundation of WineFi's selection-based argument.** If the Liv-ex 100 is a poor proxy for "fine wine" because it over-represents liquid Bordeaux, then moving to the Liv-ex 1000 — which incorporates 900 additional wines — produces better diversification characteristics. And if we go beyond Liv-ex entirely to regional sub-indices (Burgundy 150), the diversification case is even stronger:

![Burgundy 150 vs S&P 500 and FTSE 100, 2007–2010. The Burgundy 150 showed a substantially smaller GFC drawdown than both equity indices.](../images/correlation/05_burgundy150_vs_sp500_ftse_2008.png)

**The logical extension of the critics' argument is that disciplined selection of less liquid, less market-sensitive wines offers better diversification than Liv-ex index exposure.** This is WineFi's thesis, stated precisely. The critics' strongest rebuttal inadvertently validates our core differentiator.

**On the "wine does not behave like a safe haven" claim:** We agree, and we should never present it as one. The relevant claim is not that wine *goes up* in crises (it does not, in general) — it is that it falls *less* than equities, recovers *faster*, and is driven by *different* underlying factors (vintage scarcity, producer reputation, consumption trends) that are structurally independent of the financial system. That is a low-correlation diversifier, not a safe haven.

---

### What the data says

The rolling correlation data makes the nuanced picture clear:

![1-year and 2-year rolling correlations of Liv-ex 100 vs S&P 500, gold, FTSE 100. Correlations are low, time-varying, and include extended periods of near-zero and negative correlation.](../images/correlation/02_rolling_correlations_vs_sp500.png)

The quarterly heterogeneity data is equally important: within any given quarter, approximately 20–30% of investment-grade wines rise in price, 20–30% fall, and the remainder are flat. This is not a market where everything moves together — selection matters enormously. Within DRC alone (e.g. Échezeaux, LWIN7: `1028658`), the spread between top and bottom half performers from 2021 to 2026 was 52% on a mean-return basis.

**Internal conclusion:** This is the critics' most intellectually serious argument, and it deserves the most substantive response — which is also our most powerful counter. Acknowledge the Liv-ex benchmark's limitations fully. Then demonstrate that our analysis moves beyond those limitations: rolling correlations instead of static snapshots; Liv-ex 1000 and Burgundy 150 instead of Liv-ex 100; custom indices built from latent price data at the LWIN11 level; and ultimately, individual wine selection as the primary lever for delivering uncorrelated diversification. The critics are right that Liv-ex is a bad benchmark. We are right that the solution is not to abandon wine — it is to abandon reliance on Liv-ex indices.

---

## Synthesis: How the Arguments Relate to Each Other

Arguments 1, 4, and 6 are deeply interconnected and should be addressed together in any external communication:

- **Argument 1** says the GBP index headline overstates returns.
- **Argument 4** says currency exposure is a risk, not a feature.
- **Argument 6** says Liv-ex indices are misleading benchmarks.

All three converge on the same point: you cannot simply point at a GBP-denominated Liv-ex chart and say "wine outperformed during the crisis." That is the weakest version of the diversification argument, and the critics are right to attack it.

**The stronger version — and WineFi's actual position — is:**

1. After full FX decomposition, the underlying wine price component showed genuine resilience during GFC and 2022 equity drawdowns.
2. More liquid, Bordeaux-heavy indices (Liv-ex 100) are more correlated with equities than less liquid, broader indices (Liv-ex 1000, Burgundy 150).
3. Rolling correlations over 1–3 year windows show persistently low and unstable correlation between fine wine and equities — not zero, but materially lower than almost any other asset class comparison.
4. Selection is the primary lever: disciplined allocation to wines with idiosyncratic demand drivers (rare vintages, niche producers, emerging-market demand independent of financial cycles) can deliver true portfolio diversification.
5. Fine wine is not a safe haven. It is a structural diversifier for investors with a 3–7 year horizon who can tolerate reduced liquidity.

---

## Internal Recommendations

1. **Retire the simple GBP-only Liv-ex chart as a core marketing exhibit.** Replace it with FX-decomposed multi-currency analysis showing the wine price component separately from the FX component.
2. **Use rolling correlation windows (1-year and 3-year) as standard.** Never present a static correlation heatmap without noting its limitations (illiquidity bias, appraisal smoothing).
3. **Lead with the Liv-ex 1000 and Burgundy 150, not the Liv-ex 100.** These are more representative of the investable universe and show stronger diversification characteristics.
4. **Build and publish custom indices using latent price data.** The `dev_winefi_raf.ml.ml_latent_prices_historic` table provides continuous price series at the LWIN11 level. Chain-link index construction from this data, starting with the most liquid LWIN7s and extending to less liquid names, is the analytical gold standard that no critic can replicate from public data alone.
5. **Always name the heterogeneity.** Specific LWIN7 comparisons (Salon `1807626`, DRC Échezeaux `1028658`, Lafite `1011872`) are more compelling than index-level arguments. Show the performance spread, not just the average.
6. **Acknowledge and address geopolitical risk explicitly.** Include it as a standard risk disclosure for any wine with significant demand concentration in a single market.
7. **Never claim wine is a "safe haven."** The defensible and accurate claim is: *selective, disciplined fine wine investment has historically provided low-correlation diversification relative to equities, with shallower drawdowns during major market stress events, at the cost of reduced liquidity.*

---

*This document is for internal WineFi use only. Not for distribution.*
