---
title: "05. Ratings & agencies"
layout: default
nav_order: 6
---

# Ratings and agencies
{: .no_toc }

*~8 min read*

**Interview occasional**

## Why it matters

Ratings are the shorthand the whole market uses to sort credits before anyone reads a single covenant — they gate what many funds are even allowed to buy, and they're baked into regulatory capital rules for banks and insurers. Knowing what a rating is (and isn't) protects you from the classic interview trap of treating a letter grade as a precise probability.

## Core concepts

- **The big three: Moody's, S&P, Fitch.** Moody's uses Aaa/Aa/A/Baa/Ba/B/Caa/Ca/C; S&P and Fitch use AAA/AA/A/BBB/BB/B/CCC/CC/C, each with +/− or numeric modifiers (Aa1/Aa2/Aa3 ≈ AA+/AA/AA−). The letter is an *ordinal ranking of relative credit risk*, not a calibrated default probability — agencies are explicit that ratings measure relative, not absolute, risk.
- **Investment grade vs. speculative grade is the single most consequential line in the market.** BBB−/Baa3 or better is investment grade (IG); BB+/Ba1 or below is high yield (HY) / speculative grade. Many pension funds, insurers, and money-market-adjacent mandates are contractually or regulatorily restricted to IG only — a downgrade across that line ("fallen angel") forces indiscriminate selling regardless of fundamental view. See [IG vs. HY](../08-ig-vs-hy/).
- **What agencies actually assess.** Business risk (industry cyclicality, competitive position, scale), financial risk (leverage ratios like Debt/EBITDA, interest coverage, FFO/Debt), management/governance quality, and increasingly explicit country/industry ceilings. Methodology publications for each sector are public and are exactly what a credit analyst benchmarks against.
- **Issuer rating vs. issue rating.** A corporate has a single issuer (family) rating, but individual bonds can be rated differently based on seniority and structural position — a senior secured note can sit one or more notches above the issuer rating, a subordinated note one or more notches below, reflecting expected recovery in default (see [Seniority & capital structure](../06-seniority-capital-structure/)).
- **Watchlist and outlook are the leading indicators.** A "negative outlook" or "on review for downgrade" precedes many actual rating actions by months and often moves spreads before the letter grade changes — the market reacts to the *direction of travel*, not just the current notch.
- **Ratings are lagging, and the agencies know it.** Ratings react to public information and agency analyst judgment; markets and CDS spreads frequently move ahead of a rating change. The 2008 crisis and CDO downgrades are the canonical cautionary tale about over-relying on ratings as a risk-management substitute rather than an input.
- **Split ratings and shadow/synthetic ratings.** When agencies disagree (a "split-rated" credit), desks often use the average or the lower of the two as the working assumption; for unrated or thinly-rated issuers, analysts build a synthetic rating from the same financial-ratio framework the agencies publish.

## Mental model

```
  Issuer (corporate family) rating
        |
        +-- Senior secured notes   ->  rated ABOVE issuer rating (better recovery)
        +-- Senior unsecured notes ->  rated AT/near issuer rating
        +-- Subordinated notes     ->  rated BELOW issuer rating (worse recovery)

  Investment grade  |  Speculative grade (high yield)
  AAA / Aaa  ......  BBB- / Baa3   |   BB+ / Ba1  ......  D
                     ^
              the line that triggers forced selling on a downgrade ("fallen angel")
```

## Interview questions

1. **What does a "BBB" rating actually tell you, and what does it not tell you?**
   Answer: It tells you S&P/Fitch's ordinal, relative assessment that this issuer's credit risk sits in the lowest investment-grade tier, based on business risk, leverage, and coverage metrics. It does not give you a precise, calibrated default probability, a market price, or a guarantee that the rating is current — outlooks and watchlist status carry the forward-looking signal.

2. **Why can a single corporate have bonds with different ratings from the same agency?**
   Answer: Because notching reflects expected recovery given the bond's position in the capital structure. A senior secured tranche recovers more in default than a subordinated tranche of the same issuer, so agencies notch the issue rating up or down from the issuer/family rating accordingly.

3. **A BBB− issuer gets downgraded one notch to BB+. Why does this matter more than a BBB to BBB− downgrade of the same size?**
   Answer: It crosses the investment-grade/high-yield line. Many IG-only mandates are forced to sell regardless of their fundamental credit view ("fallen angel" selling), which can push spreads wider than the fundamental deterioration alone would justify — a technical, forced-flow effect layered on top of the credit story.

4. **Ratings agencies were widely criticized after 2008. What's the structural critique, beyond "they got it wrong"?**
   Answer: The issuer-pays model creates a potential conflict of interest (agencies are paid by the entities they rate); ratings are inherently backward/slow-moving relative to market-implied risk (CDS spreads); and for structured products specifically, rating models underestimated correlated default risk across underlying assets. The lesson for a credit analyst: use ratings as one input, cross-check against spread-implied and fundamental views, never as a sole risk gate.

5. **How would you build a "shadow rating" for an unrated private credit?**
   Answer: Apply the same public methodology frameworks the agencies publish for that industry — benchmark leverage (Debt/EBITDA), coverage (EBITDA/Interest, FFO/Debt), scale, margin stability, and business-risk qualitative factors against rated peers, then map the resulting profile to the nearest rating category as a working proxy.

## Watch

- [Session 11: Costs of Debt and Capital](https://www.youtube.com/watch?v=-7aLvhVuPH0) — Prof. Aswath Damodaran (NYU Stern). Walks through how ratings map to synthetic default spreads and feed into the cost of debt.

## Further reading

- Moody's and S&P publish their rating methodology frameworks by sector — the public overview documents are the closest thing to "the answer key" a credit analyst benchmarks against.
- Partnoy, Frank, "The Siskel and Ebert of Financial Markets": a widely cited academic critique of the issuer-pays ratings model.
