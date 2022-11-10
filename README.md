# DACON_Nerdiness
-------------------------------------
설문의 답변과 개인 정보를 바탕으로 "Nerdiness" 값을 예측하는 대회입니다. (이진 분류)

## EDA ✏

칼럼 설명
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
- orientation: 지남력 (현재 자신이 놓여 있는 상황을 올바르게 인식하는 능력) https://www.amc.seoul.kr/asan/healthinfo/easymediterm/easyMediTermDetail.do?dictId=3798
- voted: 투표에 참여한 횟수
- married: 결혼한 횟수
- familisize: 가족 구성원 수
- ASD: 자폐스펙트럼장애 정도
- nerdiness: *타겟변수, nerdiness 정량화하는 프로젝트, nerd인지 아닌지
https://educalingo.com/ko/dic-en/nerdiness

# 


## MODEL ✏


