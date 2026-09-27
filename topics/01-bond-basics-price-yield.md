---
title: "01. Bond basics (price/yield)"
layout: default
nav_order: 2
---

# Bond basics: price and yield
{: .no_toc }

*~8 min read*

**🎯 Interview frequent**

## Why it matters

A bond is a loan wrapped in a security: the issuer promises a schedule of coupons plus principal, and the market decides how much that promise is worth today. Every other topic in this guide — duration, spreads, ratings, covenants — is a refinement of one idea: **price is the present value of promised cash flows, and yield is the single discount rate that reconciles the two.** A credit interview that starts "walk me through how a bond is priced" is really asking whether you have this reflex cold.

## Core concepts

- **A bond's cash flows are contractual, not projected.** Face value (par, usually $1,000 or $100), coupon rate (annual %, paid semiannually for most US corporates), and maturity date are fixed at issuance. This is what separates a bond from equity: the upside is capped at the promise.
- **Price is the sum of discounted cash flows.** For coupon \\(C\\) paid \\(n\\) times, face \\(F\\), and yield \\(y\\) per period:
\\[
P = \sum\_{t=1}^{n} \frac{C}{(1+y)^t} + \frac{F}{(1+y)^n}
\\]
  Yield-to-maturity (YTM) is the single \\(y\\) that makes this equation balance against the observed market price — it is an internal rate of return, not a market-given curve rate.
- **Price and yield move inversely, always.** Raise \\(y\\) in the formula above and every discount factor \\(1/(1+y)^t\\) shrinks, so \\(P\\) falls. This is arithmetic, not sentiment — it has to be true for any fixed cash-flow stream.
- **Par, premium, discount.** If the coupon rate equals the prevailing yield, the bond trades at par (\\(P = F\\)). Coupon above yield \\(\Rightarrow\\) premium (\\(P > F\\)). Coupon below yield \\(\Rightarrow\\) discount (\\(P < F\\)). A bond issued at par that later trades at a discount is telling you the market now demands a higher yield than the coupon — usually rates rose, credit worsened, or both.
- **Accrued interest and clean vs. dirty price.** Quoted ("clean") price excludes interest accrued since the last coupon date; the actual cash you pay ("dirty" or "full" price) adds it back: \\(P\_{\text{dirty}} = P\_{\text{clean}} + \text{accrued interest}\\). Interview trap: quoted price ≠ what changes hands.
- **Day count and compounding conventions matter at the margin.** US corporates typically use 30/360 semiannual compounding; Treasuries use actual/actual. These are second-order for intuition but first-order if you're asked to match a Bloomberg price to the penny.
- **A bond is a portfolio of zero-coupon bonds.** Each cash flow, discounted at its own maturity-matched rate, sums to the "correct" no-arbitrage price. Pricing everything off one flat YTM is a simplification that breaks down when the yield curve isn't flat — the seed of why spot/par curves and Z-spread exist (see [Yield measures](../02-yield-measures/)).

## Mental model

```
  Coupon $  Coupon $  Coupon $  Coupon $ + Face $
     |         |         |         |
     v         v         v         v
  t=0.5      t=1.0      t=1.5      t=2.0      <- semiannual periods
     |---------|---------|---------|
     Discount each flow back at yield y, per period
     |
     v
  Price today = sum of all discounted flows

  Raise y  -> every discount factor shrinks -> Price falls
  Lower y  -> every discount factor grows   -> Price rises
```

## Interview questions

1. **A 10-year, 5% annual-coupon bond trades at $960 on $1,000 face. Is the yield above or below 5%? Why, without solving for it?**
   Answer: Above 5%. The bond is at a discount to par, and price/yield move inversely, so the market is demanding a return higher than the stated coupon to accept the current price.

2. **Walk me through pricing a plain-vanilla bond from scratch.**
   Answer: Lay out the contractual cash flow schedule (coupons + principal at maturity), pick a discount rate per period, discount each flow back, and sum. YTM is solved by iterating/root-finding the single rate that reproduces the observed market price from that same cash-flow schedule.

3. **Why is the "clean price" you see quoted not the amount you actually pay?**
   Answer: Because interest accrues daily between coupon dates. The buyer compensates the seller for interest earned since the last coupon; the full (dirty) price = clean price + accrued interest. Otherwise a seller would lose the coupon accrual by selling one day before a coupon date.

4. **Two bonds have the same maturity and same YTM but different coupons. Do they have the same price sensitivity to a rate move?**
   Answer: No. The higher-coupon bond returns more cash sooner, so more of its value is weighted toward near-term, less rate-sensitive cash flows — it has lower duration (see [Duration & convexity](../03-duration-convexity/)) even at an identical YTM.

5. **Why can't you just discount every cash flow at the same YTM and call it a "true" price?**
   Answer: A flat YTM assumes one discount rate fits all maturities, which ignores the shape of the actual term structure. The rigorous approach discounts each cash flow at the spot rate for its own maturity; YTM is a market convention/summary statistic, useful for quoting, but curve-based pricing is what actually reconciles arbitrage-free prices across bonds.

## Watch

- [Introduction to bonds](https://www.youtube.com/watch?v=Qh-M3_L4xYk) — Khan Academy. What a bond is: par, coupon, and why a company issues one.
- [Relationship between bond prices and interest rates](https://www.youtube.com/watch?v=I7FDx4DPapw) — Khan Academy. Why prices and yields move inversely, with a simple coupon example.

## Further reading

- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapters on pricing conventions and accrued interest.
- Tuckman & Serrat, *Fixed Income Securities*, chapter 1, for a rigorous treatment of price/yield mechanics and day-count conventions.
