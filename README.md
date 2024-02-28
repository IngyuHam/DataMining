# 데이터마이닝 팀 프로젝트  

## A. 소개 
데이터마이닝 수업에서 배운 이론들을 활용하여 팀별로 자유롭게 AI 모델을 구현 및 개발해보았습니다.
저희 팀은 "수질 데이터를 활용한 음용수 분류 모델 개발"을 주제로 선정하여 프로젝트를 진행하였습니다. 

## B. 진행 과정 
### 0. 데이터 출처
[Kaggle Dataset : Water quality](https://www.kaggle.com/datasets/mssmartypants/water-quality)

### 1. 전처리
target variable인 is_safe를 제외하고, 각 변수별로 이상치와 결측치를 탐색 및 처리하는 시간을 가졌습니다.   
1) 결측치 처리
    -> 총 결측치 수가 3개인 것으로 보아 프로젝트 진행에 거의 영향을 끼치지 못한다고 판단하여 삭제
2) 이상치 처리
   -> aluminium, arsenic, nitrites 세 변수에서 이상점의 비율이 20%를 넘어서 따로 처리하지 않기로 결정

### 2. EDA
1) is_safe에 따른 각 변수의 그래프를 그려서 어떤 변수가 is_safe의 여부를 결정할지 예측, 해당 프로젝트에서는 밀도함수 그래프와 Boxplot을 활용함. 
2) 변수간의 상관관계를 확인해보고, 상관관계가 높은 변수끼리는 한 쪽을 제거하는 방향을 고려 
3) target variable에서 클래스 간의 비율이 불균형을 이루는지 확인
   -> R의 ROSE 패키지를 활용하여 오버샘플링과 언더샘플링을 동시에 진행함으로써 클래스 비율을 재조정
4) 변수 간의 단위 차이가 크면, 모델 학습 시 단위가 큰 변수에 영향을 더 많이 받으므로, 표준화나 정규화를 통해 변수 간의 범위를 조정함으로써 정확도 향상 
   -> 변수 간의 단위 차이가 크면, 모델 학습 시 단위가 큰 변수에 영향을 더 많이 받을 수 밖에 없다. 따라서 표준화나 정규화를 통해 변수 간의 범위를 조정해야 한다.

### 3. Modeling


