---
title: "07. Indentures & covenants lite"
layout: default
nav_order: 8
---

# Indentures and covenants (lite)
{: .no_toc }

*~9 min read*

**🎯 Interview frequent**

## Why it matters

The indenture is the actual contract a bondholder owns — coupon and maturity are just headline terms; covenants are what determine whether the issuer can quietly re-lever, sell the collateral, or upstream cash to shareholders before you get repaid. Credit analysts spend real time in the actual document; interviewers want to see you know which covenants matter and why, not that you've memorized boilerplate.

## Core concepts

- **The indenture is the trust agreement**, typically between the issuer and a trustee acting on behalf of all bondholders collectively. It specifies events of default, remedies, and — critically — the covenants, which are the ongoing promises the issuer makes for as long as the bonds are outstanding.
- **Maintenance covenants vs. incurrence covenants.** A maintenance covenant must be satisfied continuously (tested every quarter regardless of issuer action) — common in bank loans, rare in most HY bonds since the mid-2000s. An incurrence covenant is only tested when the issuer *takes an action* (issuing new debt, paying a dividend, making an acquisition) — the dominant structure in modern high-yield bond indentures, and materially weaker protection because a static, do-nothing issuer never trips it.
- **Restricted payments covenant.** Caps dividends, share buybacks, and other value leaked to equity holders, usually via a "build-up basket" tied to cumulative net income/EBITDA since issuance, plus specified baskets. This is the covenant that determines whether a sponsor can dividend cash out of a leveraged issuer.
- **Debt incurrence covenant.** Limits additional borrowing, typically via a leverage ratio test (e.g., "no additional debt unless pro forma Debt/EBITDA ≤ 5.0x") or a fixed-charge coverage ratio test, often layered with specific baskets (permitted refinancing debt, permitted acquisition debt) that create real headroom regardless of the ratio test.
- **Negative pledge / limitation on liens.** Restricts the issuer from pledging assets as collateral to other creditors, which would structurally or contractually subordinate the existing unsecured bondholders. A weak or basket-riddled negative pledge is exactly how many "unsecured" HY issuers later prime existing bondholders with new secured debt (a live, current theme in liability management exercises).
- **Change of control put.** Gives bondholders the right to sell the bond back to the issuer (typically at 101% of par) if a defined change-of-control event occurs — protection against the issuer being acquired/re-levered by a buyer who dramatically increases leverage post-close.
- **Cross-default and cross-acceleration.** A default on one debt instrument triggers default (cross-default) or the *right* to accelerate (cross-acceleration, a slightly softer version) on other debt instruments — this is why a single covenant breach can cascade across an issuer's entire capital structure almost instantly.
- **Covenant-lite (cov-lite).** Refers to loans (increasingly, and by extension the broader capital structure) that drop maintenance covenants entirely, leaving only incurrence-based tests. Cov-lite's rise since the mid-2010s is a standing interview topic on "why is HY/leveraged loan documentation weaker today than pre-2008."

## Mental model

```
  Maintenance covenant:  tested EVERY quarter, regardless of issuer behavior
       -> issuer must stay compliant continuously (bank loan style)

  Incurrence covenant:   tested ONLY when issuer takes an action
       -> a passive issuer never trips it, even if leverage has drifted way up
       -> "weaker" protection, dominant in modern HY bond indentures

  Covenant package, ranked by what bondholders actually rely on:
  Negative pledge (no new liens) > Debt incurrence limit > Restricted payments
  > Change-of-control put > (everything else is largely boilerplate)
```

## Interview questions

1. **What's the practical difference between a maintenance covenant and an incurrence covenant, and why does it matter for a deteriorating credit?**
   Answer: A maintenance covenant is tested every period regardless of what the issuer does, so a slow, organic decline in EBITDA alone can trip it and force a renegotiation. An incurrence covenant is only tested on issuer-initiated actions (new debt, dividends), so a passive issuer whose credit quality erodes never breaches it — bondholders get no early contractual trigger to renegotiate or reprice risk.

2. **A private equity sponsor wants to dividend cash out of a portfolio company that issued HY bonds. What covenant governs whether they can, and how is the capacity typically sized?**
   Answer: The restricted payments covenant. Capacity is usually built from a formula basket — often something like a percentage of cumulative net income (or EBITDA-based build-up) since the bonds were issued, plus specific carve-out baskets (e.g., a fixed-dollar "general" basket) — so the sponsor's ability to dividend grows as the company generates cumulative earnings, subject to also passing a leverage ratio condition in many indentures.

3. **Why does a weak negative pledge covenant matter even if the debt incurrence covenant looks strong?**
   Answer: A weak negative pledge lets the issuer grant liens on assets to new creditors, effectively priming existing unsecured bondholders even without violating the debt incurrence test (which limits *amount* of debt, not *ranking*). This is the mechanism behind many recent "liability management exercises" where an issuer moves assets to an unrestricted subsidiary and pledges them to new secured lenders, subordinating existing bondholders without technically breaching either covenant.

4. **What is a change-of-control put, and what specific risk does it protect against that leverage covenants don't?**
   Answer: It gives bondholders the right to require the issuer to repurchase the bonds (typically at 101%) upon a defined change-of-control event. It protects against a scenario where a new owner (e.g., an LBO sponsor) dramatically re-levers the company post-acquisition — a risk that a static leverage covenant tested only at issuance wouldn't have caught, since the covenant package was written for the *old* owner's credit profile.

5. **Explain cross-default in one sentence, and why a single covenant breach can become an existential event for an issuer.**
   Answer: A default (or, under cross-acceleration, an actual acceleration) on one debt instrument automatically constitutes a default under other debt agreements containing cross-default language, so a breach on a relatively small facility can immediately put the issuer's entire capital structure in default and trigger acceleration rights across all creditors simultaneously — which is exactly why issuers move fast to cure or waive even seemingly minor breaches.

## Watch

- [Session 21: Debt Design](https://www.youtube.com/watch?v=4glb7Ze5ZuI) — Prof. Aswath Damodaran (NYU Stern). Matching debt terms, duration, and covenant structure to the borrower's cash-flow profile and assets.

## Further reading

- Moyer, Stephen G., *Distressed Debt Analysis: Strategies for Speculative Investors*, chapters on covenant analysis and liability management.
- Standard & Poor's / LSTA publish public primers on covenant-lite loan structures and maintenance-vs-incurrence testing conventions.
