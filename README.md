# FinanceNews_Sentiment_Projec

---

## 개요

---

- 금융상품을 투자할 때 기본적으로 금융뉴스를 확인해서 어떤 정보를 가지고 있는지와 어떠한 뉘양스를 보이는지 파악해야 합니다. 또한 금융 투자 초보자일 경우는 뉴스를 보고 이해하는 것도 힘들 수 있습니다. 그러기에 금융 뉴스의 뉘양스를 자연어 처리 LSTM으로 감정분석을 하여 투자에 도움이 되는 금융 감정 분석 프로그램을 제작을 목표하고 진행하였습니다.


## 과정

---

- 금융 뉴스 문장 데이터 처리
    - 부정 : 0, 중립 : 1, 긍정 : 2로 라벨링 진행
    - 영문, 한글 번역문 혼합데이터 → 영어 문장 삭제
    - 글자와 숫자만 남기고 불필요한 부분 제거
- LSTM SETTING
    - 불용어 리스트로 불용어 처리 진행
    - keras의 Tokenizer 메서드를 통해 문장 단어 토큰화
    - keras의 pad_sequences 메서드를 통해 패딩 진행
- LSTM
    - RNN의 단점을 보완하여 **기울기 소실을 해결**, 이 전 **정보를 기억**할 수 있어서 기사문장에 대한 모델링에 적합하다고 생각
    - 타켓 클래스 **불균형**으로 **F1** SCORE로 평가지표 설정
    - kfold 교차 검증을 진행 → F1: 0.71

## 결과

---

- 금융 뉴스 제목을 입력하였을 때 긍정/부정/중립 (%) 로 감정분석 결과 확인
