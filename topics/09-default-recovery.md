---
title: "09. Default & recovery"
layout: default
nav_order: 10
---

# Default and recovery
{: .no_toc }

*~9 min read*

**🎯 Interview frequent**

## Why it matters

Expected loss — the number that ultimately justifies a spread — is built from exactly two ingredients: how likely is default, and how much do you get back if it happens. Every credit interview eventually asks you to combine these two numbers, usually with a CDS or bond spread as the starting point.

## Core concepts

- **Expected loss decomposition.** \\(\text{EL} \approx PD \times LGD \times EAD\\), where \\(PD\\) is probability of default over the horizon, \\(LGD\\) is loss given default, and \\(EAD\\) is exposure at default. Recovery rate \\(R = 1 - LGD\\); a commonly cited rough assumption for senior unsecured corporate debt is \\(R \approx 40\%\\), but this is a convention, not a law — actual recovery varies enormously by seniority, industry, and cycle.
- **What counts as a default.** Ratings agencies and CDS documentation define it broadly: missed coupon or principal payment, bankruptcy filing, and — for CDS specifically — sometimes a "distressed exchange" where bondholders are pressured into accepting worse terms to avoid a formal default. The precise definition matters a great deal for CDS settlement and historical default-rate statistics.
- **The interview hazard-rate approximation.** For a flat hazard rate \\(\lambda\\) and CDS par spread \\(s\\): \\(s \approx \lambda \times LGD\\). So a 100bp spread at 40% assumed recovery implies \\(\lambda \approx 100\text{bp} / 0.6 \approx 167\\)bp of hazard per year. Survival probability under constant hazard: \\(P(\tau > t) = e^{-\lambda t}\\) — a 5-year survival at that hazard is \\(e^{-0.0167 \times 5} \approx 92\%\\), so 5-year cumulative default probability \\(\approx 8\%\\).
- **Recovery varies systematically by seniority.** Historically: secured/first-lien loans recover the most (often 60–80%+), senior unsecured bonds recover moderately (call it 35–50% on average, wide dispersion), subordinated debt recovers the least. This is the empirical face of the waterfall discussed in [Seniority & capital structure](../06-seniority-capital-structure/) — theory and data agree here.
- **Recovery is cyclical, not a fixed constant.** Recovery rates are meaningfully lower in systemic, industry-wide downturns (when many firms in the same sector default simultaneously and asset sales flood a depressed market) than in idiosyncratic, single-name defaults where a healthier buyer can acquire distressed assets near fair value. Modeling recovery as a fixed 40% ignores this correlation between PD and LGD in a real credit cycle — a subtlety interviewers like to probe.
- **Recovery is realized value, not a quoted market price at default.** The actual recovery an investor achieves depends on how the default is resolved: a negotiated out-of-court restructuring, a formal Chapter 11 reorganization (potentially converting debt to new equity), or a liquidation (Chapter 7) — each with very different timelines and realized values relative to the "trading price at 30 days post-default" convention CDS auctions use to settle.
- **PD and LGD are correlated, and that correlation is the tail risk.** In a severe, broad recession, default probability rises across many names *and* recovery falls simultaneously (more distressed sellers, fewer buyers, depressed collateral values) — the reason portfolio credit losses are fat-tailed rather than well-approximated by independent, identically-distributed default draws.

## Mental model

```
  Expected Loss  =  PD  x  LGD  x  EAD
                     |      |
                     |      +-- LGD = 1 - Recovery Rate
                     |               Recovery varies by seniority (see topic 06)
                     |               and is LOWER in systemic downturns
                     |
                     +-- CDS/spread-implied PD is usually HIGHER than
                         historical/real-world PD (risk premium + liquidity)

  Interview shortcut:  spread s ≈ hazard rate λ × LGD
                        survival to time t ≈ e^(-λt)
```

## Interview questions

1. **A 5-year CDS trades at a 200bp par spread, and you assume 40% recovery. Estimate the hazard rate and 5-year cumulative default probability.**
   Answer: \\(\lambda \approx 0.02 / 0.6 \approx 3.33\%\\) per year. Survival to year 5 \\(\approx e^{-0.0333 \times 5} \approx 84.6\%\\), so cumulative 5-year default probability \\(\approx 15.4\%\\). (Flat-hazard, continuous-payment approximation — good enough for a screen, not for a term sheet.)

2. **Why is CDS-implied (risk-neutral) default probability typically higher than the historical default rate for a same-rated bond?**
   Answer: The spread compensates for expected loss plus a risk premium (investors demand extra return for bearing correlated, fat-tailed default risk) plus liquidity/technical costs. Historical default rates are simply realized frequencies — there's no premium embedded, just the observed outcome. The gap is the market's price of uncertainty, analogous to implied vs. realized volatility in options.

3. **Why shouldn't you assume a flat 40% recovery rate when modeling expected losses across an entire portfolio through a full credit cycle?**
   Answer: Because PD and LGD are correlated — in a systemic downturn, more issuers default simultaneously *and* recovery falls (distressed asset sales flood a depressed market, fewer healthy buyers exist). Treating recovery as a fixed constant independent of the default environment understates tail risk; portfolio credit losses are fatter-tailed than an independent-draws model would suggest.

4. **A senior secured loan and a senior unsecured bond from the same defaulted issuer show very different recoveries. Explain why, tying it back to capital structure.**
   Answer: The secured loan has a direct claim on specific pledged collateral and is paid from that collateral's value before any unsecured creditor sees a cent (absolute priority). The unsecured bond only has a claim on whatever's left in the general asset pool after secured claims and administrative costs are satisfied — so its recovery is both lower and more variable, since it depends on total enterprise value net of the secured claim, not on a specific asset.

5. **What's the difference between "recovery rate" as used in a CDS auction settlement and the recovery an investor might actually realize by holding through a Chapter 11 reorganization?**
   Answer: CDS auction recovery is a market-clearing price for the deliverable obligation observed roughly 30 days after the credit event — a point-in-time trading price, often depressed by forced/technical selling immediately after default. An investor who holds through a full Chapter 11 process may receive a package of new debt, new equity, and/or cash whose realized value (often over a longer horizon, once the reorganized entity stabilizes) can differ meaningfully from that initial post-default trading price in either direction.

## Watch

- [Credit default swaps](https://www.youtube.com/watch?v=a1lVOO9Y080) — Khan Academy. Protection buyer/seller mechanics and the running spread as the price of default protection.
- [Credit default swaps (CDS) intro](https://www.youtube.com/watch?v=ccaCl1GKdJ0) — Khan Academy. A short, mechanical second pass at the contract and payout on a credit event.

## Further reading

- Altman, Edward I., and Kishore, Vellore M., research on corporate bond recovery rates by seniority and industry.
- Moody's and S&P publish annual default and recovery studies with the empirical seniority-tiered recovery data referenced above.
