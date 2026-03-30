[reference_analysis.md](https://github.com/user-attachments/files/26198528/reference_analysis.md)
# 1) 데이터셋 분석

심장질환 예측을 위해 UCI 기반의 의료 데이터를 활용하였다.

-   270명의 환자
-   14개의 변수 (13 feature + 1 target)

## 변수 구성

-   수치형: age, trestbps, chol, thalach, oldpeck
-   범주형: sex, cp, fbs, restecg, exang, slope, ca, thal

## 데이터 전처리

-   결측치 없음
-   추가적인 피처 엔지니어링 없음
-   StandardScaler를 사용하여 평균 0, 표준편차 1로 정규화
-   학습 데이터로만 fit 후 테스트 데이터에 transform 적용 (데이터 누수
    방지)
## 심장질환 통계 로그
성별: 젠더 (남성 : 1; 여성 : 0)
cp: 환자가 경험한 흉통의 유형. 이 용어는 4가지 범주로 분류됩니다.
0: 전형적인 협심증, 1: 비전형적인 협심증, 2: 비협심증성 통증, 3: 무증상(명목상)
trestbps: 환자의 안정시 혈압 수치(mmHg, 수치)
chol: 혈청 콜레스테롤 (mg/dl, 숫자)
fbs: 공복 혈당 수치가 120mg/dl 초과인 경우 참이면 1, 거짓이면 0으로 표시합니다(명목척도).
restecg: 안정 시 심전도 검사 결과는 3가지 값으로 표시됩니다.
0: 정상, 1: ST-T파 이상(T파 역전 및/또는 ST 상승 또는 하강이 0.05mV 초과),
2: Estes 기준에 따른 좌심실 비대 가능성 또는 확정 소견(명목상).
시상: 달성된 최대 심박수(숫자)

<img width="874" height="169" alt="image" src="https://github.com/user-attachments/assets/60cc9218-68b9-4f26-b7fb-ad85bc174d59" />
<img width="873" height="162" alt="image" src="https://github.com/user-attachments/assets/2efbb572-1cea-4ee8-873d-2beb0befb2ed" />


------------------------------------------------------------------------

# 2) 모델링 분석

## 사용 알고리즘

-   Logistic Regression
-   Decision Tree
-   Random Forest
-   Gradient Boosting
-   K-Nearest Neighbors (KNN)
-   Support Vector Machine (SVM, RBF kernel)
-   Naive Bayes

## 알고리즘 선택 이유


-   Logistic Regression: 해석이 쉬운 기본 선형 모델
-   Decision Tree: 직관적인 규칙 기반 모델
-   Random Forest: 과적합 감소 및 성능 향상
-   Gradient Boosting: 오차를 보완하며 학습하는 고성능 모델
-   KNN: 거리 기반 분류 모델
-   SVM: 복잡한 결정 경계 학습 가능
-   Naive Bayes: 빠르고 단순한 확률 기반 모델

------------------------------------------------------------------------

# 3) 성능 평가 분석

## 평가 지표

-   Accuracy
-   Precision
-   Recall
-   F1-score
-   ROC-AUC
-   Cross Validation Mean / Std

## 성능 결과

-   Logistic Regression과 Naive Bayes가 약 87% 정확도로 가장 우수
-   Logistic Regression:
    -   Accuracy: 0.8704
    -   F1-score: 0.8627
    -   ROC-AUC: 0.9097

## 해석

-   대부분 모델이 유사한 성능을 보임
-   데이터가 잘 정제되어 있으며 특정 모델 의존도가 낮음
