# personal-spo

**Supply path optimization, applied to your own attention.**

In ad tech, *supply path optimization* (SPO) means cutting the intermediaries between a buyer and the inventory they actually want: fewer hops, less fee leakage, more of each dollar reaching the screen. This is the same audit for a personal tool stack. Your attention is the inventory, and every app, agent and memory layer is a hop that has to earn its place.

**[Open it →](https://patrickcarmichael.github.io/personal-spo/)**

## How it scores

Each tool gets 1–5 ratings for value, uniqueness, reliability, integration and portability, minus an "attention tax" and a cost penalty:

```
score = (0.28·value + 0.22·unique + 0.20·reliable + 0.15·integration + 0.15·portable) / 5 × 100
        − 6 × (attention − 1)
        − min(15, monthly cost / 20)
```

The result is clamped to 0–100 and rounded to a whole number.

Verdicts are checked in this order, first match wins:

| Verdict | Rule |
|---|---|
| **Specialist** | uniqueness ≥ 4 but score < 60: odd, but irreplaceable |
| **Keep** | score ≥ 75 |
| **Consolidate** | score 58–74: duplicates a route you already have (a score of 58–59 with uniqueness ≥ 4 is Specialist instead) |
| **Sunset** | everything else |

The summary cards track active paths, monthly spend, keep/specialist count and potential savings (the monthly cost of Consolidate and Sunset rows). It borrows one more ad-tech idea, the *working media ratio*: the share of time and money that reaches an actual outcome instead of setup, migration and deciding which tool should ask which other tool.

## Details

- One self-contained `index.html`, no build step, no dependencies.
- Your ratings stay in your browser (`localStorage`). Nothing is sent anywhere.
- Export to CSV, or reset to the generic sample stack.
