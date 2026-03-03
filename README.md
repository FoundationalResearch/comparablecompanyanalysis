# @foundationalresearch/comparablecompanyanalysis

[![npm version](https://img.shields.io/npm/v/@foundationalresearch/comparablecompanyanalysis.svg)](https://www.npmjs.com/package/@foundationalresearch/comparablecompanyanalysis)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![AI Skill](https://img.shields.io/badge/AI-Skill-blue.svg)](#)

**Standalone AI skill for comparable company (comps) analysis** -- a structured methodology for relative valuation using trading multiples and peer comparison.

This package provides a complete, production-grade prompt that guides LLM-powered financial agents through the full comps analysis workflow, from peer selection through football field chart construction.

---

## What Is This?

This is an **agent skill** -- a portable, structured prompt packaged as an npm module. It gives AI agents (Claude Code, Cursor, Codex, or any LLM-based tool) deep domain expertise in comparable company analysis without requiring any runtime dependencies or code execution.

The skill lives in `SKILL.md` and follows a standardized frontmatter format that agent frameworks can discover and load automatically.

## Methodology Overview

The skill guides the agent through a rigorous 6-step comparable company analysis:

### Step 1: Select Comparable Companies
Identify 5-10 publicly traded peers based on industry, size, growth profile, business model, and profitability. Applies strict exclusion criteria for pending M&A targets, recent IPOs, financially distressed companies, and conglomerates.

### Step 2: Gather Trading Multiples
Collect a comprehensive set of valuation multiples across three categories:

**Enterprise Value (EV) Multiples:**
- EV/Revenue (LTM and NTM)
- EV/EBITDA (LTM and NTM)
- EV/EBIT (LTM and NTM)

**Equity Value Multiples:**
- P/E -- Price-to-Earnings (LTM and NTM)
- P/B -- Price-to-Book
- PEG Ratio

**Sector-Specific Multiples:**
- Technology/SaaS: EV/ARR, EV/Gross Profit
- Telecom/Media: EV/Subscribers, EV/EBITDA-CapEx
- REITs: Price/FFO, Price/AFFO
- Banks/Insurance: P/TBV, P/PPOP
- Biotech/Pharma: EV/Pipeline Value
- E-commerce: EV/GMV, EV/Take Rate Revenue

### Step 3: Normalize the Data
Adjust for non-recurring items, stock-based compensation, operating lease treatment, fiscal year alignment, and currency differences to ensure true comparability.

### Step 4: Statistical Analysis
Compute mean, median, 25th/75th percentile, and min/max across the peer set. Identify and handle outliers using standard deviation thresholds. Assess dispersion via coefficient of variation to determine which multiples are most reliable.

### Step 5: Apply Multiples to Target
Select the 2-3 most relevant multiples, apply peer median values to the target's financial metrics, and derive implied enterprise value, equity value, and share price. Assess whether a premium or discount is warranted based on relative growth, margins, competitive position, and governance.

### Step 6: Football Field Chart
Synthesize all valuation ranges into a single visual summary incorporating:
- 52-week trading range
- Comparable company implied range (25th-75th percentile)
- DCF valuation range (if available)
- Analyst consensus price targets
- Precedent transaction multiples (if available)

The overlap zone where multiple methodologies converge represents the most defensible valuation range.

## Output Structure

The skill produces a structured analysis containing:

1. **Executive Summary** -- Valuation conclusion in one paragraph
2. **Peer Selection Table** -- Companies, tickers, market caps, and selection rationale
3. **Trading Multiples Table** -- Full multiples grid with summary statistics
4. **Normalization Notes** -- Material adjustments and their impact
5. **Implied Valuation Summary** -- Applied multiples and resulting valuations
6. **Football Field Chart Description** -- All ranges with convergence analysis
7. **Key Risks and Sensitivities** -- Factors that could shift the valuation

## Installation

```bash
npm install @foundationalresearch/comparablecompanyanalysis
```

No runtime dependencies. The package contains only the skill definition (`SKILL.md`), documentation, and license.

## Usage

### With Claude Code

Add the skill to your project's agent configuration. Claude Code will automatically discover and load `SKILL.md` from the installed package:

```bash
npm install @foundationalresearch/comparablecompanyanalysis
```

Then reference it in your agent's skill configuration or let the framework auto-discover installed `@foundationalresearch/*` skill packages.

### With Cursor

Install the package in your project and configure Cursor's agent to include the skill:

```bash
npm install @foundationalresearch/comparablecompanyanalysis
```

Reference the `SKILL.md` file path in your Cursor rules or agent prompt configuration.

### With Codex

Install and point your Codex agent configuration to the skill:

```bash
npm install @foundationalresearch/comparablecompanyanalysis
```

Include the `SKILL.md` content in your agent's system prompt or tool definitions.

### Direct Usage

You can also read and use the skill content directly:

```javascript
import { readFileSync } from 'fs';
import { resolve, dirname } from 'path';
import { fileURLToPath } from 'url';

// If using from another package
const skillPath = resolve(
  dirname(fileURLToPath(import.meta.url)),
  'node_modules/@foundationalresearch/comparablecompanyanalysis/SKILL.md'
);
const skillContent = readFileSync(skillPath, 'utf-8');
```

## Example Prompt

Once the skill is loaded, you can prompt your agent with queries like:

- *"Run a comparable company analysis for Snowflake (SNOW)"*
- *"Find comps for Shopify and derive an implied valuation range"*
- *"Build a peer group for CrowdStrike and calculate trading multiples"*
- *"What is the implied EV/ARR valuation for Datadog based on SaaS peers?"*

The agent will follow the full 6-step methodology defined in the skill.

## Related Skills

| Skill | Package | Description |
|-------|---------|-------------|
| DCF Valuation | [`@foundationalresearch/dcfvaluation`](https://www.npmjs.com/package/@foundationalresearch/dcfvaluation) | Discounted cash flow analysis with WACC derivation |
| Competitive Analysis | [`@foundationalresearch/companalysis`](https://www.npmjs.com/package/@foundationalresearch/companalysis) | Competitive landscape and strategic positioning |

Using comps analysis alongside DCF valuation provides the most robust valuation framework -- comps capture market sentiment and relative positioning, while DCF reflects intrinsic value based on projected cash flows.

## File Structure

```
comparablecompanyanalysis/
  SKILL.md        # The skill definition (frontmatter + methodology)
  README.md       # This documentation
  LICENSE         # MIT license
  package.json    # npm package metadata
```

## License

MIT -- see [LICENSE](./LICENSE) for details.

Copyright (c) 2026 FoundationalResearch
