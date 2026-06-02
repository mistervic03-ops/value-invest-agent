# 05 Decision Check

## Purpose

Make a final investment decision after completing source collection, business understanding, business evaluation, investment assessment, and thesis challenge.

This is a short decision checkpoint, not a new analysis stage. It should compress the expectation gap, owner earnings judgment, error test, and final label.

## Required Inputs

Use the completed outputs from:

- `00_required_sources.md`
- `.work/key_variables.md`
- `.work/numerical_anchors.md`
- `01_understand_business.md`
- `02_evaluate_business.md`
- `03_assess_investment.md`
- `04_challenge_thesis.md`

If any required prior step is incomplete, do not make a recommendation. State what is incomplete and what must be finished before a decision can be made.

Before making the final decision, check whether any optional skill output should update the decision. Use `skills/normalized_owner_earnings.md`, `skills/expectation_decomposition.md`, or `skills/bear_thesis_construction.md` only if the relevant judgment remains unresolved and the skill could change the final label, primary uncertainty, expectation gap, or what-would-change-my-mind triggers.

## Required Sections

Use these sections exactly.

## 1. Decision

Choose exactly one:

- `BUY`
- `WATCH`
- `PASS`
- `SELL`

Decision standards:

- `BUY`: Attractive business and valuation with favorable risk/reward after considering counterarguments.
- `WATCH`: Potentially attractive, but valuation, uncertainty, timing, or missing evidence prevents action.
- `PASS`: Insufficient quality, unattractive risk/reward, poor evidence, or better alternatives likely exist.
- `SELL`: Existing holding no longer meets the investment case, has impaired fundamentals, or offers unfavorable forward risk/reward.

State the decision label first, then give a brief plain-language explanation.

## 2. Expectation Gap

Answer in plain language:

- What does the current price seem to believe?
- What do we believe differently, based on evidence?
- Is the gap large enough to justify the decision?

Tie the answer to the 1-3 key variables.

## 3. Owner Earnings Underwritten

State the normalized owner earnings, cash flow, or economic earnings stream being underwritten.

Briefly explain the most material adjustments or limitations. Avoid model detail unless it changes the decision.

Use the checked figures from `.work/numerical_anchors.md` for valuation-sensitive numbers such as share count, enterprise value, FCF, capex, dilution, and owner earnings yield. Do not introduce new numerical anchors at the decision stage unless they are first added to `.work/numerical_anchors.md`.

## 4. Key Evidence

List only the most important evidence from prior steps. Prioritize evidence tied to the key variables and expectation gap.

## 5. Error Test

Include the strongest reason the decision may be wrong and the disconfirming evidence that would matter most.

Use the challenge work from `04_challenge_thesis.md`. Do not soften the counterargument to make the decision appear easier.

## 6. Major Unknowns

State the most important unresolved issues.

Focus on unknowns that could materially affect the decision, primary uncertainty, or expected outcome range.

Unknowns tied to key variables should usually take priority over secondary uncertainties.

## 7. Primary Uncertainty

State the single uncertainty most likely to change the investment judgment.

If no single uncertainty dominates, state that the judgment depends on multiple uncertainties and name only the most important ones.

## 8. What Would Change My Mind

State specific evidence, events, valuation changes, business deterioration, or improved information that would change the decision.

Tie these triggers to the key variables whenever possible.

Examples include:

- New evidence that changes the business quality assessment.
- A material change in valuation.
- Evidence that a critical assumption is wrong.
- Balance sheet deterioration or improvement.
- Better disclosure that resolves a major unknown.
- Competitive, regulatory, or customer behavior changes.

## Rules

- Do not introduce major new analysis.
- Do not hide uncertainty.
- Do not make a recommendation if required prior steps are incomplete.
- Do not use more precision than the evidence supports.
- The final decision must be traceable to prior steps.
- Prefer plain language over investment jargon.
- Select exactly one decision label.
- Do not present multiple decisions or conditional recommendations as the final decision.
- Do not summarize the whole workflow. Preserve only what matters for the investment judgment.

## Completion Check

This step is complete when:

- Exactly one decision label is selected.
- The expectation gap is stated.
- The owner earnings being underwritten are stated.
- The decision is supported by prior analysis and the final `.work/key_variables.md`.
- The strongest error test is included.
- Major unknowns are stated.
- Primary uncertainty is stated.
- `What Would Change My Mind` is included.
- Valuation-sensitive numbers in the decision are traceable to `.work/numerical_anchors.md`.
