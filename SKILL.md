---
name: comparable-company-analysis
description: Comparable company (comps) analysis methodology for relative valuation using trading multiples
---

# Comparable Company Analysis (Comps)

You are a financial analyst performing a comparable company analysis. This is a relative valuation methodology that derives a company's implied value by examining how similar publicly traded companies are valued by the market. Follow each step methodically.

## Step 1: Select Comparable Companies

Identify 5-10 publicly traded peer companies. Apply the following selection criteria:

**Primary Criteria:**
- **Industry/Sub-sector:** Same GICS sub-industry or direct competitors in the same addressable market
- **Size:** Revenue and market capitalization within a reasonable range (typically 0.5x-2.0x of the target)
- **Growth Profile:** Similar revenue and earnings growth rates (historical 3-year CAGR and forward estimates)
- **Business Model:** Comparable revenue mix (recurring vs. one-time), customer concentration, and go-to-market strategy
- **Profitability:** Similar margin structure (gross margin, EBITDA margin, net margin)

**Geographic Considerations:**
- Prioritize companies with similar geographic revenue exposure
- Note any regional regulatory or market structure differences

**Exclusion Criteria — remove companies that exhibit any of the following:**
- Pending M&A transactions (target or acquirer) that distort trading multiples
- Recent IPO (less than 12 months) with limited trading history and potentially volatile multiples
- Financial distress, restructuring, or bankruptcy proceedings
- Conglomerate structure where the comparable business line is a minority of revenue

Document why each peer was selected and why any obvious candidates were excluded.

## Step 2: Gather Trading Multiples

Collect the following valuation multiples for each comparable company:

**Enterprise Value (EV) Multiples:**
- **EV/Revenue** — LTM (Last Twelve Months) and NTM (Next Twelve Months)
- **EV/EBITDA** — LTM and NTM (most commonly used multiple)
- **EV/EBIT** — LTM and NTM (useful when D&A varies significantly across peers)

**Equity Value Multiples:**
- **P/E (Price-to-Earnings)** — LTM and NTM
- **P/B (Price-to-Book)** — Current
- **PEG Ratio** — P/E divided by expected earnings growth rate

**Sector-Specific Multiples (apply where relevant):**
- **Technology/SaaS:** EV/ARR (Annual Recurring Revenue), EV/Gross Profit
- **Telecom/Media:** EV/Subscribers, EV/EBITDA-CapEx
- **REITs:** Price/FFO (Funds From Operations), Price/AFFO
- **Banks/Insurance:** P/TBV (Price-to-Tangible Book Value), P/PPOP (Pre-Provision Operating Profit)
- **Biotech/Pharma:** EV/Pipeline Value, EV/R&D-adjusted earnings
- **E-commerce/Marketplaces:** EV/GMV (Gross Merchandise Value), EV/Take Rate Revenue

For each multiple, note:
- Source and date of data
- Whether consensus estimates are used for forward multiples
- The diluted share count methodology (treasury stock method)
- Treatment of convertible securities and options

## Step 3: Normalize the Data

Adjust financial metrics to ensure comparability across the peer set:

**Non-Recurring Items:**
- Remove one-time gains/losses, restructuring charges, litigation settlements, and asset impairments from EBITDA and earnings
- Adjust for acquisition-related costs (integration, transaction fees)

**Stock-Based Compensation (SBC):**
- Decide whether to include or exclude SBC from EBITDA — document the approach and rationale
- If excluding, present both SBC-adjusted and unadjusted multiples for transparency

**Operating Leases:**
- Under IFRS 16 / ASC 842, verify that all peers treat leases consistently
- If pre-adoption figures are mixed, capitalize operating leases uniformly

**Fiscal Year Alignment:**
- Calendarize financial data for companies with non-December fiscal year-ends
- Use quarterly data to construct comparable LTM figures on the same end-date

**Currency Adjustments:**
- Convert all figures to a single reporting currency using consistent exchange rates
- Note if any peers have significant FX exposure that affects comparability

## Step 4: Statistical Analysis

Compute summary statistics across the peer set for each multiple:

**Key Metrics:**
- **Mean** — Simple average (note sensitivity to outliers)
- **Median** — Preferred central tendency measure (more robust to outliers)
- **25th Percentile** — Low end of the valuation range
- **75th Percentile** — High end of the valuation range
- **Min / Max** — Absolute range boundaries

**Outlier Treatment:**
- Flag any peer trading at more than 2 standard deviations from the mean
- Consider removing outliers or presenting results both with and without them
- Document the reason for any exclusion (e.g., company-specific event, data error)

**Dispersion Analysis:**
- Calculate the coefficient of variation (standard deviation / mean) for each multiple
- Lower dispersion indicates a more reliable multiple for valuation
- If dispersion is high (CV > 30%), investigate whether the peer set is too heterogeneous

Present the results in a formatted comparison table with all peers and summary statistics.

## Step 5: Apply Multiples to Target

Derive the implied valuation for the target company:

**Multiple Selection:**
- Select 2-3 multiples most relevant to the target's industry and stage
- Prefer multiples with the lowest dispersion across the peer set
- Weight EV/EBITDA and EV/Revenue most heavily for operating companies
- Use sector-specific multiples as a cross-check

**Valuation Calculation:**
- Apply the peer group **median** multiple to the target's corresponding financial metric
- Calculate Implied Enterprise Value = Multiple x Target Metric
- Convert to Implied Equity Value: subtract net debt, minority interests, preferred stock; add associates and equity investments
- Derive Implied Share Price = Implied Equity Value / Diluted Shares Outstanding

**Range Construction:**
- Use 25th-75th percentile range to establish a valuation corridor
- Present point estimates at the median, mean, and for the closest 2-3 peers

**Premium / Discount Assessment:**
- Compare the implied value to the current trading price
- Identify whether a premium or discount is warranted based on:
  - Superior or inferior growth relative to peers
  - Higher or lower margins and return on capital
  - Stronger or weaker competitive position and moat
  - Better or worse management track record
  - Liquidity premium (small-cap vs. large-cap)
  - Country or governance risk differential

## Step 6: Football Field Chart

Synthesize all valuation ranges into a single visual summary:

**Include the following ranges (horizontal bars):**
1. **52-Week Trading Range** — Actual high/low share price over the past 12 months
2. **Comparable Company Analysis** — Implied share price range from this analysis (25th-75th percentile from Step 5)
3. **DCF Valuation Range** — If available, the discounted cash flow implied range (from a separate DCF analysis)
4. **Analyst Price Targets** — Consensus low, median, and high price targets from sell-side coverage
5. **Precedent Transactions** — If available, the implied range from comparable M&A transactions

**Presentation:**
- Mark the current share price as a vertical reference line
- Order ranges from market-based (top) to fundamental (bottom)
- Show the overlap zone where multiple methodologies converge — this is the most defensible valuation range
- Annotate key assumptions or drivers for the widest/narrowest ranges

## Output Format

Present the final analysis with:

1. **Executive Summary** — One paragraph stating the implied valuation range and whether the stock appears undervalued, fairly valued, or overvalued relative to peers
2. **Peer Selection Table** — Company name, ticker, market cap, key operating metrics, and rationale for inclusion
3. **Trading Multiples Table** — All collected multiples for each peer with summary statistics row
4. **Normalization Notes** — Material adjustments made and their impact
5. **Implied Valuation Summary** — Target metric, applied multiple, implied EV, implied equity value, implied share price for each multiple used
6. **Football Field Chart Description** — All ranges with overlap analysis
7. **Key Risks and Sensitivities** — Factors that could shift the valuation outside the stated range

## Important Notes

- **Data Recency:** All market data and consensus estimates must be as of the same date. State the as-of date prominently.
- **Forward vs. Trailing:** NTM multiples are generally preferred as they reflect market expectations, but LTM multiples are more objective. Present both.
- **Circular Reference:** When valuing a public company, exclude the target itself from the peer set.
- **Transaction Context:** If the analysis is for M&A purposes, note that a control premium (typically 20-40%) should be added to the public market implied value.
- **Limitations:** Comps analysis assumes the market correctly values the peer group. If the entire sector is over- or under-valued, the implied value will inherit that bias.
- **Complementary Methods:** Comps should be used alongside DCF analysis and, where applicable, precedent transaction analysis to triangulate a robust valuation range.
