# 03 Assess Investment

## Purpose

Determine whether the current price implies expectations that are meaningfully different from expectations supported by evidence.

This step evaluates the investment opportunity, not just the business. It should make the investment judgment sharper, not longer. It does not make the final `BUY`, `WATCH`, `PASS`, or `SELL` recommendation.

## Required Inputs

Use the completed outputs from:

- `00_required_sources.md`
- `.work/key_variables.md`
- `.work/numerical_anchors.md`
- `01_understand_business.md`
- `02_evaluate_business.md`

If prior steps are incomplete, state what is missing and how that limits the investment assessment.

If owner earnings quality could materially change the judgment, use `skills/normalized_owner_earnings.md`. If price-implied expectations or the decision-dominant variable are unclear, use `skills/expectation_decomposition.md`. Use these only when they can change the investment assessment.

Before beginning valuation work, create `.work/numerical_anchors.md` as a lightweight verification artifact. This is not a separate workflow stage. It exists only to verify valuation-sensitive numbers that will be used in this step, separate reported numbers from calculated numbers and estimates, and preserve enough calculation detail for the investment assessment to be reproducible.

Include only numbers that can materially affect valuation, owner earnings, expectation gap, balance sheet judgment, or dilution. Do not turn this into a comprehensive financial model or source summary.

Use type labels such as:

- 공시
- 시장 데이터
- 계산
- 추정
- 가이던스

## Required Sections

Use these sections exactly.

## 1. Price-Implied Expectations

Identify what the current price appears to believe.

State which key variables the current price appears most sensitive to.

Consider:

- Current market capitalization and enterprise value.
- Revenue growth implied by the valuation.
- Margin expectations implied by the valuation.
- Cash flow or owner earnings expectations.
- Reinvestment needs.
- Terminal value assumptions.
- Balance sheet risks or benefits.
- Comparison to relevant peers, history, or transaction ranges where useful.

Use reverse DCF, multiples, owner earnings yield, sum-of-the-parts, or another relevant method only when it helps identify what the price must be assuming. State implied expectations as estimates or interpretations, not facts.

Any market capitalization, enterprise value, owner earnings yield, FCF yield, or per-share calculation used here must be traceable to `.work/numerical_anchors.md`.

## 2. Evidence-Supported Expectations

State what expectations are supported by the reviewed evidence.

Anchor this section to the 1-3 key variables. Focus on what the source base supports about:

- Long-term revenue growth.
- Margins and operating leverage.
- Reinvestment needs and capital intensity.
- Cash conversion.
- Balance sheet risk.
- Durability or fragility of the business model.

Separate facts from judgment. Do not assume that recent performance, management guidance, or non-GAAP figures are automatically durable.

## 3. Normalized Owner Earnings

Before normalizing owner earnings, identify the economic metric that best represents value creation for this company.

For ordinary operating companies, this may be normalized FCF or owner earnings. For banks, it may be through-cycle ROE, credit cost, deposits, and excess capital. For insurers, it may be normalized underwriting profit, reserve quality, and float economics. For companies with finance subsidiaries, separate operating company economics from finance subsidiary economics. For turnarounds, distinguish current depressed earnings from normalized post-recovery earnings.

Do not create a sector-specific workflow unless the user explicitly chooses a company that requires one. If the company is outside the investor's circle of competence, state that limitation rather than forcing a generic valuation.

Identify the earnings, cash flow, or economic return stream being underwritten.

Address the relevant adjustments without turning this into a mechanical model:

- Reported earnings versus operating earnings.
- Free cash flow versus owner earnings.
- Maintenance capex versus growth capex when reasonably distinguishable.
- Stock-based compensation, dilution, restructuring charges, one-time items, acquisition accounting, leases, working capital swings, credit losses, insurance reserves, or commodity/cycle effects where material.
- Currency, tax, or regulatory items where material.

If normalized owner earnings cannot be estimated responsibly, state why and explain how that limits the investment judgment.

Any reported earnings, cash flow, capex, share count, dilution, financing, or non-recurring item that materially affects normalized owner earnings must be checked in `.work/numerical_anchors.md` before being used here.

## 4. Expectation Gap

Compare price-implied expectations with evidence-supported expectations.

Answer:

- Where do market expectations and evidence-supported expectations differ?
- Is the gap large enough to create an attractive investment?
- Is the gap positive, negative, or too uncertain to underwrite?
- What is the main source of margin of safety, if any?
- What is the most important downside if the gap closes against the thesis?

Use valuation methods only to clarify the gap. Do not add models for completeness.

Bear/Base/Bull cases are optional. Use them only when they clarify the expectation gap and can be estimated without false precision. If they would create false precision, use a qualitative downside/base/upside discussion instead.

## 5. Investment Judgment Before Error Test

State whether the opportunity appears attractive, unattractive, or inconclusive before the thesis challenge.

Address:

- Whether the expectation gap is large enough.
- Whether normalized owner earnings support the valuation.
- Upside versus downside.
- Probability and severity of permanent capital loss.
- Dependence on optimistic assumptions.
- Sensitivity to valuation multiples, margins, growth, reinvestment, owner earnings quality, and balance sheet risk.
- Opportunity cost versus other investments or waiting.
- Whether waiting for more evidence could eliminate the expectation gap before uncertainty is resolved.

This section may state whether the opportunity appears attractive, unattractive, or inconclusive, but must not make the final `BUY`, `WATCH`, `PASS`, or `SELL` recommendation.

After completing the assessment, update `.work/key_variables.md` only if the expectation-gap work changes which variables matter, the current view of a variable, the evidence supporting it, or what would change the view.

## Rules

- Use ranges rather than precise point estimates where appropriate.
- Explicitly identify uncertainty.
- Do not make a final `BUY`, `WATCH`, `PASS`, or `SELL` recommendation.
- Do not assume valuation outputs are facts.
- Do not hide weak assumptions inside a model.
- Do not use complexity to create false confidence.
- Do not ignore business quality when interpreting valuation.
- Do not optimize for valuation completeness. Optimize for identifying the expectation gap.
- Do not broaden this workflow into a universal valuation engine. Stay within circle of competence.

## Completion Check

This step is complete when the output clearly answers:

- What does the current price seem to believe?
- What expectations are supported by evidence?
- What owner earnings are actually being underwritten?
- Is the expectation gap large enough?
- What are the most important valuation uncertainties?
- Valuation-sensitive numbers used in this step have been checked in `.work/numerical_anchors.md` with source, date or period, type, definition or calculation, and key caveats.

The output must not make a final `BUY`, `WATCH`, `PASS`, or `SELL` recommendation.
