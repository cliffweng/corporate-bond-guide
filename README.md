# Corporate Bond Guide

A practical corporate bond and credit study guide for builders and credit/FI desk interview candidates — covering price/yield mechanics, duration and convexity, credit spreads, ratings, capital structure, and default/recovery with clean math and desk-level rigor.

**Live site:** https://cliffweng.github.io/corporate-bond-guide/
*(Also accessible via custom domain path: [cliffweng.com/corporate-bond-guide/](https://cliffweng.com/corporate-bond-guide/))*

## Roadmap

14 topics, one file each under [`topics/`](topics/), ordered foundational → applied:

1. Bond basics (price/yield)
2. Yield measures (YTM, current, spot/par, etc.)
3. Duration & convexity
4. Credit spreads
5. Ratings & agencies
6. Seniority & capital structure
7. Indentures & covenants (lite)
8. Investment-grade vs. high yield
9. Default & recovery
10. Relative value / spread analysis
11. Interest-rate risk vs. credit risk
12. Corporate issuance process
13. Reading a bond teaser / term sheet
14. Interview patterns

## Interview hotspots

Every topic page carries a badge (🎯 Frequent / Occasional) so you know where to spend prep time. If you're short on time, prioritize these:

- **Bond basics & yield measures** — the reflex every other topic assumes; interviewers probe why price and yield move inversely and the difference between YTM, spot rates, and yield to worst.
- **Duration & convexity** — the most-tested quantitative topic; expect a whiteboard derivation of \(\Delta P/P \approx -D\_{\text{mod}}\Delta y + \tfrac12\text{Conv}(\Delta y)^2\) and why callable bonds can go negatively convex.
- **Credit spreads** — nominal vs. Z-spread vs. OAS, and the risk-neutral-vs-real-world PD wedge behind every spread.
- **Seniority & capital structure** — waterfall mechanics, structural subordination, and fulcrum-security identification.
- **Indentures & covenants** — maintenance vs. incurrence covenants and how weak baskets let issuers prime existing bondholders.
- **Default & recovery** — expected loss decomposition (\(PD \times LGD \times EAD\)) and why recovery is cyclical, not a fixed 40%.
- **Rate risk vs. credit risk** — decomposing bond risk into separately hedgeable components, and why IG and HY sit at opposite ends of that spectrum.
- **Interview patterns** — end-to-end price/duration walkthroughs, spread-to-PD conversions, and recovery-waterfall case math in under 10 minutes.

**Occasional** (still essential, less likely to anchor an entire round): ratings & agencies, IG vs. HY, corporate issuance process, reading a term sheet.

This split reflects the rigorous, desk-level demands of credit research, leveraged finance, and fixed-income interviews.

## How to use this guide

Each topic page is designed to be read in **~10 minutes** and follows the same structure: why it matters, core concepts with explicit formulas, a mental model (ASCII diagram or crisp intuition), 4–5 interview questions with detailed answer keys, and a short list of verified YouTube videos where a good one exists. Read them in order, or jump straight to what you need. No backend, no market data feed, no auth, no sign-up — just read the pages.

## How to contribute

See [CONTRIBUTING.md](CONTRIBUTING.md). In short: one topic per file, keep it under ~10 minutes to read, and only link to sources (especially YouTube videos) you've personally verified exist. Open an issue before proposing new topics or restructuring the curriculum.

## Decisions

These are the product locks this guide was built against — echoed here so future contributors don't accidentally relitigate them:

- **Audience**: builders and interview candidates preparing for credit/FI desk interviews. Bias toward credit/FI interview rigor (spreads, duration, covenants) over full rates-desk modeling or structured credit (CDOs).
- **Time-boxed**: every topic is readable in 10 minutes or less. Depth is balanced with interview scannability; further reading links point to standard fixed-income texts (Fabozzi, Tuckman & Serrat).
- **Learning + interview prep in one page**: each topic pairs core bond/credit mechanics with interview questions, rather than splitting them into separate tracks.
- **Real links only**: every YouTube link is verified to exist (via oEmbed) before being added. No invented URLs, ever. A few topics intentionally have no video where no verified, on-topic one exists.
- **Static site, GitHub Pages, Just the Docs**: no backend, no auth, no paid data, no quizzes/progress tracking.

## Enabling GitHub Pages

Just the Docs is configured via `_config.yml` (remote theme). After this lands on `main`:

1. Repo **Settings → Pages**.
2. **Build and deployment → Source**: **Deploy from a branch**.
3. Branch: `main` / folder: `/ (root)`.
4. Save. Site publishes to https://cliffweng.github.io/corporate-bond-guide/

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

## License

[MIT](LICENSE)
