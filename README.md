# Recap : Multi-step Time Series 활용 시계열 분석
- ## Roadmap
> ### Project
> - 업체 협약 프로젝트 코드 일부 발췌
> ### 수자원공모전
> - 유량 적산차 예측을 위한 Skforecast : Multi-step Time series 라이브러리 활용
> - 1시간 단위의 예측에 총 14일로 336 step의 예측 수행

- ## Project
> ## Task
> ### 1. 7월4일 Feature Engineering.xlsx
> - Feature Engineering에 사용할 변수 EDA
> ### 2. 7월 26일_Direct hybrid Strategy_ver3.ipynb
> - Brown Lee(2017) Multi-step Time Series Strategy 중 Direct-Recursive Hybrid Strategy 구현
> - Feature Engineering에 사용된 내용 :
>   **_ffill, STL분해, 잔차, 이동평균_**
> - LGBM Method 사용
> - 가격 변수 사용
> - 목표는 중장기간 농산물 가격 예측으로 30, 90, 180, 270, 365일의 예측 모델을 생성함
> - MAPE : 47.11 ~ 51.83

- ## 수자원공모전
> ## Task
> ### 1. forecaster(recursive).py
> - recursive 모델 데이터
> ### 2. main.ipynb
> - **_Preprocessing_** : Pandas, Pandas-Profiling 라이브러리, STL 분해 등의 EDA 결과 변동성이 높고 주기가 뚜렷한 데이터로 판단함. 그러나 계절에 영향을 받지 않고(구글링 및 지역 뉴스 분석) 일일 편차가 큼. 따라서 unique 함수를 통해 각 값이 1개만 존재하는 데이터와 이상치를 제거함. Winsorizing은 모델의 예측력을 하락시킴.
> - **_Training_** : Multi Step Time Series Recursive Strategy를 활용한 RandomForestRegressor 활용
> - **_Inference_** : 추론 결과 초기 MAE 99.2까지의 예측력을 보였으나 이후 Underfitting의 문제가 발생함. 이는 Recursive 모델의 오류 증폭 특성이 반영되었다고 판단됨.
> - 주최측 요구 모델의 크기에 따른 시간적 한계 등으로 더 실험하지 못하고 Drop
> ### 3. pr_test_report.html
> - Pandas-Profiling 라이브러리를 활용한 Test 데이터 EDA
> ### 4. pr_train_report.html
> - Pandas-Profiling 라이브러리를 활용한 Train 데이터 EDA