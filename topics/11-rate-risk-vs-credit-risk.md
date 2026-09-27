---
title: "11. Rate risk vs. credit risk"
layout: default
nav_order: 12
---

# Interest-rate risk vs. credit risk
{: .no_toc }

*~8 min read*

**🎯 Interview frequent**

## Why it matters

Every corporate bond carries two distinct, separately hedgeable risks bundled into one instrument: the risk-free curve can move, and the issuer's creditworthiness can move, independently of each other. A credit desk's entire hedging and risk-management framework rests on being able to separate and price these two exposures individually rather than treating "bond risk" as one undifferentiated number.

## Core concepts

- **Two separate sources of price sensitivity.** Rate duration (see [Duration & convexity](../03-duration-convexity/)) measures sensitivity to the risk-free curve; spread duration measures sensitivity to the issuer's credit spread, holding the risk-free curve fixed. Total price sensitivity is approximately additive: \\(\frac{\Delta P}{P} \approx -D\_{\text{rate}}\,\Delta y\_{\text{rf}} - D\_{\text{spread}}\,\Delta s\\).
- **They can move in opposite directions.** A classic risk-off episode: Treasury yields fall (flight to quality, rates duration gains) while credit spreads widen (flight from risk, spread duration loses) — the two effects can partially offset, fully offset, or compound depending on magnitude. A pure "duration" hedge using Treasury futures only neutralizes the first term and leaves the second fully exposed.
- **Hedging rate risk without touching credit risk.** Shorting Treasury futures or an interest-rate swap against a corporate bond position isolates the spread component — this is exactly how a credit-focused desk expresses a pure view on an issuer's creditworthiness without taking a directional rates bet.
- **Hedging credit risk without touching rate risk** is what CDS is built for: buying protection removes (most of) the default/spread exposure while leaving the underlying bond's rate exposure with the investor (unless also hedged separately).
- **Which risk dominates depends on where you sit on the credit spectrum.** For high-grade issuers, rate duration typically dominates total risk because spread/default risk is small (see [IG vs. HY](../08-ig-vs-hy/)); for high-yield and especially distressed names, spread duration dominates, and at the most stressed end, price behaves almost entirely as a function of expected recovery rather than either duration measure meaningfully.
- **Correlation between rates and spreads is regime-dependent, not constant.** In a "growth scare" / recession-risk regime, rates often fall and spreads widen together (both reflecting flight to safety) — negatively correlated in price-impact terms is actually a partial natural hedge for a long bond position (rates gain offsetting spread loss). In a "central bank hiking to fight inflation" regime, rates rising and spreads widening can occur simultaneously — reinforcing losses on both legs at once, the worst combination for a long corporate bond position.
- **DTS (duration times spread)** is a practical portfolio-risk convention: scaling spread duration by the current spread level itself, on the empirical observation that *proportional* spread changes (not absolute bp changes) are more stable across the credit spectrum — a AA credit's spread might move 10% in a stress event while a CCC credit's spread might move 10% too, even though the bp magnitude is wildly different.

## Mental model

```
  Total bond return  ≈  Rate return          +      Spread return
                         -D_rate x Δy_rf              -D_spread x Δs

  IG bond:     |=================|  (mostly rate risk, small spread slice)
  HY bond:     |=====|===========|  (rate risk shrinks, spread risk grows)
  Distressed:  |==|==============|  (mostly recovery/scenario risk, not duration at all)

  Hedge rate risk only:  short Treasury futures / pay-fixed swap  -> isolates spread view
  Hedge credit risk only: buy CDS protection                     -> isolates rate exposure
```

## Interview questions

1. **You're long a 10-year IG corporate bond and want to express a pure "this credit is going to improve" view without taking a rates bet. How do you hedge?**
   Answer: Short Treasury futures (or pay fixed / receive floating on an interest-rate swap) sized to match the bond's rate duration/DV01. That neutralizes the rate-driven component of returns, leaving your P&L driven almost entirely by the spread — which is exactly the credit view you want to express.

2. **Rates fall 20bp and the same issuer's spread widens 20bp on the same day. What happened to the bond's price, roughly?**
   Answer: The two effects largely offset (assuming similar rate and spread duration magnitudes), so the price impact is small — a real-world illustration of why "yield" moves alone don't tell you which risk is actually driving a credit's price, and why decomposing into rate and spread components matters for attribution.

3. **Why does spread duration matter more, proportionally, for a CCC credit than for an AA credit, even if both have similar maturity?**
   Answer: For an AA credit, default/spread risk is a small part of total yield, so most of the price sensitivity comes from the risk-free rate component (rate duration dominates). For a CCC credit, the spread itself is large and volatile, and the credit's price behavior is driven overwhelmingly by changes in perceived default risk — spread duration (and ultimately recovery/scenario analysis) dominates, and traditional Macaulay/modified duration becomes a much less useful description of risk.

4. **What is DTS (duration times spread), and why do some risk models prefer it to plain spread duration for combining exposures across a credit portfolio?**
   Answer: DTS scales spread duration by the current spread level, based on the empirical observation that credit spreads tend to move proportionally (in percentage terms) rather than by a constant absolute bp amount across very different spread levels. This makes DTS a more stable, comparable risk measure across a portfolio spanning tight IG names and wide HY/distressed names than raw spread duration alone.

5. **In a rate-hiking, inflation-fighting cycle, why can a long corporate bond position lose money on both the rate leg and the spread leg simultaneously — the worst-case combination?**
   Answer: Central bank hikes raise the risk-free curve (rate duration loss for a long bond) at the same time tighter financial conditions and slower growth expectations can widen credit spreads (spread duration loss too), rather than the more typical "flight to quality" pattern where falling rates partially offset widening spreads. This dual-loss regime is exactly why understanding the current correlation regime between rates and spreads matters for sizing a credit book's total risk, not just its duration.

## Watch

- [Relationship between bond prices and interest rates](https://www.youtube.com/watch?v=I7FDx4DPapw) — Khan Academy. The pure rate-risk building block before layering on credit.
- [Credit default swaps (CDS) intro](https://www.youtube.com/watch?v=ccaCl1GKdJ0) — Khan Academy. The instrument built specifically to isolate and trade credit risk apart from rate risk.

## Further reading

- Tuckman & Serrat, *Fixed Income Securities*, on decomposing bond risk into rate and spread components.
- Barclays/Bloomberg index methodology papers on duration-times-spread (DTS) as a portfolio risk-aggregation measure.
