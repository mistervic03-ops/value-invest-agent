# Update Workflow

## Purpose

Revisit an existing investment judgment without redoing the entire analysis.

This workflow is for judgment tracking after a prior investment memo already exists. Use the prior memo as the baseline, identify what changed, and decide whether the prior decision should change.

The goal is not a new business understanding, a full valuation refresh, or a comprehensive memo. The goal is to preserve whether new evidence changes the investment judgment.

## Required Inputs

Use the most recent relevant prior artifacts:

- Prior `investment_memo.md`
- Prior `reasoning_summary.md`, if available
- Prior `source_log.md`, if needed to understand the evidence base
- New filings, earnings releases, transcripts, presentations, market data, or other evidence since the prior memo

If the prior memo is unavailable, do not use this workflow. Run the full analysis workflow instead.

If new evidence is too limited to update the judgment responsibly, state that limitation and keep the decision impact inconclusive.

If new evidence makes the prior decision-dominant variable unclear or obsolete, use `skills/expectation_decomposition.md`. If new evidence materially changes cash conversion, capex, SBC, working capital, cyclicality, or other owner earnings distortions, use `skills/normalized_owner_earnings.md`. Use optional skills only when they can change the decision impact.

## Scope

Focus only on changes since the prior memo.

Do not repeat:

- Business model explanation
- Full business quality assessment
- Full valuation work
- Full owner earnings build
- General risk lists
- Source summaries that do not change the judgment

Repeat prior conclusions only when needed to establish the baseline.

## Required Sections

Use these sections exactly.

## 1. Previous Decision

State the prior decision label: `BUY`, `WATCH`, `PASS`, or `SELL`.

Briefly state the prior decision reason in 1-3 sentences. Do not restate the full memo.

## 2. Previous Primary Uncertainty

Copy or summarize the prior memo's primary uncertainty.

If the prior memo did not clearly identify one, state the uncertainty that appears most decision-relevant from the prior memo.

## 3. Previous Decision-Dominant Question

State the one question that most controlled the prior decision.

This should usually be a judgment question, not a generic risk. Examples:

- Is growth durable enough to support the valuation?
- Is margin pressure temporary or structural?
- Is capex growth producing high-return capacity or lower owner earnings quality?
- Is the balance sheet risk manageable under normalized conditions?

## 4. Previous What Would Change My Mind

Summarize the prior memo's stated triggers that would change the decision.

Separate triggers that would improve the decision from triggers that would weaken it when useful.

## 5. New Evidence

List only new evidence since the prior memo that could affect the decision.

Prioritize:

- New financial results
- Guidance changes
- Segment-level changes
- Capital allocation changes
- Balance sheet changes
- Competitive, regulatory, customer, or industry evidence
- Material price or valuation changes

For each item, state why it matters. If evidence is interesting but not decision-relevant, omit it.

## 6. Changes to Key Variables

Identify whether the prior key variables changed.

For each decision-relevant variable, state:

- Prior view
- New evidence
- Updated view
- Direction of change: strengthened, weakened, unchanged, or unclear

If the previous decision-dominant variable no longer dominates, state what replaced it.

Do not add new key variables unless new evidence makes the old framing obsolete or incomplete.

## 7. Changes to Owner Earnings

State whether the underwritten normalized owner earnings changed.

Use ranges and judgment. Do not rebuild the full valuation model.

Address only material changes in:

- Revenue durability
- Margins
- Reinvestment or maintenance capex
- Working capital
- Stock-based compensation or dilution
- Interest, tax, leases, or balance sheet costs
- One-time items that affect normalized earnings interpretation

If owner earnings are unchanged, say why.

## 8. Changes to Expectation Gap

Compare the updated evidence-supported expectations with the updated price-implied expectations.

Focus on whether the gap became:

- More attractive
- Less attractive
- Unchanged
- Too uncertain to judge

Do not perform full valuation work. Use only the valuation checks needed to judge whether the gap changed.

## 9. Updated Primary Uncertainty

State the current single uncertainty most likely to change the investment judgment.

If the primary uncertainty changed from the prior memo, explain why.

If it did not change, state whether the new evidence strengthened, weakened, or failed to resolve it.

## 10. Decision Impact

State whether the prior decision should change.

Choose one:

- Decision unchanged
- Upgrade
- Downgrade
- Inconclusive

If the decision changes, state the updated decision label: `BUY`, `WATCH`, `PASS`, or `SELL`.

Explain the decision impact in plain language. Tie it to:

- New evidence
- Key variable changes
- Owner earnings changes
- Expectation gap changes
- Updated primary uncertainty

## Rules

- Use the prior memo as the baseline.
- Focus only on material changes.
- Do not repeat business understanding.
- Do not repeat full valuation.
- Do not introduce a new thesis unless the evidence requires it.
- Do not bury a decision change in narrative.
- Do not treat market price movement alone as sufficient evidence unless it changes the expectation gap.
- Do not produce a new recommendation if new evidence has not been reviewed enough to support it.
- Preserve uncertainty explicitly.
- Keep the output lightweight.

## Completion Check

This workflow is complete when the output clearly answers:

- What was the prior decision?
- What uncertainty and decision question controlled the prior decision?
- What evidence would have changed the prior decision?
- What new evidence has appeared?
- Which key variables changed?
- Did normalized owner earnings change?
- Did the expectation gap change?
- What is the updated primary uncertainty?
- Should the decision change?

If the answer to "Should the decision change?" is unclear, the correct output is `Inconclusive`, not a forced decision.
