---
title: "08. IG vs. HY"
layout: default
nav_order: 9
---

# Investment-grade vs. high yield
{: .no_toc }

*~8 min read*

**Interview occasional**

## Why it matters

IG and HY aren't just different points on the same spread curve — they're different markets with different buyers, different documentation, different sensitivity to the economic cycle, and different tools for analysis. Interviewers use this split to check whether you understand *why* the line at BBB−/Baa3 is where the market's behavior actually changes, not just where the rating letter changes.

## Core concepts

- **The line is BBB−/Baa3 and above (IG) vs. BB+/Ba1 and below (HY/speculative grade)** — see [Ratings & agencies](../05-ratings-agencies/). This single line gates enormous pools of capital: many insurance companies, pension funds, and money-market-adjacent mandates are restricted to IG only, either by internal policy or regulatory capital treatment.
- **Different buyer base, different behavior.** IG is dominated by real-money buy-and-hold accounts (insurers, pensions) that care about matching liabilities and rarely trade actively. HY is dominated by mutual funds, ETFs, CLOs, and hedge funds with shorter horizons and more active turnover — which is part of why HY spreads are more volatile and more correlated with equity market sentiment than IG spreads are.
- **Rate risk dominates IG; credit risk dominates HY.** An IG bond's total risk is mostly duration/rate risk, because default probability is low — an IG bond often trades and behaves like a rates instrument with a modest credit overlay. A HY bond's price is driven far more by spread/credit-quality moves than by Treasury rate moves — see [Rate risk vs. credit risk](../11-rate-risk-vs-credit-risk/).
- **Documentation is meaningfully different.** IG bonds are typically bullets (non-callable) with thin covenant packages — the market relies on the rating and disclosure regime, not contractual protection. HY bonds are usually callable from early in their life, carry the full incurrence-covenant package (restricted payments, debt incurrence, negative pledge), and are far more document-intensive to analyze — see [Indentures & covenants](../07-indentures-covenants/).
- **"Crossover" credits and fallen angels.** BBB/Baa-rated issuers sitting near the IG/HY line are watched closely because a downgrade forces IG-only holders to sell indiscriminately regardless of fundamental view — historically one of the more reliable sources of technical (non-fundamental) spread widening. A large wave of fallen angels (like March 2020) can temporarily overwhelm HY market capacity to absorb the new supply.
- **CCC and below is its own regime.** Within HY, CCC-rated (and below) credits behave qualitatively differently from BB/B — spreads become extremely sensitive to idiosyncratic news, liquidity dries up fastest here first in a risk-off move, and recovery/restructuring scenario analysis (not spread-duration math) becomes the primary analytical lens.
- **Index and benchmark structure differs.** IG benchmarks (e.g., broad corporate bond indices) are duration-heavy and rate-sensitive; HY benchmarks are spread-heavy. Total return attribution for the two asset classes decomposes very differently — an IG portfolio manager worries about the Fed; a HY portfolio manager worries about the default cycle and idiosyncratic credit stories.

## Mental model

```
  AAA .......... BBB-  |  BB+ .......... CCC .......... D
  Investment grade      High yield / speculative grade
  (rate risk dominates)      (credit risk dominates)

  IG buyer: insurer/pension, buy-and-hold, cares about duration match
  HY buyer: mutual fund/CLO/hedge fund, active, cares about spread & default cycle

  Downgrade crossing the line -> forced selling by IG-only mandates
  ("fallen angel") -- a TECHNICAL flow, separate from the fundamental credit story
```

## Interview questions

1. **Why does an IG corporate bond behave more like a rates instrument, while a HY bond behaves more like a credit/equity-correlated instrument?**
   Answer: IG default probability is low enough that expected loss is a small part of the yield, so price moves are dominated by Treasury rate changes (duration). HY default probability is materially higher and more cyclical, so spread changes — which track the market's evolving view of default risk — dominate price moves, and those spread changes are themselves correlated with equity risk sentiment.

2. **What happens to HY spreads, mechanically, when a large wave of BBB issuers gets downgraded to HY simultaneously (a "fallen angel" wave)?**
   Answer: A sudden surge of new HY supply hits a market with finite dedicated HY buyer capacity, at the same time forced sellers (IG-only mandates) are dumping the newly-downgraded bonds regardless of price. Spreads across HY can widen well beyond what fundamentals alone justify — a technical/liquidity effect, historically often followed by mean reversion once the flow is absorbed (2020 being the largest recent example).

3. **Why are HY bond indentures so much more covenant-heavy than IG bond indentures?**
   Answer: IG issuers have low default probability and strong disclosure/rating oversight, so the market accepts thin contractual protection and relies on the rating. HY issuers carry meaningfully higher default risk, so bondholders demand explicit contractual limits on leverage, dividends, and asset sales (the covenant package) to protect against value leakage before repayment — the covenants are a substitute for the credit-quality cushion IG bonds don't need.

4. **A CCC-rated bond and a BB-rated bond both "high yield" — why should you analyze them completely differently?**
   Answer: BB/B credits are still meaningfully likely to survive to maturity, so spread-duration and relative-value framing (similar tools to IG, just wider spreads) still apply reasonably well. CCC and below have a high enough probability of distress or default that the relevant analysis shifts to recovery/waterfall scenario modeling and restructuring outcomes — you're pricing a distressed-debt problem, not a spread-trading problem.

5. **Why do HY spreads tend to be more correlated with the equity market than IG spreads are?**
   Answer: Both HY bonds and equities are levered claims on the same underlying enterprise value and are highly sensitive to the same driver — the issuer's expected future cash flow and default risk. IG bonds, by contrast, have default probability low enough that equity-market-driven fundamental news moves them much less; their price action is dominated by rates, which don't move in lockstep with equities the same way.

## Watch

- [Session 11: Costs of Debt and Capital](https://www.youtube.com/watch?v=-7aLvhVuPH0) — Prof. Aswath Damodaran (NYU Stern). Debt ratings, synthetic spreads, and where the IG/HY line changes the cost-of-debt calculus.
- [Session 24: Distressed Equity as an option](https://www.youtube.com/watch?v=L2luFJSpQo8) — Prof. Aswath Damodaran (NYU Stern). Why the lowest-rated HY names shift the analytical frame toward distressed/option-like thinking.

## Further reading

- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapter comparing investment-grade and high-yield market structure.
- Altman, Edward I., research on fallen angels and high-yield default/recovery cycles.
