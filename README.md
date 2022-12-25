# Multi-step time series 분석 내용입니다.

## Project

프로젝트를 진행하며 수행한 Feature Engineering과 코드 일부를 발췌해 담았습니다.

현재 기업과의 협업 프로젝트로 연구실 내 타 석사과정과 함께 수행중입니다.

## 수자원공모전

시계열 관련 공모전 분석내용입니다. 유량의 적산차를 예측하는 공모전이었습니다.

주 라이브러리는 Skforecast: time series forecasting를 썼습니다. 해당 라이브러리는 multi-step time series를 구현하는 라이브러리로 Direct 방식과 Recursive 방식을 지원합니다.

### 분석내용

변동성이 높은바 unique 함수 등을 활용하여 값이 1개만 존재하는 data를 삭제하고 STL 분해의 additive 모델을 활용했습니다. 이를 통해 유량이 0이 되는 때를 주기로 하여 조금 더 높은 수치의 정확도를 확인했습니다

MAE가 99.2 까지의 정확도를 보였으나 더 좋은 결과치를 찾지 못해 Drop한 과제 내용입니다.

