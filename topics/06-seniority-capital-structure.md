---
title: "06. Seniority & capital structure"
layout: default
nav_order: 7
---

# Seniority and capital structure
{: .no_toc }

*~9 min read*

**🎯 Interview frequent**

## Why it matters

When an issuer defaults, recovery is not split evenly — it's paid out strictly according to a waterfall determined by seniority and collateral. Understanding where a specific bond sits in that stack is the single most decision-relevant fact for a credit investor, more than the headline coupon or even the issuer's overall rating.

## Core concepts

- **The waterfall, top to bottom.** In a liquidation or reorganization, proceeds pay claims in this order: (1) secured creditors up to the value of their collateral, (2) administrative/priority claims (bankruptcy costs, certain employee/tax claims), (3) senior unsecured debt, (4) subordinated/junior debt, (5) preferred equity, (6) common equity. Each class must be paid in full (or waive its claim) before the next class receives anything — the **absolute priority rule**.
- **Secured vs. unsecured.** Secured debt is backed by specific collateral (a mortgage on real assets, a pledge of receivables, equipment). If the issuer defaults, secured lenders can foreclose on or claim that specific collateral before unsecured creditors get anything from the general asset pool. First-lien vs. second-lien secured debt further ranks claims on the *same* collateral pool.
- **Senior unsecured is the default corporate bond.** Most investment-grade corporate bonds are senior unsecured: no specific collateral pledge, but ranked ahead of subordinated debt and equity against the general asset pool. "Senior" here means relative to other unsecured claims, not equivalent to secured.
- **Subordinated / junior debt** contractually agrees to be paid after senior unsecured creditors, in exchange for a higher coupon. Structurally subordinated debt is a related but distinct concept: debt issued at a holding company, structurally behind operating-company debt because operating assets and cash flows sit below the holdco and must first satisfy opco creditors.
- **Guarantees change the picture.** A subsidiary guarantee can pull a holdco bond's effective claim up to par with opco creditors on that subsidiary's assets; the absence of guarantees is exactly why structural subordination matters so much in multi-entity corporate groups (private equity-owned issuers especially).
- **Recovery in practice tracks this stack closely, but not perfectly.** Historical recovery rates by seniority (roughly: secured loans highest, senior unsecured bonds in the middle, subordinated/unsecured notes lowest) are the empirical evidence that the waterfall isn't just legal theory — see [Default & recovery](../09-default-recovery/). Fulcrum security analysis — figuring out which tranche is the one that converts into the reorganized equity — is the practical, forward-looking application of this whole framework.
- **Equity is always last, and that's the point.** Equity holders have unlimited upside but are wiped out first in a bad outcome — which is exactly why distressed equity behaves like an out-of-the-money call option on the enterprise value, a framing corporate finance and credit desks share.

## Mental model

```
  Enterprise Value in default, paid out top to bottom:

  1. Secured debt (1st lien, then 2nd lien)  <- paid from pledged collateral first
  2. Administrative / priority claims
  3. Senior unsecured debt
  4. Subordinated debt
  5. Preferred equity
  6. Common equity                            <- residual claim, paid last (or nothing)

  Structural subordination (holdco/opco):

  HoldCo bonds  --- structurally behind ---  OpCo creditors
       |                                          |
   claim on HoldCo's assets              claim on OpCo's assets directly
   (mainly OpCo equity, AFTER OpCo debt is paid)
```

## Interview questions

1. **An issuer has $500mm senior secured debt, $300mm senior unsecured debt, and enterprise value in default of $600mm. Roughly how does that get split (ignoring administrative costs)?**
   Answer: Secured debt is paid in full first (to the extent collateral value supports it) — assume $500mm recovered in full. The remaining $100mm goes to senior unsecured, which recovers roughly 33% ($100mm / $300mm) under absolute priority; equity gets nothing.

2. **What is structural subordination, and why does it matter for a bond issued by a holding company?**
   Answer: A holdco's only real asset is typically its equity stake in operating subsidiaries. If the opco has its own debt, opco creditors get paid from opco's cash flows and assets first; only residual value flows up to the holdco as equity distributions. So holdco bondholders are effectively behind opco creditors even without a contractual subordination clause — purely a function of corporate structure.

3. **Why would a private equity sponsor's portfolio company issue debt at the opco level rather than the holdco level, all else equal?**
   Answer: OpCo-level debt typically prices tighter (lower coupon) because it has a direct claim on operating assets and cash flow, ahead of any holdco debt. It's also often the collateral pool for the LBO's senior secured facilities. HoldCo debt (often PIK toggle notes) is priced wider to compensate for structural subordination and is used because it doesn't burden opco's credit agreement covenants.

4. **What is a "fulcrum security," and why do distressed investors care about identifying it?**
   Answer: The fulcrum security is the most senior tranche in the capital structure that is not paid in full in a restructuring — the class whose recovery is impaired enough that it typically converts into the reorganized company's new equity. Identifying it tells a distressed investor which tranche actually controls (or benefits from) the post-reorganization outcome, and is the basis for "loan-to-own" and other distressed strategies.

5. **Two senior unsecured bonds from the same issuer, same seniority, but one has a subsidiary guarantee and the other doesn't. Why might they trade at different spreads?**
   Answer: The guaranteed bond has a direct claim on the guarantor subsidiary's assets, closing the structural subordination gap; the unguaranteed bond only has a claim on the issuing entity. If meaningful assets or cash flow sit at the guaranteeing subsidiary, the guaranteed bond should recover more in default and trade tighter, all else equal.

## Watch

- [Session 17: The Debt/Equity Trade off](https://www.youtube.com/watch?v=wk6yec9pGAs) — Prof. Aswath Damodaran (NYU Stern). Debt as a senior, contractual claim versus equity as the residual claim — the theory underlying the waterfall.
- [Session 24: Distressed Equity as an option](https://www.youtube.com/watch?v=L2luFJSpQo8) — Prof. Aswath Damodaran (NYU Stern). Why equity, as the last claim in the stack, behaves like an out-of-the-money call option on enterprise value.

## Further reading

- Moyer, Stephen G., *Distressed Debt Analysis: Strategies for Speculative Investors*, on capital structure mapping and fulcrum security identification.
- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapter on corporate bond seniority and security provisions.
