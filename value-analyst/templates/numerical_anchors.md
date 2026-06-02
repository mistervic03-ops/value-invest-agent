---
company: ""
ticker: ""
analysis_date: ""
analyst_agent: ""
artifact_type: "numerical_anchors"
---

# 숫자 앵커

목적: valuation, owner earnings, 기대 차이, balance sheet 판단, dilution 판단에 직접 영향을 주는 숫자만 검증한다. 전체 재무 모델이나 자료 요약으로 확장하지 않는다.

유형은 `공시`, `시장 데이터`, `계산`, `추정`, `가이던스` 중 하나를 사용한다.

| 항목 | 값 | 기준일 / 기간 | 유형 | 출처 | 정의 / 계산식 | 주의점 |
| --- | ---: | --- | --- | --- | --- | --- |
| 주가 |  |  | 시장 데이터 |  |  | 출처별 차이가 있으면 범위 또는 반올림값 사용 |
| 주식 수 |  |  | 공시 |  |  | 기본/희석/outstanding/share class 구분 |
| Equity value / market cap |  |  | 계산 / 시장 데이터 |  | 주가 x 주식 수 또는 시장 데이터 출처 | 계산값과 시장 데이터가 다르면 차이 설명 |
| 현금 및 시장성 증권 |  |  | 공시 |  |  | 제한 현금 또는 비영업 투자자산 구분 필요 여부 |
| 부채 및 부채성 항목 |  |  | 공시 |  |  | 리스, preferred, convertibles, 후속 발행 여부 |
| Enterprise value |  |  | 계산 / 추정 |  | equity value - cash + debt +/- 조정 | 불확실 항목은 범위 사용 |
| OCF / capex / FCF |  |  | 공시 / 계산 |  | OCF - capex | TTM, FY, 분기 기간 구분 |
| 핵심 세그먼트 매출 / 이익 / 마진 |  |  | 공시 / 계산 |  |  | 세그먼트 정의 변경 여부 |
| backlog / RPO / deferred revenue |  |  | 공시 |  | 회사 정의 그대로 | 포함 범위와 인식 기간 확인 |
| capex / 매출 / 마진 가이던스 |  |  | 가이던스 |  |  | 기간, 범위, 조건 확인 |
| SBC / buyback / issuance / dilution |  |  | 공시 / 계산 / 추정 |  |  | 발행 예정, ATM, convertibles, preferred 별도 표시 |
| 비경상 또는 조정 항목 |  |  | 공시 / 추정 |  |  | 세금, 소송, 투자자산 평가손익, 구조조정 등 |
| underwrite한 owner earnings |  |  | 추정 |  | 핵심 조정 요약 | 단일값보다 범위 사용 |
| owner earnings yield / FCF yield |  |  | 계산 |  | owner earnings 또는 FCF / EV 또는 equity value | denominator와 numerator 일관성 확인 |

## 사용하지 않은 숫자

검토했지만 최종 valuation 또는 판단에 쓰지 않은 숫자는 필요할 때만 짧게 적는다.

-
