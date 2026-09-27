---
title: "13. Reading a bond teaser / term sheet"
layout: default
nav_order: 14
---

# Reading a bond teaser / term sheet
{: .no_toc }

*~8 min read*

**Interview occasional**

## Why it matters

Before you ever get a full prospectus or indenture, you get a one- or two-page teaser (or a term sheet once pricing firms up). Being able to read one cold — and know exactly which line item to chase for more detail — is a practical skill that separates someone who's studied bonds from someone who's actually worked with them.

## Core concepts

- **Issuer and guarantor(s).** The legal entity actually issuing the debt, and any subsidiaries guaranteeing it. This is your first stop for a seniority/structural-subordination read — see [Seniority & capital structure](../06-seniority-capital-structure/): is this the opco or a holdco, and who's on the hook if the issuer can't pay?
- **Security / ranking.** States whether the notes are senior secured, senior unsecured, or subordinated, and (if secured) what collateral backs them. This single field often tells you more about expected recovery than the coupon does.
- **Size, tenor, and coupon/price talk.** Deal size (e.g., "$500mm"), maturity ("8-year notes"), and either a fixed coupon (if already priced) or price talk expressed as a spread over Treasuries or as a yield range (if still in bookbuilding) — see [Corporate issuance](../12-corporate-issuance/) for how that number gets set.
- **Call schedule.** Standard HY structure: non-callable for roughly half the tenor, then callable starting at a premium to par that steps down toward par over time (e.g., "NC-3, then callable at 103.5, 101.75, par"). This is exactly the schedule you'd plug into a yield-to-worst calculation — see [Yield measures](../02-yield-measures/).
- **Use of proceeds.** Refinancing existing debt, funding an acquisition, general corporate purposes, or a dividend recapitalization to sponsors — this single line is often the fastest signal for how the deal should be read (a refi is lower event risk than a debt-funded dividend to a PE sponsor).
- **Ratings (expected).** Agency ratings, often shown as "expected" if the deal prices before final agency confirmation — flag if ratings are split (see [Ratings & agencies](../05-ratings-agencies/)), since split ratings can affect index eligibility and thus which buyers can even participate.
- **Covenant summary (term sheet, more detail than a teaser).** A short bullet list flagging the restricted payments capacity, debt incurrence test, and change-of-control provisions — the term sheet won't have full indenture language, but it will tell you the basket sizes and ratio triggers, which is often enough to spot a red flag before the full document is available. See [Indentures & covenants](../07-indentures-covenants/).
- **Key financial metrics box.** Most term sheets for HY/leveraged deals include a summary of pro forma leverage (Debt/EBITDA), coverage (EBITDA/Interest), and sometimes liquidity (cash + revolver availability) — this is the fastest gut-check against the sector and rating peer set before you dig into the actual financials.

## Mental model

```
  TEASER / TERM SHEET, read in this order:

  1. Issuer / Guarantor         -> who's actually promising to pay?
  2. Security / ranking          -> where in the waterfall?
  3. Size / tenor / coupon       -> the headline economics
  4. Call schedule                -> what's the REAL yield (yield to worst)?
  5. Use of proceeds              -> refi (low event risk) vs. LBO/div-recap (high)?
  6. Ratings (expected)           -> IG or HY? split? index-eligible?
  7. Covenant summary             -> how much can they lever up / dividend out later?
  8. Leverage / coverage metrics  -> sanity-check vs. sector peers and the rating
```

## Interview questions

1. **You're handed a one-page teaser for a new HY deal. What are the first three things you check, in order, and why that order?**
   Answer: Issuer/guarantor structure and security/ranking first (determines what you actually own a claim on and where it sits), then use of proceeds (tells you the event-risk profile — refi vs. acquisition-funded vs. dividend recap), then the call schedule and price talk (needed to even compute a meaningful yield to worst). Financial ratios and covenant detail come after you understand the structural basics, not before.

2. **A term sheet shows the notes are "senior secured, guaranteed by all domestic restricted subsidiaries, first-lien on substantially all assets." What does this tell you relative to an unsecured bond from the same sponsor's other portfolio company?**
   Answer: This bond sits ahead of unsecured creditors on the pledged collateral pool and benefits from guarantees pulling subsidiary assets into its claim, both of which materially improve expected recovery in a default scenario versus a comparable unsecured structure — you'd expect it to price tighter, all else equal, purely on structural grounds.

3. **The teaser says "proceeds to fund a dividend to existing sponsor" versus another deal that says "proceeds to refinance the 2027 notes." How does your read of these two deals differ before you've looked at a single financial metric?**
   Answer: The dividend recap deal directly increases leverage without adding any offsetting operating value — pure re-leveraging for sponsor benefit, a yellow flag worth pricing extra spread for. The refinancing deal is largely leverage-neutral (old debt out, new debt in, similar amount) and carries much lower event risk, since there's no change to the underlying credit profile beyond term/coupon.

4. **A term sheet shows a call schedule "NC-4, then callable at 104.25 stepping to par by year 7" on an 8-year bond priced at a 7% coupon. Why does this matter more than the headline coupon for estimating realistic return?**
   Answer: If rates or the issuer's credit improve enough that refinancing below 7% becomes attractive to the issuer, they will call at the first opportunity (year 4, at 104.25) rather than let the bond run to the 8-year maturity — so yield to worst (likely the yield-to-call scenario) is the number that actually describes achievable return, not the yield to the stated 8-year maturity.

5. **Two competing term sheets show identical coupon, tenor, and rating, but one has meaningfully larger restricted payments and debt incurrence baskets. What does that tell you, and how should it affect relative pricing?**
   Answer: Larger baskets mean the issuer has more contractual room to lever up further or pay dividends to equity before tripping a covenant — weaker bondholder protection for the same headline terms. All else equal, that bond should demand a wider spread to compensate for the additional flexibility the issuer has retained to take actions that could hurt existing bondholders down the line.

## Further reading

- Fabozzi, *Bond Markets, Analysis, and Strategies*, chapter on prospectus and offering document structure.
- Moyer, Stephen G., *Distressed Debt Analysis: Strategies for Speculative Investors*, on reading offering documents for structural red flags.
