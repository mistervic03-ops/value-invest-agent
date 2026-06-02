# Expectation Decomposition Skill

## Purpose

Use this optional deep-analysis skill to decompose what the current price appears to believe and identify the expectation that most drives the investment judgment.

This is not a default workflow stage. Invoke it only when it can materially improve the decision by clarifying the expectation gap, key variable ranking, primary uncertainty, or final decision.

Before invoking, answer:

> What investment judgment could this skill change?

If the answer is unclear, do not invoke the skill.

## Invocation Triggers

Use this skill when one or more of the following is true:

- The business is high quality but the valuation appears demanding.
- The decision is near a `BUY` / `WATCH` boundary.
- The decision is near a `WATCH` / `PASS` boundary.
- The valuation appears expensive or cheap, but the reason is unclear.
- Multiple key variables exist and the decision-dominant expectation is unclear.
- The current price requires assumptions that should be made explicit before deciding.

## Non-Triggers

Do not use this skill when:

- Business understanding is still weak.
- Source quality or numerical anchors are not reliable enough.
- Valuation is obviously unattractive without deeper work.
- The analyst only wants more detail and cannot name the decision impact.
- The output would duplicate `03_assess_investment.md` without changing judgment.

## Required Inputs

Use already-completed workflow artifacts. Do not collect new sources unless a missing source is necessary to interpret a price-implied expectation.

Required:

- `.work/key_variables.md`
- `.work/numerical_anchors.md`
- `01_understand_business.md`
- `02_evaluate_business.md`
- `03_assess_investment.md`
- Current price, market capitalization, enterprise value, and owner earnings or FCF yield from `.work/numerical_anchors.md`
- Evidence-supported views on growth, margins, reinvestment, cash conversion, durability, balance sheet, and normalized owner earnings

If the numerical anchors are not traceable, stop and fix them before using this skill.

## Workflow

1. State the gating question and why the skill is being invoked.
2. Translate the valuation into 2-4 anchors:
   - owner earnings yield or FCF yield
   - implied earnings or cash flow multiple
   - EV / revenue, EV / EBIT, or another relevant multiple
   - any balance sheet adjustment that changes the interpretation
3. List 3-5 price-implied expectation candidates.
   - Express them as interpretations, not facts.
   - Focus on growth, margin, reinvestment, cash conversion, durability, and terminal quality.
4. Compare each candidate with evidence-supported expectations.
   - Mark each as supported, uncertain, weakly supported, or contradicted.
   - Separate recent performance, management guidance, and durable evidence.
5. Identify the decision-dominant expectation.
   - Choose the expectation most likely to change the investment decision.
   - If no single expectation dominates, name the smallest set that does.
6. Assess the expectation gap.
   - Is the gap positive, negative, or too uncertain?
   - Is it large enough after downside risk, balance sheet risk, and opportunity cost?
7. State the decision impact.
   - Strengthen, weaken, or leave unchanged the current investment judgment.
   - Do not force a decision change.

## Output Format

Keep the output short. Use this format:

```text
## Expectation Decomposition

Invocation reason:

Valuation anchors:

Price-implied expectation candidates:

Evidence-supported comparison:

Decision-dominant expectation:

Expectation gap:

Decision impact:

Updates required:
- Key variables:
- Expectation gap:
- Primary uncertainty:
- Final decision:
```

Do not paste this full output into the final memo unless it materially improves clarity. Compress the conclusions into the existing memo sections.

## Failure Modes

- Treating market expectations as facts instead of estimates.
- Adding a complex model that creates false precision.
- Using multiples as a substitute for explicit expectations.
- Giving every variable equal importance.
- Smuggling in optimistic assumptions to justify a desired conclusion.
- Ignoring owner earnings quality when interpreting valuation.
- Repeating the investment assessment without changing the judgment.
- Calling the skill because the analyst wants more detail rather than because a decision could change.

## Feedback Into Main Workflow

This skill feeds back into existing workflow artifacts only when it changes judgment.

- Key variables: reorder or revise `.work/key_variables.md` if the decision-dominant expectation differs from the prior ranking.
- Expectation gap: revise `03_assess_investment.md` or the final memo only if the gap becomes clearer, larger, smaller, or more uncertain.
- Primary uncertainty: update `05_make_decision.md` if the skill identifies a sharper uncertainty than the prior one.
- Final decision: change the decision only if the clarified expectation gap changes risk/reward after the thesis challenge.

The skill should reduce uncertainty. It should not make the analysis longer unless it makes the investment judgment sharper.
