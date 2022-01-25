# Data-Science-Portfolio
> 본 저장소는 지금까지 진행했던 프로젝트와 공모전 참여내용을 정리하는 곳입니다.<br>
> 내용과 관련한 문의는 언제든지 gghdwl1103@gmail.com 로 해주시면 감사하겠습니다.

<br>

## Portfolio
포트폴리오 업로드 된 pdf 주소 첨부
<br><br><br>
## Contents

### Daagn app review analysis
(2020.06, 개인 프로젝트)
* [바로가기](https://github.com/sweetpersimmon/Data-Science-Portfolio/tree/main/daangn-app-review-analysis) / [PDF](https://github.com/sweetpersimmon/Data-Science-Portfolio/blob/main/daangn-app-review-analysis/daangn%20app%20review%20analysis%20-%20report.pdf)<br>

**■ Background**
* 긍정적 리뷰와 부정 리뷰를 구분하는 데 영향으 미치는 키워드가 존재하며, 이를 분류기로 구현했을 때 충분히 구분해 내는지 확인
* 긍정 혹은 부정적인 상황에서 주로 사용하는 키워드를 시각화하여 현안 이슈 파악

**■ Tools**
* Python, Keras<br>

**■ Summary**<br><br>
**1. Data Collection**
  * [구글 플레이 스토어](https://play.google.com/store/apps/details?id=com.towneers.www&hl=ko&gl=US)에서 당근마켓의 최근 2142건의 리뷰와 별점을 selenium으로 크롤링 후 각 리뷰의 긍정(1)과 부정(0)으로 수동 라벨링
  * 총 2142건, 긍정 1534건 / 부정 608건

**2. Data Processing**
  * 한국어로 작성된 내용을 처리하기 위해 특수문자 및 영문 제거, 텍스트 리뷰 없이 별점만 매긴 리뷰 삭제<br>
  * 수집 데이터로 Word Cloud 생성하여 주로 사용된 어휘 파악
  * Tokenizer : Twitter 한국어 처리기에서 파생된 오픈소스 한국어 처리기 Okt를 이용하여 형태소 분석

**3. Model & Algorithms**
  * 긍/부정 리뷰 분류기 생성 - LSTM, Lime
    * LSTM의 장점 적기
    * 리뷰 내에서 긍정 혹은 부정 판별에 영향을 미치는 어휘와 영향의 정도를 그래프로 나타내기 위해 Lime으로 시각화
  * 키워드 분석 - FastText, t-SNE
    * facebook의 FastText 알고리즘으로 3개 차원에 워드 임베딩 후 t-SNE로 시각화하여 키워드들의 군집 특성 파악

**5. Report**
  * 각 평가는 긍정 혹은 부정적인 의견은 확연히 구분되는 문장 구성을 갖추고 있음을 확인했으며, 감성 분류 모델을 통해 해당 어플을 이용하는 고객이 불만족스러운 리뷰를 남겼을 때, 자동으로 탐지할 수 있도록 함
  * 긍/부정 감성 별 주요 키워드를 시각화 함으로써 당근 마켓의 현안을 탐색학 도출된 장단점을 통해 고객경험을 효율적으로 관리하고 개선 사항을 쉽게 파악할 수 있음

**6. Review**
  * 사전에 Word Cloud를 그릴 때, 긍/부정 리뷰에 초점을 둔 만큼 감성 구분 별 시각화를 진행했다면 내용을 파악하는 데 도움이 되었을 것으로 보임
  * BiLSTM을 사용하여 순방향과 역방향의 결과를 모두 활용하고 싶었지만 결과에서 큰 차이가 나지 않았음
  * CNN 레이어를 결합하는 등 모델 구조적인 측면에서 다양한 시도를 해 보지 못해 아쉬움
  * 프로젝트 당시 LSTM의 모델을 Lime에 동일하게 적용한 시각화에 실패했었으나 일관적이 결과 해석을 위해 해결 방안을 탐색 후 코드 개선 예정
<br><br>

### Ko-en machine translation
(2020.06, 개인 프로젝트)
* [바로가기](https://github.com/sweetpersimmon/Data-Science-Portfolio/blob/main/ko-en-machine-translation/Seq2seq%20with%20attention(machine%20translation).ipynb) / [PDF](https://github.com/sweetpersimmon/Data-Science-Portfolio/blob/main/ko-en-machine-translation/Seq2seq%20with%20attention(machine%20translation).pdf)
* Seq2seq with attention 알고리즘 구현을 통한 
* 활용 데이터
* 프로젝트 소개 with 핵심 아이디어
  * 목적(핵심 아이디어)
  * 과정
  * 주요 알고리즘과 선택 이유
* 배운점/성과 & 어려웠던 점과 해결방법
<br><br>

### 2020 bigcontest
(2020.08 ~ 12, 팀 참여)
- [바로가기](https://github.com/sweetpersimmon/Data-Science-Portfolio/tree/main/2020-bigcontest) / [PDF](https://github.com/sweetpersimmon/Data-Science-Portfolio/blob/main/2020-bigcontest/혁신아이디어분야_코로나나빠_결과보고서.pdf)
- 혁신아이디어 부문, 뉴노멀 시대 준비를 위한 서비스 아이디어 및 PoC(Proof Of Concept) 결과 제시
  ```
  산업 평가 인덱스 개밤을 통한 코로나 시기의 취약 산업군 선별
  해당 산업군의 회복을 위한 비대면 중고거래 자판기의 입지선정
  ```
- 데이터 목록(대회 데이터 사용 문제와 용량 제한으로 인하여 본 저장소에는 업로드하지 않았습니다.)
  |제공데이터|외부데이터|
  |----|----|
  |데이터이름|데이터이름|
- 분석 과정
  - [EDA](https://github.com/sweetpersimmon/Data-Science-Portfolio/tree/main/2020-bigcontest/eda)
  - [Index](https://github.com/sweetpersimmon/Data-Science-Portfolio/tree/main/2020-bigcontest/index)
  - [MCLP](https://github.com/sweetpersimmon/Data-Science-Portfolio/tree/main/2020-bigcontest/mclp)
- 내 역할
- 기여자
<br><br>

### DACON news topic classification
(2020. 06 ~ 08, 팀 참여)
- [바로가기](https://github.com/sweetpersimmon/Data-Science-Portfolio/tree/main/dacon-news)
- [월간 데이콘 17, 뉴스토픽 분류 AI 경진대회](https://dacon.io/competitions/official/235747/overview/description)<br>
  ```
  한국어 뉴스 헤드라인을 이용하여, 뉴스의 주제를 분류하는 알고리즘 개발
  ```
- YNAT(주제 분류를 위한 연합 뉴스 헤드라인) 데이터 세트를 활용해 주제 분류 알고리즘을 개발
- 분석 과정(폴더 링크)
- 내 역할
- 기여자
<br><br>

### 2021 weather bigdata contest
(2020.06 ~ 08, 팀 참여)
- [바로가기]() / [PDF]()
- 민간협력 부문, 날씨 변수 설정을 위한 재고관리 모델 및 군집화 제시(미완)
- 활용 데이터
- 분석 과정(폴더 링크)
- 내 역할
- 기여자
