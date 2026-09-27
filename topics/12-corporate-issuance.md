---
title: "12. Corporate issuance process"
layout: default
nav_order: 13
---

# Corporate issuance process
{: .no_toc }

*~8 min read*

**Interview occasional**

## Why it matters

Every bond you analyze secondary-market started as a primary deal that a syndicate desk built, priced, and allocated over the course of days. Understanding that process — why a deal is announced, how it's priced, and who ends up holding it — explains a lot of otherwise-confusing secondary market behavior, including new-issue concessions and post-deal price action.

## Core concepts

- **Why companies issue bonds vs. draw on a revolver or issue equity.** Bonds lock in a fixed, long-dated cost of capital and don't dilute existing shareholders (unlike equity), while typically carrying lower cost and more flexibility than a fully drawn bank facility for permanent, long-term capital needs. The decision interacts directly with the capital-structure and leverage trade-offs a corporate finance analyst would recognize as the debt-vs-equity choice, applied specifically to the tenor and covenant terms of a bond.
- **Registered vs. Rule 144A offerings.** A registered offering is SEC-registered and can be sold broadly, including to retail; most HY and many crossover corporate deals in the US are instead sold via **Rule 144A** to qualified institutional buyers (QIBs) — faster to execute, less disclosure burden, but the bonds can only trade among QIBs until an exchange offer registers them for broader resale (a "144A-for-life" bond simply never does the exchange, less common but exists).
- **The syndicate process.** The issuer mandates one or more investment banks as underwriters/bookrunners. They build an order book: announce size and initial price talk, take investor orders (indications of interest), and revise price talk tighter as demand builds — a well-oversubscribed book lets the issuer tighten pricing multiple times before final terms are set.
- **New issue concession and allocation.** As covered in [Relative value](../10-relative-value-spreads/), the final priced spread typically sits somewhat wide of the issuer's existing secondary curve — compensation for taking down size in one day. Allocations to investors are influenced by order size, existing relationship with the underwriter, and (informally) how "real" versus opportunistic/flip-oriented the order is perceived to be.
- **Use of proceeds and market windows.** Deals are timed around market conditions (avoiding earnings blackout periods, FOMC weeks, or broad risk-off episodes) and are often explicitly tied to a use of proceeds: refinancing existing debt approaching maturity, funding an acquisition (a "bridge-to-bond" takeout), or general corporate purposes. Refinancing deals typically price more easily than acquisition-funding deals, which can carry event risk if the underlying M&A deal is contested or falls through.
- **Credit rating engagement happens in parallel.** The issuer (or its advisors) engages rating agencies before or during the roadshow so a rating is available (or reaffirmed/reviewed) by pricing — a new or lower-than-expected rating can materially move final price talk, which is why rating agency dialogue is a critical, and often confidential, workstream running alongside the bookbuilding process.
- **Post-pricing settlement and secondary trading.** Bonds typically settle T+3 to T+5 for a new issue (longer than the T+1/T+2 typical of seasoned secondary trades), and "grey market" or "when-issued" trading can occur between pricing and settlement, giving an early read on whether the deal was priced too cheap or too rich relative to where accounts actually want to hold it.

## Mental model

```
  Issuer decision: bond vs. loan vs. equity
        |
        v
  Mandate underwriter(s) -> Rating agency engagement (parallel)
        |
        v
  Announce deal: size + initial price talk (IPT)
        |
        v
  Build order book -> revise price talk tighter as demand grows
        |
        v
  Price final terms (coupon, spread, size)  <- new issue concession baked in here
        |
        v
  Allocate to investors -> Settle (T+3 to T+5) -> Secondary trading begins
        |
        v
  Concession typically compresses over following days/weeks (see topic 10)
```

## Interview questions

1. **Why would an issuer choose a Rule 144A offering over a fully SEC-registered bond, and what's the trade-off?**
   Answer: 144A is faster to execute and carries a lighter disclosure/registration burden, which matters for issuers who want to move quickly (e.g., funding a time-sensitive acquisition) or who don't want to go through full SEC registration. The trade-off is a smaller initial buyer universe (QIBs only) until/unless an exchange offer registers the bonds for broader resale, which can mean somewhat wider pricing to compensate the initial buyer base for that liquidity restriction.

2. **A new bond deal is announced with initial price talk of "Treasuries + 250bp area," and the book is 4x oversubscribed within hours. What happens next, and why?**
   Answer: The underwriters will typically revise price talk tighter (e.g., to +225bp) to take advantage of strong demand while still leaving enough concession to clear the deal and leave investors a reasonable break in secondary trading — issuers want the tightest sustainable pricing, but underwriters also want the deal to trade well afterward to protect their franchise with investors for future deals.

3. **Why do refinancing-driven bond deals typically price more smoothly than acquisition-financing deals?**
   Answer: A refinancing deal has no binary "will the underlying transaction actually close" event risk — the issuer's credit profile is essentially unchanged pre- and post-deal. An acquisition-financing deal carries deal-completion risk (regulatory approval, financing contingencies, possible renegotiation or break fee) and often changes the pro forma leverage/credit profile materially, both of which investors need to underwrite and price in, typically demanding a larger concession.

4. **What does "grey market" or "when-issued" trading tell you, and when does it happen?**
   Answer: It's trading that occurs after a deal is priced but before it formally settles, giving an early, real-money read on secondary demand at the just-set terms. If the bond trades up meaningfully in grey market, it suggests the deal was priced with generous concession (cheap to the issuer's cost, rich opportunity for allocated investors); trading flat or down suggests the deal was priced tight to fair value or demand was weaker than the order book implied.

5. **Why might a company engage rating agencies confidentially well before a public deal announcement?**
   Answer: The final or reaffirmed rating materially affects investor demand and achievable pricing, so the issuer wants rating clarity (or at least a strong sense of where it will land) before committing to a public announcement and IPT — an unexpected downgrade mid-process, after a deal is announced, can force an embarrassing repricing or even a pulled deal.

## Watch

- [Introduction to bonds](https://www.youtube.com/watch?v=Qh-M3_L4xYk) — Khan Academy. Why a company issues a bond in the first place — the starting point of the whole process.
- [Session 6: Cost of Debt and Capital](https://www.youtube.com/watch?v=N_FH89DCdGs) — Prof. Aswath Damodaran (NYU Stern). How the issuer's cost-of-debt calculus (rating, term, structure) feeds directly into the terms a deal is designed and priced around.

## Further reading

- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapter on the primary market issuance process.
- SIFMA publishes public overviews of US corporate bond market structure and standard settlement conventions.
