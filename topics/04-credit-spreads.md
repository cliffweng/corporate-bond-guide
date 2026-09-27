---
title: "04. Credit spreads"
layout: default
nav_order: 5
---

# Credit spreads
{: .no_toc }

*~9 min read*

**🎯 Interview frequent**

## Why it matters

A corporate bond's yield is the risk-free rate plus a spread that compensates for everything a Treasury doesn't have to worry about: default risk, liquidity, and structural complexity. "Spread" is the single number a credit desk actually trades and monitors intraday — decomposing it correctly is a recurring interview centerpiece.

## Core concepts

- **The spread decomposition.** Corporate yield \\(\approx\\) risk-free rate + credit spread. But the credit spread itself is not pure expected loss — it bundles **expected loss** (default probability × loss given default), a **risk premium** for bearing that uncertain loss, and **liquidity/technical** compensation (corporates trade far less than Treasuries). Risk-neutral (market-implied) default probabilities extracted from spreads are almost always higher than real-world historical default rates for the same rating — the same wedge as implied vs. realized volatility in options.
- **Nominal spread** is simply YTM(corporate) − YTM(comparable-maturity Treasury). It's easy to compute but ignores the shape of the yield curve — a poor tool when the curve isn't flat.
- **Z-spread (zero-volatility spread)** is the constant spread added to *every point* on the Treasury spot curve that makes the discounted cash flows equal the bond's price. It's curve-consistent, unlike the nominal spread, and is the standard credit-desk convention for a bullet bond.
- **OAS (option-adjusted spread)** strips out the value of embedded optionality (calls, puts) from the Z-spread, using an interest-rate model to value the option first. OAS is the apples-to-apples spread for comparing a callable corporate to a bullet — Z-spread alone conflates call risk with credit risk.
- **Asset swap spread** reframes the bond versus the swap curve rather than Treasuries — closer to a bank or hedge fund's actual funding curve, and common in comparing corporates to floating-rate benchmarks.
- **CDS-bond basis.** Buying a cash bond and buying CDS protection on the same name is roughly a synthetic risk-free position (plus funding). Basis = CDS spread − bond's Z-spread (sign convention varies by desk). A persistently nonzero basis reflects funding costs, cheapest-to-deliver optionality in the CDS, counterparty risk, and technical supply/demand — not just credit.
- **Spread widening/tightening — desk language.** "The name widened 20bp" means the spread increased — bad for anyone long the bond or short protection, since the market now demands more compensation for the same credit. Spread moves can happen with zero change in the risk-free curve, which is exactly why spread duration is tracked separately from rate duration.

## Mental model

```
  Corporate yield = Risk-free rate  +  Credit spread
                                          |
                     -----------------------------------------
                     |               |                       |
              Expected loss    Risk premium          Liquidity / technical
              (PD x LGD)      (compensation for      (corporates trade
                               uncertainty of loss)   thinner than UST)

  Nominal spread:  one number vs. one Treasury point   (curve-blind)
  Z-spread:        one number added to the WHOLE curve  (curve-consistent)
  OAS:             Z-spread minus the value of embedded optionality
```

Think of spread the way you think of an insurance premium: part of it is the actuarially fair cost of the loss, and part of it is what the insurer charges you for being the one stuck holding an uncertain claim.

## Interview questions

1. **A corporate bond's Z-spread is 150bp. What does that number actually represent?**
   Answer: The constant spread that, added uniformly to every point on the Treasury spot curve, makes the discounted contractual cash flows equal the bond's market price. It's a curve-consistent measure of compensation over risk-free, bundling default risk, liquidity, and any residual technical factors.

2. **Why would a bond's Z-spread and OAS differ meaningfully, and for which bonds should they be closest?**
   Answer: They differ when the bond has embedded optionality (a call, typically) — OAS removes the value of that option from the spread, so OAS < Z-spread for a callable bond when the call has positive value to the issuer. For a non-callable bullet, there's no option to strip out, so Z-spread and OAS should be nearly identical.

3. **Risk-neutral default probabilities implied from CDS/bond spreads are usually higher than historical (real-world) default rates for the same rating. Why?**
   Answer: Spreads price under a risk-neutral measure that embeds a risk premium (investors demand extra compensation for bearing correlated, fat-tailed default risk) plus liquidity and dealer balance-sheet costs. Historical default rates are simply realized frequencies under the real-world measure — the same "Q vs. P" wedge that shows up between implied and realized volatility.

4. **A trader tells you "the CDS-bond basis on this name is very negative." What's actually going on, and what trade does that suggest?**
   Answer: CDS spread is trading tight relative to the bond's Z-spread (protection is "cheap" relative to the cash bond's implied credit risk). It can reflect funding costs on the bond, cheapest-to-deliver value in the CDS, or technical supply/demand. A basis trade would buy the cash bond and buy protection to capture the gap, subject to funding and counterparty risk.

5. **Why do desks track spread duration separately from interest-rate duration for a corporate bond?**
   Answer: A bond's spread can move with zero change in the Treasury curve — the market can reprice the same issuer's credit risk independently of rates. Spread duration measures price sensitivity to that spread move specifically, and for a stressed or long-dated credit it can dominate rate duration as a source of P&L risk (see [Rate risk vs. credit risk](../11-rate-risk-vs-credit-risk/)).

## Watch

- [Session 11: Costs of Debt and Capital](https://www.youtube.com/watch?v=-7aLvhVuPH0) — Prof. Aswath Damodaran (NYU Stern). Walks through debt ratings and synthetic default spreads as the building blocks of a corporate's cost of debt.
- [Credit default swaps](https://www.youtube.com/watch?v=a1lVOO9Y080) — Khan Academy. The running spread as the price of protection, and how it packages default compensation.

## Further reading

- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapter on spread measures (nominal, Z-spread, OAS).
- Duffie & Singleton, *Credit Risk: Pricing, Measurement, and Management*, on the risk-neutral vs. real-world default probability wedge.
