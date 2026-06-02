# value-invest-agent

가치투자 에이전트를 위한 분석 프레임워크입니다.

이 저장소는 종목 추천을 자동으로 찍어내는 가치평가 엔진이 아닙니다. 에이전트가 기업을 이해하고, 증거를 검토하고, 현재 가격에 담긴 기대와 실제 증거 사이의 차이를 판단하도록 돕는 작업 체계입니다.

핵심 질문은 하나입니다.

> 현재 가격은 무엇을 믿고 있고, 검토한 증거는 그 믿음을 지지하는가?

## 지향하는 철학

이 저장소의 분석가는 트레이더도, 거시경제 예측가도, 천재 투자자도 아닙니다. 목표는 **신중한 8/10 가치투자 분석가**입니다.

- 사업 먼저, 가치평가는 그 다음
- 증거 먼저, 결론은 그 다음
- 1차 자료 우선
- 모르는 것은 모른다고 말하기
- 정밀한 척하지 않기
- 매력적인 투자 논리일수록 더 강하게 반박하기
- `BUY`, `WATCH`, `PASS`, `SELL`을 일관된 기준으로 사용하기

목적은 긴 보고서를 쓰는 것이 아니라, 투자 판단을 실제로 바꿀 수 있는 변수를 선명하게 만드는 것입니다.

## 저장소가 하는 일

`value-analyst/`는 에이전트가 기업을 분석할 때 따라야 할 절차와 출력 형식을 담고 있습니다.

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

각 문서는 에이전트가 다음 순서로 생각하도록 만듭니다.

1. 필수 자료를 모으고 누락된 자료를 밝힌다.
2. 사업을 이해한다.
3. 사업 품질과 지속성을 평가한다.
4. 가격에 내재된 기대와 증거 기반 기대를 비교한다.
5. 가장 강한 반론으로 투자 논리를 시험한다.
6. 최종 결정을 내린다.
7. 장기 기억에 필요한 산출물만 저장한다.

## 구현 방식

### 1. 루트 지침

[`value-analyst/AGENTS.md`](value-analyst/AGENTS.md)는 에이전트의 역할, 언어 정책, 핵심 원칙, 의사결정 기준을 정의합니다.

특히 사용자에게 보여주는 분석 결과는 한국어로 작성하도록 정해져 있습니다. 회사명, 티커, FCF, ROIC, 10-K처럼 그대로 쓰는 편이 더 명확한 표현은 예외입니다.

### 2. 단계별 워크플로우

`00`부터 `05`까지의 워크플로우는 에이전트가 성급하게 결론으로 뛰어가지 않도록 잡아줍니다.

- [`00_required_sources.md`](value-analyst/00_required_sources.md): 필수 자료와 자료 기록
- [`01_understand_business.md`](value-analyst/01_understand_business.md): 사업 모델과 경제성 이해
- [`02_evaluate_business.md`](value-analyst/02_evaluate_business.md): 사업 품질, 경쟁우위, 경영진, 재무 위험 평가
- [`03_assess_investment.md`](value-analyst/03_assess_investment.md): 기대 차이와 정상화 owner earnings 판단
- [`04_challenge_thesis.md`](value-analyst/04_challenge_thesis.md): 가장 강한 반론과 오류 검증
- [`05_make_decision.md`](value-analyst/05_make_decision.md): 최종 `BUY` / `WATCH` / `PASS` / `SELL`

### 3. 판단 추적 워크플로우

[`update_workflow.md`](value-analyst/update_workflow.md)는 기존 투자 메모를 다시 전부 분석하지 않고 업데이트할 때 사용합니다.

기존 메모를 기준으로 삼고, 바뀐 것만 확인합니다.

- 무엇이 새로 바뀌었는가
- 핵심 변수가 바뀌었는가
- owner earnings가 바뀌었는가
- 기대 차이가 바뀌었는가
- 최종 판단이 바뀌어야 하는가

목표는 재분석이 아니라 판단의 변화를 추적하는 것입니다.

### 4. 선택적 심화 분석 문서

[`value-analyst/skills/`](value-analyst/skills)는 기본 워크플로우가 아닙니다. 특정 판단이 아직 흐릴 때만 여는 보조 문서입니다.

- [`normalized_owner_earnings.md`](value-analyst/skills/normalized_owner_earnings.md): 보고 이익, FCF, SBC, 설비투자, 운전자본, 경기순환 등이 owner earnings 판단을 흐릴 때
- [`expectation_decomposition.md`](value-analyst/skills/expectation_decomposition.md): 현재 가격이 무엇을 믿는지, 판단을 좌우하는 기대가 무엇인지 불명확할 때
- [`bear_thesis_construction.md`](value-analyst/skills/bear_thesis_construction.md): 투자 논리가 너무 매끄럽거나 `BUY` 후보를 더 세게 검증해야 할 때

이 보조 문서들은 분석을 길게 만들기 위한 도구가 아닙니다. 판단이 바뀔 수 있는 지점만 더 깊게 보기 위한 도구입니다.

### 5. 저장 정책

[`06_storage.md`](value-analyst/06_storage.md)는 분석 산출물을 가볍게 보존하는 방식을 정의합니다.

완료된 분석은 원칙적으로 세 파일만 남깁니다.

```text
companies/
  <티커>/
    <YYYY-MM-DD>/
      source_log.md
      reasoning_summary.md
      investment_memo.md
```

중간 산출물은 `.work/`에 만들고, 최종 메모와 판단 요약이 완성되면 삭제합니다. 장기적으로 필요한 것은 모든 과정이 아니라, 증거 기반과 판단의 핵심입니다.

## GitHub 저장 범위

회사별 분석 결과는 개인적이고 시점 의존적인 산출물이므로 GitHub에 올리지 않습니다.

현재 `.gitignore`는 다음을 제외합니다.

```text
value-analyst/companies/
```

즉, GitHub에는 분석 체계, 워크플로우, 템플릿, 보조 분석 문서만 저장합니다. 특정 회사의 분석 결과는 내 컴퓨터에만 남깁니다.

## 사용 예시

새 기업을 분석할 때:

```text
1. 00_required_sources.md로 필수 자료 수집
2. 01_understand_business.md로 사업 이해
3. 02_evaluate_business.md로 사업 품질 평가
4. 03_assess_investment.md로 기대 차이와 owner earnings 판단
5. 04_challenge_thesis.md로 가장 강한 반론 작성
6. 05_make_decision.md로 최종 결정
7. 06_storage.md에 따라 자료 기록, 판단 요약, 투자 메모 저장
```

기존 판단을 업데이트할 때:

```text
1. 이전 투자 메모를 기준으로 읽기
2. update_workflow.md로 새 증거만 검토
3. 핵심 변수, owner earnings, 기대 차이 변화 확인
4. 판단 영향만 기록
```

## 최종 산출물이 답해야 하는 질문

좋은 투자 메모는 다음 다섯 질문에 답해야 합니다.

1. 현재 가격은 무엇을 믿고 있는가?
2. 검토한 증거를 바탕으로 우리는 무엇을 다르게 보는가?
3. 그 기대 차이는 충분히 큰가?
4. 실제로 어떤 owner earnings를 기준으로 판단하는가?
5. 무엇이 이 판단을 틀리게 만들 수 있는가?

이 저장소는 에이전트가 그 질문을 반복해서, 일관되게, 스스로를 덜 속이면서 묻게 만드는 장치입니다.
