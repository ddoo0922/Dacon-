# DACON_Nerdiness
-------------------------------------
설문의 답변과 개인 정보를 바탕으로 "Nerdiness" 값을 예측하는 대회입니다. (이진 분류)

## EDA ✏

✔칼럼 설명
- Q1~Q26: 질문
    - 대답: 1 ~ 5
- country: 응답자의 국적
- introelapse: intro에서 소요된 시간
- testelapse: test에서 소요된 시간
- surveyelapse: survey에서 소요된 시간
- TIPI1~TIPI10: 본인을 나타내는 단어 
    - 대답: 1(전혀 아니다) ~ 7(매우 그렇다)
- VCL1~VCL16: 지식 수준?, 정확한 의미를 아는 단어 체크 
    - 대답: 1(안다), 0 (모른다)
- education: 교육 수준
- urban: 거주 지역
- gender: 성별
- engnat: 영어가 모국어인지의 여부
- age: 나이
- hand: 왼손잡이 or 오른손잡이
- religion: 종교
- orientation: 성향 
- voted: 투표에 참여한 횟수
- married: 결혼한 횟수
- familisize: 가족 구성원 수
- ASD: 자폐스펙트럼장애 정도
- nerdiness: *타겟변수, nerdiness 정량화하는 프로젝트, nerd인지 아닌지
https://educalingo.com/ko/dic-en/nerdiness

✔설문 문항 별 상관관계 분석

- e.g) Questions 상관분석


![image](https://user-images.githubusercontent.com/74172467/201461649-7f1de40d-92f2-4212-bb0a-0b968e0a0fb0.png)

✔결측치 처리 

- e.g) Questions의 결측치 채우기
~~~
from sklearn.impute import KNNImputer

def knull(col):
    imputer = KNNImputer(n_neighbors=3)
    a = imputer.fit_transform(train[col])
    x_train[col] = a

#knull(col) : null값을 knn을 사용하여 채워줍니다.
#여기서 주의 하실점이 있어요. col이 2차원이여야만 knn이 가능합니다. 그래서 Q나 TIPI에만 사용할 수 있어요
# 아니면 결측치를 채우고 싶은 col과 다른 col들을 묶어서 넣어주어도 가능합니다. 물론 이상치 제거가 우선되야겠죠?

knull(Answers)
~~~

✔이상치 제거 

- e.g) age 이상치 제거

![image](https://user-images.githubusercontent.com/74172467/201464834-85ac2053-f49b-43df-a15c-e7cb79976a8c.png)
~~~
x_train = x_train.drop(x_train[x_train.age > 120].index)
x_train = x_train.drop(x_train[x_train.age < 4].index)

y_train = x_train.drop(x_train[x_train.age > 120].index)
y_train = x_train.drop(x_train[x_train.age < 4].index)

test = test.drop(test[test.age > 120].index)
test = test.drop(test[test.age < 4].index)
~~~

## MODEL ✏


