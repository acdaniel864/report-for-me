# Fine Wine as a Diversification Play Argument Rebuttals

We wrote a report about Fine Wine as a diversifier, how it's performed during periods of market stress, it is stored in `projects/correlation-diversification/winefi-diversification-report.md`

Others have written indirect rebuttals, all stored in `projects/correlation-diversification/rebuttals-to-analyse.md`.

Your job is to write two reports and do analysis using data from Mother Duck database, as well as other resources from internet from Yahoo Finance, etc. Exploring if fine wine is a good diversifier within a wider selection of assets. Focusing on the idea that using Liv-ex indices to track the fine wine market is biassed because they are just the most liquid subset of wines and therefore the most highly responsive to changes in market situations. This is a biassed subset, and that heterogeneity within fine wine is key because some wines maintain demand better than others during periods of market stress.

Specifically:
1. One report should be a general internal report for our own learnings and general findings.
2. The second report should be an indirect (not referencing other people) rebuttal that addresses the responses to our report, Which can be shared publicly with WineFi clients and put on our website. In that vein, it needs to be easy to digest, make sense, reference sources correctly, not overly technical, but still withstand any arguments against it.


**My opinion to be explored:**
We absolutely can hang our hat on, “even if the Liv-ex has shown periods of correlation with stocks. Certain wines don’t and asset selection is key.”

Just because industry experts experience lower demand and a harder market when there’s a massive financial crash (which is obvious) doesn’t mean that if you sell your wine during that crash, you’re going to have to take an equal or greater hit on the valuation of that wine compared to how much the S&P might have fallen.

This is one of the most controversial topics in the wine trade but also a topic everyone 𝘭𝘰𝘷𝘦𝘴 to overcomplicate.

Are fine wine returns uncorrelated with other assets and therefore does fine wine make a good portfolio diversifier? 

Why does it even matter?

Whilst fine wine is not completely isolated from financial markets (nothing is in 2026), it has historically shown low and time-varying correlation with other assets like equities and gold.

Static month-on-month correlations can be misleading. Illiquidity, appraisal-based pricing, and non-synchronous trading artificially smooth wine prices and bias correlations downward. 

Rolling correlations provide a more realistic view, showing low but unstable relationships that can briefly rise during systemic crises.

Even then, during major market stress, fine wine has often shown apparent resilience.

Through the 2008 financial crisis, the Liv-ex 100 — an index of frequently traded fine wines — fell ~17% vs. the S&P 500 at ~36%. The fine wine index had recovered to prior highs by 2010 while equities did not until 2013.

Now here’s the key no one talks about…

💎 Fine wine is highly heterogeneous: what wine you invest in matters 𝐚 𝐥𝐨𝐭.

💎 Correlation with mainstream assets, as well as overall returns, varies wildly by region, producer, liquidity and other factors.

💎 Diversification benefits are selection-dependent. 

💎 Broader indices (Liv-ex 1000) and regional indices (e.g. Burgundy 150) have historically shown even lower equity correlation than the Liv-ex 100. 

Now, this is not to say that the wine trade doesn't have a hard time during economic crises, that trading activity is unaffected by the wider market or that 'all fine wine is perfectly uncorrelated with other assets'. 

Fine wine is not as a guaranteed safe haven. But through disciplined data-led selection and purchasing - rather than passive exposure to the market as a whole - low correlation diversification benefits can be achieved. 

A well-selected fine wine portfolio can provide diversification and resilience.

**Additional points to explore:**
- it is important to show the GBP is the baseline currency for fine wines you can argue that it is changes in strerling relative to other currencies that make the largest impact to fine wine prices and we can also show that with data. Maybe you only have to argue its one of the main baseline currencies for it to be a factor worth mentioning. 
- What’s mad is if you were investing in property internationally, one of your considerations would be what currency is this property in and what currency am I likely to sell it in.
- Their argument is like you’re not allowed to mention the the currency element of fine wine ownership/investment. 
- Liquidity can reduce in fine wine without that having a massive effect on transaction prices especially  in the short term.  the real question isn't "Do wine prices fall?" or "Does the market get tougher during wider market instability or crashes like the 08 crisis." It's really how much the price is falling compared to other assets. How hard is it to sell if you want to liquidate.
- Show examples of the heterogeneity within fine wine frequently traded wines that fell in price using transaction data, even more than the market during market crashes;  frequently traded fine wines that fell much less than the market during the market crash.  Analyse what this says about Fine Wine and why grouping it all together is one thing or why using the Liv-ex indices to define the fine wine markets undersell its potential to outperform especially in wider market downturns. For example salon (1807626) and dom perignon (1082656) have been much more resilient than Lafite (1011872) in wider asset market downturns. 



**Database connection:**

Connect to MotherDuck via the Python `duckdb` library. The `motherduck_token` env var is already set in the environment — `duckdb.connect("md:")` picks it up automatically. All dependencies are pre-installed from `requirements.txt`.

```python
import duckdb

conn = duckdb.connect("md:")

# Always use fully qualified table names: database.schema.table
df = conn.execute("""
    SELECT column_name, data_type 
    FROM information_schema.columns 
    WHERE table_schema = 'mrt' 
      AND table_catalog = 'winefi'
      AND table_name = 'mrt_unified_trades_tbvm'
""").df()
```

**First step in any notebook**: Run the schema query above to discover available columns before writing analysis queries. Do NOT assume column names.

**Performance rules**: 
- Never `SELECT *` without a `LIMIT` — some tables have tens of millions of rows.
- Push aggregation and filtering into SQL. Only pull aggregated/filtered results into pandas.
- Use `LIMIT` during development, remove for final analysis.

**Yahoo Finance for comparison assets**: Use the `yfinance` library to pull S&P 500 (`^GSPC`), FTSE 100 (`^FTSE`), and Gold (`GC=F`). Use price-only data (not total return) for correlation analysis.

```python
import yfinance as yf

sp500 = yf.download("^GSPC", start="2000-01-01")["Close"]
ftse = yf.download("^FTSE", start="2000-01-01")["Close"]
gold = yf.download("GC=F", start="2000-01-01")["Close"]
```

**Database navigation:**
1. LWINs used for joins THIS IS VERY IMPORTANT As navigating the database totally relies on understanding this:
Key 1	LWIN7	7 digits	The wine lable (not producer) (e.g. 'Lafite' by Château Lafite Rothschild). - 1011872
Key 2	LWIN11: LWIN7 + Vintage	11 digits	Label with vintage Year the grapes were harvested (e.g., 2010). - 10118722010
Key 3	LWIN16 LWIN7 + Vintage + Bottle Size	16 digits	How much wine is in the bottle (e.g., 750ml vs. 1500ml) with zero padding. - 1011872201000750
Key 4	LWIN18 LWIN7 + Vintage +Pack size + Bottle Size 	18 digits	How many bottles are in the case (e.g., a case of 6 or 12) with zero padding and placed between vintage and bottle size. - 101187220101200750

2. Connect data from the following tables in the MotherDuck database, but don't ever get the entire data set. You have to be selective with what you get, so aggregate calls and joins do as much of the analysis as you can do within the query. Some of these data sets have tens of millions of rows.

database name: winefi
schema name: mrt or ml 
table names: 
- winefi.mrt.mrt_unified_bids (for all current bids) 
- winefi.ml.ml_unified_trades_tbvm (look at all historic trade data with some outliers removed and unification done)

3. Use these colours for plots: 
#9437ff — purple
#83D483 — mantis
#FFD166 — sunglow
#F78C6B— coral
#4D87D0 — blue  
#EF476F— red
#06D6A0 — emerald
#C23FB7 — pink/purple
#4A4A68 — slate


**Liv-ex indices:**
- The returns of these indices are in /Users/AaranDaniel/Desktop/git/report-for-me/projects/correlation-diversification/data/liv-ex_index_history.csv
- Use these and hetrogeneaity between them to make a point about how different subset of (even the most liquid) fine wines have difference correlations to widder asset classes. 


**IMPORTANT POINTS:**
- All prices are in GBP in the datebase unless otherwise stated! Currency needs to be paid careful attention at ALL TIMES. 
- Write across multiple notebooks and keep the notebooks super segmented and clear as to what they're focusing on.
- Save important aggregated data sets and save images in a separate directory.
- Data for all historic liv-ex indices which Trade Fine Wine Markets is stored in `projects/correlation-diversification/data/liv-ex_index_history.csv`
- We only care about the period from ~2000 onwards when the first Liv-ex indices begin. 
- You can decide and define scturtue of `projects/correlation-diversification/` repo 
- You will have to spend some time taking the trade data from sparse trades to something which can be more analysable, and it's going to be important that you think about how that can be analysed. We should focus on transaction prices and quantities to understand how correlated or otherwise fine wine is with other asset classes. 
- Focus on S&P500, FTSE100 and Gold as comparison assets. 
- Move beyond just the LIv-ex indices try to build your own trade based indices if possible.
- One ket focus will have to be on how you build these kinds of indices or market trackers with sparse trade data. Doing it with the most liquid subset of lwin11 or lwin7 will be a good starting point but you need to think about bias here... this is a bias subset how do we look at the less liquid wines? 
- Consider leading academic research on fine wine price tracking and sparse asset price market price tracking.
- Focus on heterogeneity and opportunities that can be found in fine wine. Asking the question what wine labels (LWIN7) or wine-vintages (lwin11) have proven to be good diversifiers - lots of trades and little price decrease - even during wider market crashes AND which (like all the wines in the Liv-ex 1000 probably) have proven to be 
- Check how the Burgundy 150 did during 2008 crash compared to S&P500 after acccounting for currency difference AND vs the FTSE100. 
- A core part of our rebuttle needs to be that Liv-ex 100 and 1000 are THE MOST LIQUID subset of fine wines with secondary market liquidity, using that subset as the measure of 'the market' is common because its easy not because its a perfect representation of the market at wide. 
- Lower trade quantity does not neccessarily = lower prices if you DO try and exit. The fact sellers aren't willing to take a cut on their valuation with say high reserve prices even in a market downturn is a feature not a bug and good for those that do want to exit. 


## What completed looks like:
You should make 2 reports both can be as markdown files with related plots saved in suitably named image dirs.
1. Internal consumption only addressing each of the points made by the articles and giving a balanced nuanced analysis of their veracity. What did they get right, what did they get wrong, what does the data say and how does it relate to our opinions/arguements. 
2. An external facing article which will be used on our website as official company stance on fine wines as a diversifier, its relative performance compared to other asset classes especially in market downturns. 
3. All images are saved and committed to git and every image has a caption that explains the data being shown and that fits on the image. Not titles or text is overlapping on the images. 
4. All arguments are triple checks for their veracity. 

