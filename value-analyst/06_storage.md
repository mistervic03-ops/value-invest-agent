# 06 Storage

## Purpose

Define the storage lifecycle for completed company analyses.

The goal is to preserve source evidence, compressed reasoning, and final investment judgment while preventing repository bloat.

The storage model should not preserve process for its own sake. Permanent artifacts should make the expectation gap, owner earnings judgment, and error test easy to recover.

## Permanent Storage Model

Completed analyses must preserve only three primary artifacts:

- `source_log.md`
- `reasoning_summary.md`
- `investment_memo.md`

The visible analysis directory should remain clean and focused on long-term investment memory.

```text
companies/
  <ticker>/
    <YYYY-MM-DD>/
      source_log.md
      reasoning_summary.md
      investment_memo.md
```

## Analysis Phase

Create or identify the dated analysis directory before writing company-specific analysis outputs:

```text
companies/<ticker>/<YYYY-MM-DD>/
```

During analysis, generate workflow artifacts in a temporary `.work/` directory:

```text
companies/
  <ticker>/
    <YYYY-MM-DD>/
      source_log.md
      .work/
        key_variables.md
        numerical_anchors.md
        01_business_understanding.md
        02_business_evaluation.md
        03_investment_assessment.md
        04_thesis_challenge.md
        05_decision.md
```

Workflow artifacts are mandatory. They are not optional.

`key_variables.md` is a living workflow artifact, not a separate workflow stage. It preserves the 1-3 variables most likely to drive long-term business and investment outcomes so later stages stay focused.

`numerical_anchors.md` is a lightweight verification artifact, not a separate workflow stage. It preserves only valuation-sensitive numbers that must be checked before investment assessment: source, date or period, type, definition or calculation, and key caveats. It should distinguish reported numbers from market data, calculated numbers, estimates, and guidance. It should not become a comprehensive model or source summary.

Each later stage must read the prior artifacts:

- `02_business_evaluation.md` must use `source_log.md`, `key_variables.md`, and `01_business_understanding.md`.
- `03_investment_assessment.md` must use `source_log.md`, `key_variables.md`, `numerical_anchors.md`, `01_business_understanding.md`, and `02_business_evaluation.md`.
- `04_thesis_challenge.md` must use `key_variables.md` and all prior workflow artifacts.
- `05_decision.md` must use `key_variables.md`, `numerical_anchors.md`, and all prior workflow artifacts.

Do not mechanically rewrite `key_variables.md`. Update it only when the business evaluation, expectation-gap work, or error test changes which variables matter, the current view of a variable, the evidence supporting it, or what would change the view.

Do not bypass workflow stages.

## Memo Generation Phase

Generate:

- `investment_memo.md`

The final memo must be synthesized from:

- `source_log.md`
- `.work/key_variables.md`
- `.work/numerical_anchors.md`
- `.work/01_business_understanding.md`
- `.work/02_business_evaluation.md`
- `.work/03_investment_assessment.md`
- `.work/04_thesis_challenge.md`
- `.work/05_decision.md`

The memo is the primary long-term investment artifact. It should be readable on its own, but its judgment must remain traceable to the source log and workflow artifacts.

The memo must follow the repository language policy: write user-facing headings, labels, table columns, and narrative text in Korean unless the user explicitly requests another language.

The memo should answer five questions:

1. 현재 가격은 무엇을 믿고 있는가?
2. 검토한 증거를 바탕으로 우리는 무엇을 다르게 보는가?
3. 그 기대 차이는 충분히 큰가?
4. 실제로 어떤 owner earnings를 underwrite하고 있는가?
5. 무엇이 이 판단을 틀리게 만들 수 있는가?

The memo should preserve only the checked numerical anchors that affect the final judgment. Do not repeat the full `numerical_anchors.md` table unless the user explicitly asks for it.

## Compression Phase

After memo generation, create:

- `reasoning_summary.md`

`reasoning_summary.md` preserves the most important reasoning from the workflow artifacts without permanently storing every intermediate document.

Required sections:

1. 핵심 변수 요약
2. 사업 이해 요약
3. 사업 평가 요약
4. 기대 차이 요약
5. 오류 검증 요약
6. 결정 요약

Each section should contain only the most important conclusions, evidence, assumptions, uncertainties, and reasoning. Keep it concise.

## Cleanup Phase

After `source_log.md`, `reasoning_summary.md`, and `investment_memo.md` exist:

- Delete `.work/` unless the user explicitly requests preservation.
- Do not leave workflow artifacts in the visible analysis directory.
- Do not save company-specific artifacts at the repository root.
- Do not save final or intermediate analysis files directly under `companies/<ticker>/`.

Final visible structure:

```text
companies/
  <ticker>/
    <YYYY-MM-DD>/
      source_log.md
      reasoning_summary.md
      investment_memo.md
```

## Never Overwrite Rule

Never overwrite an existing analysis.

Each new analysis must create a new dated directory. If multiple analyses occur on the same date, append a suffix:

```text
2026-06-02-a
2026-06-02-b
```

## Metadata

Preserved artifacts should begin with a metadata block when practical:

```yaml
---
company: "<company name>"
ticker: "<ticker>"
analysis_date: "YYYY-MM-DD"
analyst_agent: "<analyst or agent>"
artifact_type: "source_log | reasoning_summary | investment_memo"
---
```

The metadata block must match the directory path and file contents.

## Completion Criteria

An analysis is complete only when:

- `source_log.md` exists.
- `reasoning_summary.md` exists.
- `investment_memo.md` exists.
- The final memo includes the final key variables.
- The reasoning summary includes `핵심 변수 요약`.
- The final memo answers the five expectation-gap questions above.
- The reasoning summary compresses the workflow artifacts without preserving process-only detail.
- Temporary workflow artifacts have been removed or explicitly preserved at the user's request.
- No company-specific analysis files exist directly under `companies/<ticker>/`.
- No company-specific working artifacts remain at the repository root.
