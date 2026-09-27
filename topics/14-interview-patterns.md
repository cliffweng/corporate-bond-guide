---
title: "14. Interview patterns"
layout: default
nav_order: 15
---

# Corporate bond and credit interview patterns
{: .no_toc }

*~10 min read*

**🎯 Interview frequent**

## Why it matters

Credit and FI desk interviews recycle a small set of canonical structures: price a bond and explain duration on a whiteboard, walk through spread decomposition, size expected loss from a spread, or map a capital structure and estimate recovery. This page integrates the whole curriculum — from [price/yield](../01-bond-basics-price-yield/) through [rate vs. credit risk](../11-rate-risk-vs-credit-risk/) — into the frameworks you actually deliver under pressure.

## Core concepts

- **Pattern A: The price/yield/duration walkthrough.** Given a coupon, maturity, and yield, be ready to (1) state the pricing formula, (2) explain price/yield inverse relationship from first principles, (3) estimate Macaulay and modified duration intuitively (shorter maturity or higher coupon → lower duration), and (4) apply the Taylor approximation \\(\frac{\Delta P}{P} \approx -D\_{\text{mod}}\Delta y + \frac{1}{2}\text{Conv}(\Delta y)^2\\) for a given rate shock. See [Bond basics](../01-bond-basics-price-yield/) and [Duration & convexity](../03-duration-convexity/).
- **Pattern B: Spread decomposition and expected loss.** Given a spread (nominal, Z-spread, or CDS), decompose it into expected loss + risk premium + liquidity, then invert the hazard-rate approximation \\(s \approx \lambda \times LGD\\) to back out an implied default probability, and sanity-check that risk-neutral PD sits above the historical/real-world PD for that rating. See [Credit spreads](../04-credit-spreads/) and [Default & recovery](../09-default-recovery/).
- **Pattern C: Capital structure and recovery waterfall.** Given a simplified balance sheet (secured debt, unsecured debt, equity) and an assumed enterprise value in distress, apply absolute priority to compute recovery by tranche, and identify the fulcrum security. See [Seniority & capital structure](../06-seniority-capital-structure/).
- **Pattern D: IG vs. HY and rate-vs-credit risk framing.** Given a bond description (rating, tenor, callability), classify it as rate-risk-dominated or spread-risk-dominated, and explain how you'd hedge each component separately (Treasury futures/swaps for rate risk, CDS for credit risk). See [IG vs. HY](../08-ig-vs-hy/) and [Rate risk vs. credit risk](../11-rate-risk-vs-credit-risk/).
- **Pattern E: Covenant and structural red-flag spotting.** Given a term-sheet-style summary, identify the seniority/security, the use of proceeds, the call schedule, and flag any wide covenant baskets that weaken bondholder protection. See [Indentures & covenants](../07-indentures-covenants/) and [Reading a term sheet](../13-reading-teaser-term-sheet/).
- **Pattern F: Relative value pitch.** Given two comparable bonds (same sector, different issuers or maturities), build a one-minute relative-value pitch: normalize spread by leverage or maturity, check the CDS-bond basis if relevant, and state a clear cheap/rich conclusion with the risk to that view. See [Relative value](../10-relative-value-spreads/).

## Mental model

```
  DELIVER LIKE A CREDIT ANALYST'S ONE-MINUTE PITCH:

  1. State the headline number       (spread, yield, or recovery estimate)
  2. Decompose it                    (rate vs. credit; PD vs. LGD; seniority)
  3. Sanity-check against a peer/benchmark
  4. State the risk to your view     (what would make you wrong)

  Whiteboard math patterns to have cold:
  Price = Σ CF_t / (1+y)^t            Duration ≈ -1/P · dP/dy
  s ≈ λ × LGD                         Survival(t) ≈ e^(-λt)
  Recovery by tranche = waterfall(EV, capital structure)
```

## Interview questions

1. **Walk me through pricing a 5-year, 4% semiannual coupon bond and estimating its modified duration, in under 90 seconds.**
   Answer: "Price is the sum of ten semiannual coupon payments of $20 plus the $1,000 face value, each discounted at the semiannual yield. Modified duration is the PV-weighted average time of those cash flows, adjusted for compounding frequency — intuitively, since it's a 5-year bond with a modest coupon, duration will be meaningfully below 5, likely in the 4.2–4.5 range, because roughly 15–20% of the cash flow's present value arrives before maturity via coupons, pulling the weighted average time down from the full 5 years."

2. **A 5-year CDS trades at 180bp. Assume 40% recovery. What's the implied hazard rate, and how does that compare to what you'd expect from the issuer's BB rating?**
   Answer: \\(\lambda \approx 0.018/0.6 = 3\%\\) per year, implying roughly a 14% cumulative 5-year default probability (\\(1 - e^{-0.03 \times 5}\\)). If historical BB 5-year default rates run in the mid-single digits, the CDS-implied PD sitting well above that is consistent with the usual risk-neutral vs. real-world wedge — but if the gap looks unusually large versus typical BB spreads, it's worth flagging as either elevated market-implied concern or a technical/liquidity effect specific to that name.

3. **Enterprise value in distress is $400mm. Capital structure: $250mm first-lien secured, $200mm senior unsecured. Where's the fulcrum security, and what does each tranche recover?**
   Answer: First-lien secured recovers in full: $250mm / $250mm = 100%. Remaining value of $150mm goes to senior unsecured against its $200mm claim: $150mm / $200mm = 75% recovery — this is the fulcrum security, since it's the most senior class impaired below par, and it's the tranche most likely to end up converted into (or negotiating for) the reorganized company's new equity. Equity gets nothing.

4. **You're long a BBB− corporate bond. Rates rally 30bp but the issuer's spread widens 40bp on takeover-leverage rumors. Net effect on price, and how would you have hedged just the rumor risk?**
   Answer: Roughly, if rate duration and spread duration are similar in magnitude, the rally partially offsets the widening, but the net is still a modest loss since spread widened more than rates rallied. To hedge just the takeover/re-leveraging risk without touching your rate view, you'd buy CDS protection on the name (isolating credit risk) rather than shorting Treasury futures (which only hedges rate risk and leaves the spread widening fully exposed).

5. **Pitch me: which is the better relative value, a BB issuer trading at 300bp with 4x leverage, or a BB issuer in the same sector trading at 320bp with 3x leverage?**
   Answer: "The second issuer — despite the narrower headline spread pickup being smaller, it's compensating you nearly the same spread for a full turn less leverage. On a spread-per-turn basis, it's cheap relative to the first name. The risk to this view is that I'm normalizing only on leverage — if the first issuer has meaningfully more stable cash flow, better covenant protection, or superior collateral, that could justify its tighter leverage-adjusted spread, so I'd want to check coverage ratios and covenant baskets before sizing a trade."

## Watch

- [Session 1: Introduction to Valuation](https://www.youtube.com/watch?v=znmQ7oMiQrM) — Prof. Aswath Damodaran (NYU Stern). The delivery discipline — headline conclusion first, structured reasoning second — that also defines a strong credit pitch.
- [Session 25: Closing Thoughts](https://www.youtube.com/watch?v=Q_8rnowvoYw) — Prof. Aswath Damodaran (NYU Stern). Synthesizing valuation and risk judgment across a full framework, the same instinct this page asks you to apply to credit.

## Further reading

- Moyer, Stephen G., *Distressed Debt Analysis: Strategies for Speculative Investors*, for worked capital-structure and recovery-waterfall case studies.
- Fabozzi, *Bond Markets, Analysis, and Strategies*, as the single-volume reference underlying nearly every pattern on this page.
