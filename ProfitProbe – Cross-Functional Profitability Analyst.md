# 🔎 ProfitProbe

AI business analyst for a Myntra-style fashion e-commerce company: every department says it is on target, yet profit has fallen three quarters in a row. (Synthetic illustrative data, 24 months to Sep 2026.)

## Contribution margin by quarter (%)

## What each department reports

## Hidden cross-functional chain behind the decline

## KPI evidence vs margin change

## What-if: break the chain

Fix at:

Reverse **50**% of its rise since the decline began

## Analyst memo (LLM)

The LLM sees only the computed evidence.

Click to generate. Without LLM access the page shows a rule-based summary.

Answers are grounded in the evidence.

## Algorithm used by the analyst

1. **Integrate** 15 monthly KPIs from Marketing, HR, Operations and Finance with the profit outcome (contribution margin %).
2. **Paradox test**: score each department against its own targets (all show as met) and detect the profit decline: trailing quarters with a drop of more than 0.2 pts.
3. **Change-point**: split the margin series at the point minimizing within-segment squared error to date the onset.
4. **Detrend**: use month-over-month changes, because most KPIs trend and raw correlations are misleading.
5. **Drivers**: correlate each KPI change with margin change at lags 0–4; significant if `|r| > 2/√n`.
6. **Cross-functional graph**: draw an edge A→B when A leads B by one month, `|r| > 0.7` and A→B beats B→A by 0.15 (direction test). Revenue is excluded because it duplicates orders.
7. **Root-cause chain**: search all simple paths and keep the one with the strongest total link strength, ending at a KPI that drives margin.
8. **Quantify**: estimate each link’s slope by OLS and multiply along the chain to get the margin loss mediated by the chain; simulate fixes at any link.
9. **Narrate**: the LLM receives the evidence pack and writes a memo that states the chain, the share explained and a validation step.