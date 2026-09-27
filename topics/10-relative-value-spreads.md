---
title: "10. Relative value / spread analysis"
layout: default
nav_order: 11
---

# Relative value and spread analysis
{: .no_toc }

*~9 min read*

**🎯 Interview frequent**

## Why it matters

A credit trader's day-to-day job is rarely "is this bond cheap in absolute terms" — it's "is this bond cheap *relative to* something else I could own instead." Relative value (RV) analysis is that comparative discipline: same issuer across the curve, same sector across issuers, or cash bond versus CDS. It's the practical, tradeable synthesis of everything else in this guide.

## Core concepts

- **Same-issuer curve analysis.** Compare a single issuer's bonds across maturities on a spread basis. If the 5-year trades at 150bp and the 10-year at 180bp, the curve is upward-sloping (normal — investors demand more spread for longer, less certain exposure to the credit). An inverted or unusually flat issuer curve can signal the market pricing near-term distress risk more heavily than long-term risk, or simply technical/liquidity effects in one maturity bucket.
- **Cross-issuer, same-sector comparison.** Within a sector (say, regional banks or midstream energy), rank bonds by spread per unit of leverage or spread per notch of rating, controlling for maturity. A bond trading wide to sector peers with similar fundamentals is either "cheap" (an opportunity) or the market is pricing idiosyncratic risk you haven't identified yet — the analyst's job is to figure out which.
- **Spread per turn of leverage.** A rough desk heuristic: divide the spread by Debt/EBITDA to get a normalized "spread per turn," useful for comparing issuers with different leverage levels within the same sector. Two BB credits with the same spread but very different leverage are not equally risky — the one with lower leverage is arguably cheap relative to the other.
- **CDS-bond basis as an RV trade.** As covered in [Credit spreads](../04-credit-spreads/), a persistent gap between CDS spread and bond Z-spread on the same name is a classic basis trade: buy the cheaper side, sell/hedge the richer side, subject to funding costs and counterparty risk on the CDS leg.
- **Index vs. constituent analysis.** CDX/iTraxx (or bond index) levels represent the average; RV analysis often means finding constituents trading wide or tight to where the index-implied fair value and the name's idiosyncratic fundamentals suggest they should sit — dispersion trades exploit exactly this gap.
- **New issue concession.** A newly issued bond typically prices with a spread concession versus the issuer's existing secondary curve, to compensate primary buyers for taking down size. Post-issuance, this concession often compresses ("new issue premium comes in") — a very common, short-horizon RV trade in liquid primary markets.
- **Curve roll-down.** As time passes, a bond "rolls down" an upward-sloping curve toward shorter effective maturity, which — holding the issuer's credit curve shape constant — implies price appreciation beyond just coupon carry. This total-return effect is often underappreciated relative to pure spread-change P&L in RV comparisons.

## Mental model

```
  Same issuer, across maturities:        Same sector, across issuers:
  spread                                 spread
    |                    * 10y               |     * Issuer A (cheap? or risky?)
    |            * 7y                         |   * Issuer B
    |      * 5y                               | * Issuer C
    |  * 3y                                   |
    +---------------- maturity                +---------------- leverage (Debt/EBITDA)

  Normal: upward-sloping issuer curve    Normalize by leverage: "spread per turn"
  Compare: spread per turn of leverage, CDS-bond basis, new-issue concession
```

## Interview questions

1. **Issuer X's 5-year bond trades at 200bp and its 10-year at 190bp — an inverted spread curve. What might explain this?**
   Answer: The market may be pricing near-term distress or refinancing risk more heavily than long-term risk (common ahead of a maturity wall or covenant test), or it could be a technical/liquidity effect isolated to one maturity bucket (e.g., an index-eligibility quirk or a large one-off trade). An inverted credit curve is a flag worth investigating, not a definitive distress signal on its own.

2. **Two BB-rated issuers in the same sector trade at the same nominal spread, but Issuer A has 3x Debt/EBITDA and Issuer B has 5x. Which is "cheap" on a relative-value basis?**
   Answer: Issuer A, on a spread-per-turn-of-leverage basis — it's compensating you the same spread for materially less leverage risk. That said, a full RV call also needs to check whether Issuer B has offsetting positives (e.g., more stable cash flow, better covenant protection) before concluding it's simply mispriced.

3. **Walk me through a CDS-bond basis trade end to end.**
   Answer: Identify a name where CDS spread and bond Z-spread diverge meaningfully beyond what funding/technical factors justify. If the bond is cheap relative to CDS (bond Z-spread wide of CDS), buy the bond and buy CDS protection — you're roughly synthetically risk-free (isolating the basis) while collecting the spread differential, subject to funding cost on the bond position and counterparty risk on the CDS leg.

4. **A new bond prices at a 20bp concession to the issuer's existing curve. What happens to that bond over the following weeks in a typical, calm market, and why?**
   Answer: The concession typically compresses ("comes in") toward the secondary curve as the deal is absorbed and primary buyers who wanted concession-driven allocation rotate out — a common, short-horizon RV trade of buying new issues and selling once the concession normalizes, assuming no idiosyncratic credit deterioration in the interim.

5. **Why might "spread per turn of leverage" be a misleading metric to rely on in isolation?**
   Answer: It normalizes only for one variable (leverage) and ignores everything else that drives credit risk — cash-flow stability, covenant protection, industry cyclicality, collateral quality, and management quality. Two issuers with identical leverage can have very different genuine credit risk; the metric is a useful screening heuristic to generate ideas, not a standalone valuation conclusion.

## Watch

- [Introduction to the yield curve](https://www.youtube.com/watch?v=b_cAxh44aNQ) — Khan Academy. The building block for comparing a single issuer's spread across maturities.
- [Credit default swaps](https://www.youtube.com/watch?v=a1lVOO9Y080) — Khan Academy. The CDS mechanics underlying basis-trade relative value analysis.

## Further reading

- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapter on relative value analysis and spread-based trading strategies.
- Choudhry, Moorad, *The Credit Default Swap Basis*, on CDS-bond basis mechanics and trade construction.
