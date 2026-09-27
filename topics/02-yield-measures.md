---
title: "02. Yield measures"
layout: default
nav_order: 3
---

# Yield measures
{: .no_toc }

*~9 min read*

**🎯 Interview frequent**

## Why it matters

"What's the yield?" is an underspecified question — there are half a dozen answers, and a credit interviewer wants to know you can pick the right one and explain why the others are wrong for the job at hand. Current yield, YTM, yield-to-call, and the spot/par distinction all answer slightly different questions about the same cash flows.

## Core concepts

- **Current yield** is the simplest and weakest measure: \\(\text{CY} = \frac{\text{Annual coupon}}{\text{Price}}\\). It ignores the pull to par at maturity entirely — a bond priced at a deep discount will show a misleadingly low current yield relative to its actual total return.
- **Yield to maturity (YTM)** is the internal rate of return that equates the discounted cash flows to price (see [Bond basics](../01-bond-basics-price-yield/)). It embeds a critical, often-wrong assumption: **all coupons are reinvested at the YTM itself.** If reinvestment rates fall after purchase, realized return will undershoot quoted YTM.
- **Yield to call (YTC) / yield to worst (YTW).** Many corporates are callable. YTC assumes the bond is redeemed at the first call date/price instead of maturity. **Yield to worst** is the minimum of YTM and all YTCs across call dates — the conservative number a credit desk actually quotes for a callable bond, because the issuer will call when it's in the issuer's interest, not the bondholder's.
- **Spot rates vs. par yields.** The spot (zero) rate for maturity \\(t\\) is the rate that discounts a single cash flow at \\(t\\) with no coupon reinvestment assumption. The par yield is the coupon rate that would make a bond of maturity \\(t\\) price exactly at par given the spot curve. When the curve isn't flat, YTM on a coupon bond is a blend of spot rates weighted by cash-flow timing — not equal to the spot rate at maturity.
- **Bond-equivalent yield / semiannual compounding convention.** US corporates and Treasuries quote yields on a semiannual bond basis: annualize a semiannual rate \\(r\\) as \\(2r\\), not \\((1+r)^2-1\\). Mixing conventions is a classic error when comparing a corporate bond to a money-market or Euro-bond yield.
- **Yield-to-put, and the general lesson.** Any embedded option (call, put, sinking fund) creates a family of "yield to X" scenarios; the desk convention is to quote whichever is worst for the holder, because that's the return you can actually count on if the issuer/optionality behaves rationally.

## Mental model

```
  YTM: solve one rate that fits the WHOLE cash-flow schedule to today's price
       (assumes reinvestment at that same rate — often unrealistic)

  Spot rate: solve one rate PER maturity, for a single cash flow, no reinvestment assumption
       (the "true" no-arbitrage building block)

  YTC / YTW: same YTM math, but truncate the cash-flow schedule at a call date
       instead of maturity — then take the worst of all such scenarios
```

Think of YTM as a "blended average speed" for a road trip with several legs at different speed limits; the spot curve is the speed limit sign at each individual mile marker.

## Interview questions

1. **A callable bond yields 6% to maturity but only 4% to its nearest call date. Which does a portfolio manager use to compare against another bond, and why?**
   Answer: Yield to worst (here, 4%). The manager should assume the issuer calls if it's advantageous to the issuer — typically when rates have fallen and refinancing is cheaper — so the conservative, "worst case for the holder" yield is the honest basis for comparison.

2. **Why can realized return on a bond held to maturity differ from its quoted YTM at purchase?**
   Answer: YTM assumes every coupon is reinvested at the YTM rate itself. If market rates fall after purchase, reinvested coupons earn less, and realized return falls short of quoted YTM (reinvestment risk); if rates rise, realized return can exceed YTM.

3. **Explain the difference between a spot rate and a par yield, and why it matters for pricing.**
   Answer: A spot rate discounts a single cash flow at a given maturity with no assumptions about intermediate cash flows. A par yield is the coupon rate that makes a bond of that maturity price at exactly par given the spot curve. When the curve is upward-sloping, a coupon bond's YTM sits below the spot rate at its maturity, because early coupons are discounted at lower short-end spot rates.
   
4. **A bond shows a current yield of 8% but a YTM of 6%. What does that tell you about its price relative to par?**
   Answer: The bond trades at a premium. High coupon relative to price inflates current yield, but the pull-to-par loss at maturity (price above face, amortizing down to par) drags total return (YTM) below the current yield.

5. **Why do desks quote "yield to worst" as the headline number for high-yield callable paper specifically, more than for investment-grade bullets?**
   Answer: HY issuers are far more likely to exercise calls opportunistically (refinance as credit improves, or as part of a capital-structure event), and HY bonds are more often issued with call schedules from day one. IG bullets are frequently non-callable, so YTM and YTW coincide; for callable HY paper the gap can be economically large, so quoting YTM alone would overstate achievable return.

## Watch

- [Introduction to the yield curve](https://www.youtube.com/watch?v=b_cAxh44aNQ) — Khan Academy. What "the" Treasury yield curve actually plots, and the spot-vs-par distinction in practice.
- [Relationship between bond prices and interest rates](https://www.youtube.com/watch?v=I7FDx4DPapw) — Khan Academy. The reinvestment-rate intuition underlying why realized return can diverge from quoted YTM.

## Further reading

- Tuckman & Serrat, *Fixed Income Securities*, chapters on spot, forward, and par yield curves.
- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapter on yield measures and yield-to-call/worst conventions.
