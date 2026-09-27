---
title: "03. Duration & convexity"
layout: default
nav_order: 4
---

# Duration and convexity
{: .no_toc }

*~9 min read*

**🎯 Interview frequent**

## Why it matters

Duration and convexity are how a credit or rates desk talks about interest-rate risk without re-pricing an entire book every time the curve twitches by a basis point. This is the most-tested quantitative topic in fixed-income interviews across desks — you are expected to derive the intuition on a whiteboard, not just cite the formula.

## Core concepts

- **Macaulay duration** is the present-value-weighted average time of a bond's cash flows: \\(D\_{\text{Mac}} = \sum\_i t\_i \cdot w\_i\\), where \\(w\_i = \frac{C\_{t\_i} DF(t\_i)}{P}\\). A zero-coupon bond's Macaulay duration equals its maturity exactly; any coupon-paying bond's duration is strictly less, because some value arrives before maturity.
- **Modified duration** converts that time measure into a price sensitivity: \\(D\_{\text{mod}} = -\frac{1}{P}\frac{dP}{dy}\\). For a small parallel yield change \\(\Delta y\\): \\(\frac{\Delta P}{P} \approx -D\_{\text{mod}} \times \Delta y\\). This is the number risk systems and traders mean when they say "duration."
- **DV01 / PV01** is the dollar value of a 1bp move: \\(\text{DV01} \approx D\_{\text{mod}} \times P \times 0.0001\\). Portfolio and hedge sizing is almost always done in DV01 terms, not "duration years," because DV01 aggregates additively across positions of different sizes.
- **Convexity** is the curvature term — the second derivative of price with respect to yield: \\(\text{Conv} = \frac{1}{P}\frac{d^2P}{dy^2}\\). For plain-vanilla (option-free) bonds, convexity is always positive: the price/yield curve bows upward, so duration *understates* the price gain when yields fall and *overstates* the price loss when yields rise.
- **The two-term Taylor expansion** is what interviewers actually want on the whiteboard:
\\[
\frac{\Delta P}{P} \approx -D\_{\text{mod}} \, \Delta y + \frac{1}{2}\, \text{Conv} \, (\Delta y)^2
\\]
  Use duration alone for small moves; add the convexity term for large moves or when comparing two bonds with similar duration but different cash-flow dispersion.
- **Negative convexity is the credit-desk trap.** Vanilla bonds are always positively convex, but callable bonds and MBS can go *negatively* convex: as yields fall, the issuer becomes more likely to call, capping upside and flattening (or inverting) the price/yield curve on the low-yield side. Effective duration can shrink as yields drop — the opposite of a bullet bond.
- **What parallel-shift duration misses.** Both duration and convexity, as defined above, assume a single parallel move in one YTM (equivalently, in a flat curve). Real curves twist, steepen, and flatten. Key-rate duration decomposes sensitivity by curve segment — the tool a rates desk reaches for when "duration" alone isn't precise enough. For credit bonds specifically, spread duration (sensitivity to the credit spread holding the risk-free curve fixed) is a distinct, and often larger, risk than rate duration — see [Rate risk vs. credit risk](../11-rate-risk-vs-credit-risk/).

## Mental model

```
  Price
    |        actual price-yield curve  (convex, bows up)
    |              *  *
    |            *      *
    |          *          *
    |        *   tangent = -duration
    |      *  /
    |    *   /
    |  *    /
    | *    /
    +------------------------ yield
         y0

  small dy: duration (the tangent line) is enough
  large dy: add +1/2 convexity (dy)^2 — actual price sits ABOVE the tangent

  Callable bond, low-yield region: curve flattens / bends DOWN
  as the call becomes likely to be exercised — negative convexity
```

A barbell (cash concentrated at short and long maturities) has more convexity than a bullet (cash concentrated in the middle) at the same duration — which is exactly why convexity carries positive value whenever yield volatility is priced.

## Interview questions

1. **Derive, in one line, why a bond's price falls when yields rise.**
   Answer: Price is the sum of cash flows discounted at yield \\(y\\); raising \\(y\\) shrinks every discount factor \\(1/(1+y)^t\\), so the sum falls. Duration is just the first-order (linearized) size of that effect: \\(\Delta P \approx -D\_{\text{mod}} P \Delta y\\).

2. **Two bonds have identical duration and yield today. Why might you still prefer one?**
   Answer: Convexity (and credit, optionality, liquidity). Higher convexity is better for a long position — you gain more when yields fall a lot and lose less when yields rise a lot than the duration-only estimate would suggest, holding duration fixed.

3. **A 5-year, 6% annual coupon bond priced at par. Is its Macaulay duration bigger or smaller than 5? Why?**
   Answer: Smaller than 5. Coupons paid before year 5 pull the PV-weighted average time of cash flows below the final maturity. Only a zero-coupon bond has \\(D\_{\text{Mac}} = T\\) exactly.

4. **You hedge a long 10-year corporate bond with a short 2-year Treasury note, matched on DV01. What risk is left on the book?**
   Answer: Curve-shape risk (a 2s10s steepener or flattener hurts you even at matched DV01), convexity mismatch (the 10-year has materially more convexity), and — specific to a corporate — all of the credit spread risk, since you only hedged rate risk, not the issuer's default/spread exposure.

5. **Why can effective duration on a callable bond fall as yields fall — the opposite of a plain bond?**
   Answer: As yields drop, the issuer is increasingly likely to call and refinance cheaper, so price appreciation stalls near the call price. The price/yield curve flattens (or bends down) on the low-yield side, which is negative convexity, and the effective (option-adjusted) duration shrinks exactly when a vanilla bond's would be largest.

## Watch

- [Relationship between bond prices and interest rates](https://www.youtube.com/watch?v=I7FDx4DPapw) — Khan Academy. The inverse price/yield relationship with a simple coupon example — the foundation duration formalizes.
- [Bond convexity](https://www.youtube.com/watch?v=yOwRgWhIn_g) — Bionic Turtle. Convexity as the second moment of cash-flow timing, and why the actual curve sits above the duration tangent.

## Further reading

- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapters on duration, convexity, and key-rate duration.
- Tuckman & Serrat, *Fixed Income Securities*, for a rigorous derivation of DV01 and effective (option-adjusted) duration.
