# value-invest-agent

가치투자 리서치 에이전트를 위한 분석 운영체계입니다.

이 레포는 종목 추천을 자동으로 찍어내기 위한 valuation engine이 아닙니다. 목적은 에이전트가 기업을 이해하고, 증거를 검토하고, 현재 가격에 내재된 기대와 증거가 뒷받침하는 기대 사이의 차이를 판단하도록 만드는 것입니다.

핵심 질문은 하나입니다.

> 현재 가격은 무엇을 믿고 있고, 검토한 증거는 그 믿음을 지지하는가?

## 지향하는 철학

이 레포의 analyst는 트레이더, 매크로 예측가, 천재 투자자가 아니라 **신중한 8/10 가치투자 분석가**로 설계되어 있습니다.

- 사업 먼저, valuation은 그 다음
- 증거 먼저, 결론은 그 다음
- 1차 자료 우선
- 모르는 것은 모른다고 말하기
- 정밀한 척하지 않기
- 좋은 thesis일수록 더 강하게 반박하기
- `BUY`, `WATCH`, `PASS`, `SELL`을 일관된 기준으로 사용하기

분석의 목적은 긴 보고서를 만드는 것이 아니라, 투자 판단을 바꾸는 변수를 선명하게 만드는 것입니다.

## 레포가 하는 일

`value-analyst/`는 에이전트가 기업 분석을 수행할 때 따라야 할 절차와 출력 형식을 정의합니다.

```text
value-analyst/
  AGENTS.md
  00_required_sources.md
  01_understand_business.md
  02_evaluate_business.md
  03_assess_investment.md
  04_challenge_thesis.md
  05_make_decision.md
  06_storage.md
  update_workflow.md
  skills/
  templates/
  companies/
```

각 문서는 에이전트가 다음 순서로 판단하도록 강제합니다.

1. 필수 자료를 모으고 누락을 명시한다.
2. 사업을 이해한다.
3. 사업 품질과 지속성을 평가한다.
4. 가격에 내재된 기대와 증거 기반 기대를 비교한다.
5. 가장 강한 반론으로 thesis를 검증한다.
6. 최종 결정을 내린다.
7. 장기 기억에 필요한 산출물만 저장한다.

## 구현 방식

### 1. 루트 지침

[`value-analyst/AGENTS.md`](value-analyst/AGENTS.md)는 에이전트의 역할, 언어 정책, 핵심 원칙, 의사결정 기준을 정의합니다.

특히 모든 사용자-facing 분석 결과는 한국어로 작성하도록 설계되어 있습니다. 회사명, ticker, FCF, ROIC, 10-K 같은 짧은 전문 용어는 예외적으로 유지할 수 있습니다.

### 2. 단계별 workflow

`00`부터 `05`까지의 workflow는 분석이 성급한 결론으로 점프하지 않도록 합니다.

- [`00_required_sources.md`](value-analyst/00_required_sources.md): 필수 자료와 source log
- [`01_understand_business.md`](value-analyst/01_understand_business.md): 사업 모델과 경제성 이해
- [`02_evaluate_business.md`](value-analyst/02_evaluate_business.md): 사업 품질, moat, 경영진, 재무 위험 평가
- [`03_assess_investment.md`](value-analyst/03_assess_investment.md): 기대 차이와 normalized owner earnings 판단
- [`04_challenge_thesis.md`](value-analyst/04_challenge_thesis.md): strongest bear case와 error test
- [`05_make_decision.md`](value-analyst/05_make_decision.md): 최종 `BUY` / `WATCH` / `PASS` / `SELL`

### 3. 판단 추적 workflow

[`update_workflow.md`](value-analyst/update_workflow.md)는 기존 investment memo를 다시 전부 분석하지 않고 업데이트할 때 사용합니다.

이 workflow는 prior memo를 baseline으로 삼고 다음만 확인합니다.

- 무엇이 새로 바뀌었는가
- 핵심 변수가 바뀌었는가
- owner earnings가 바뀌었는가
- expectation gap이 바뀌었는가
- 최종 판단이 바뀌어야 하는가

목표는 재분석이 아니라 judgment tracking입니다.

### 4. 선택적 deep-analysis skills

[`value-analyst/skills/`](value-analyst/skills)는 기본 workflow가 아니라, 특정 판단이 불확실할 때만 여는 보조 문서입니다.

- [`normalized_owner_earnings.md`](value-analyst/skills/normalized_owner_earnings.md): headline earnings, FCF, SBC, capex, working capital, cyclicality 등이 owner earnings 판단을 흐릴 때
- [`expectation_decomposition.md`](value-analyst/skills/expectation_decomposition.md): 현재 가격이 무엇을 믿는지, decision-dominant expectation이 무엇인지 불분명할 때
- [`bear_thesis_construction.md`](value-analyst/skills/bear_thesis_construction.md): thesis가 너무 매끄럽거나 `BUY` 후보를 더 강하게 반박해야 할 때

skill은 “더 자세히 쓰기”가 아니라 “판단이 바뀔 수 있는 지점만 더 깊게 보기”를 위해 존재합니다.

### 5. 저장 정책

[`06_storage.md`](value-analyst/06_storage.md)는 분석 산출물을 가볍게 보존하는 방식을 정의합니다.

완료된 분석은 원칙적으로 세 파일만 남깁니다.

```text
companies/
  <ticker>/
    <YYYY-MM-DD>/
      source_log.md
      reasoning_summary.md
      investment_memo.md
```

중간 workflow 산출물은 `.work/`에 만들고, 최종 메모와 reasoning summary가 완성되면 삭제합니다. 장기적으로 필요한 것은 과정 전체가 아니라, evidence base와 판단의 핵심입니다.

## GitHub 저장 범위

회사별 분석 결과는 개인적이고 시점 의존적인 산출물이므로 GitHub에 올리지 않습니다.

현재 `.gitignore`는 다음을 제외합니다.

```text
value-analyst/companies/
```

즉, 레포에는 분석 시스템, workflow, templates, skills만 저장하고, 특정 회사의 analysis output은 로컬에만 남깁니다.

## 사용 예시

새 기업을 분석할 때:

```text
1. 00_required_sources.md로 필수 자료 수집
2. 01_understand_business.md로 사업 이해
3. 02_evaluate_business.md로 사업 품질 평가
4. 03_assess_investment.md로 expectation gap과 owner earnings 판단
5. 04_challenge_thesis.md로 strongest bear case 작성
6. 05_make_decision.md로 최종 결정
7. 06_storage.md에 따라 source_log, reasoning_summary, investment_memo 저장
```

기존 판단을 업데이트할 때:

```text
1. prior investment_memo.md를 baseline으로 읽기
2. update_workflow.md로 새 증거만 검토
3. key variables, owner earnings, expectation gap 변화 확인
4. decision impact만 기록
```

## 최종 산출물이 답해야 하는 질문

좋은 investment memo는 다음 다섯 질문에 답해야 합니다.

1. 현재 가격은 무엇을 믿고 있는가?
2. 검토한 증거를 바탕으로 우리는 무엇을 다르게 보는가?
3. 그 기대 차이는 충분히 큰가?
4. 실제로 어떤 owner earnings를 underwrite하고 있는가?
5. 무엇이 이 판단을 틀리게 만들 수 있는가?

이 레포는 에이전트가 그 질문을 반복해서, 일관되게, 더 덜 속으면서 묻게 만드는 장치입니다.
