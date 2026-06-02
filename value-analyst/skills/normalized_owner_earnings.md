# Normalized Owner Earnings Skill

## Purpose

Use this optional deep-analysis skill to determine what owner earnings the analyst is actually underwriting when headline earnings, FCF, non-GAAP metrics, capex, SBC, working capital, cyclicality, M&A, or other distortions make reported numbers unreliable.

This is not a default workflow stage, a full financial model, or a generic valuation template. Invoke it only when owner earnings quality can materially affect the investment judgment.

Before invoking, answer:

> What decision could change if normalized owner earnings are higher or lower than the headline number?

If the answer is unclear, do not invoke the skill.

## Invocation Triggers

Use this skill when one or more of the following is true:

- GAAP earnings and FCF diverge materially.
- SBC, restructuring, acquisition accounting, litigation, impairments, working capital swings, tax items, or non-GAAP adjustments are material.
- Maintenance versus growth capex matters to the judgment.
- Recent earnings are cyclically depressed or cyclically elevated.
- The `BUY` / `WATCH` / `PASS` decision depends heavily on normalized owner earnings yield.
- Management adjusted metrics are tempting but potentially misleading.
- Current FCF may not represent durable owner earnings.

## Non-Triggers

Do not use this skill when:

- FCF and earnings are stable, clean, and already sufficient for judgment.
- Owner earnings is not material to the decision.
- Source data is too weak to normalize responsibly.
- The analyst merely wants more precision.
- The output would add model detail without changing judgment.

## Required Inputs

Use already-checked workflow artifacts and primary filings. Required inputs include:

- `.work/numerical_anchors.md`
- Income statement, cash flow statement, and balance sheet
- SBC
- Capex
- Working capital
- Debt, cash, and interest expense
- Material one-time or unusual items
- Management non-GAAP reconciliations
- Segment data if it affects normalized economics

If valuation-sensitive numbers are not traceable in `.work/numerical_anchors.md`, stop and fix the anchors before using this skill.

## Workflow

1. Choose the least distorted starting point:
   - net income
   - NOPAT
   - EBIT after tax
   - FCF
   - management FCF
2. Identify reported and cash-flow distortions:
   - SBC, restructuring, litigation, impairments, acquisition costs, working capital, tax, capex timing, cyclicality, financing items, and non-GAAP adjustments
3. Classify each adjustment:
   - recurring economic cost
   - temporary distortion
   - growth investment
   - accounting noise
   - unknowable
4. Treat SBC as a real economic cost unless there is a strong reason not to.
5. Distinguish maintenance capex from growth capex only when evidence supports it.
   - If evidence is weak, use a conservative range.
6. Separate peak or trough cycle effects from normalized economics.
7. Produce a conservative owner earnings range.
   - Prefer a range over a point estimate.
   - Do not adjust numbers to reach a desired decision.
8. Translate the range into owner earnings yield or implied multiple using checked price or EV anchors.
9. State whether the range supports, weakens, or changes the investment judgment.

## Output Format

Keep the output short. Use this format:

```text
## Normalized Owner Earnings

Invocation reason:

Starting metric:

Main distortions:

Adjustments accepted:

Adjustments rejected:

Normalized owner earnings range:

Current price / EV implied multiple or yield:

Key sensitivity:

Decision impact:

Updates required:
- Numerical anchors:
- Owner earnings section:
- Expectation gap:
- Key variables:
- Primary uncertainty:
- Final decision:
```

Do not paste the full output into the final memo unless it materially improves clarity. Compress the conclusion into the existing owner earnings and expectation-gap sections.

## Failure Modes

- Using management adjusted EBITDA as owner earnings.
- Ignoring SBC.
- Excluding all growth capex too aggressively.
- Treating working capital benefits as recurring.
- Using peak earnings as normalized earnings.
- Over-normalizing a structurally declining business.
- Producing false precision.
- Adjusting numbers to justify a desired conclusion.
- Treating financing-driven per-share improvement as business owner earnings.

## Feedback Into Main Workflow

This skill feeds back into existing workflow artifacts only when it changes judgment.

- Numerical anchors: add or revise only valuation-sensitive owner earnings inputs, calculations, and caveats.
- Owner earnings section: revise the underwritten range if headline earnings or FCF were misleading.
- Expectation gap: update if the revised range changes whether the current price is attractive.
- Key variables: reorder or revise if owner earnings quality becomes more or less decision-critical.
- Primary uncertainty: update if the main uncertainty becomes earnings quality, capex intensity, SBC, cyclicality, working capital, or M&A economics.
- Final decision: change only if the revised owner earnings range changes risk/reward after the thesis challenge.

The skill should clarify the cash economics being underwritten. It should not create precision that the evidence cannot support.
