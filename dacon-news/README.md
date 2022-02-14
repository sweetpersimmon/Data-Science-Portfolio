# 월간 데이콘 뉴스 토픽분류 AI 경진대회
**■ Background**
* 뉴스 헤드라인 내에 있는 텍스트 정보를 이용하여 뉴스의 토픽을 분류할 수 있는 모델을 만들고, 다양한 언어 모델을 이용한 분류기 생성을 시도하며 뉴스 헤드라인의 특성을 파악
<br><br>

**■ Tools**
* Python, Transforemer
<br><br>

**■ Summary**<br><br>
**1. Data Collection**
  * 주최 측에서 제공한 국내 최초 오픈 데이터 세트인 KLUE(Korean Language Understanding Evaluation) 데이터 세트를 이용
<br>

**2. Data Processing**
  * 특수문자 제거, 뉴스 내용을 축약하여 전달하기 위해 주로 사용되는 한자 표기를 한글로 변환하여 성능을 향상시킴
  * 뉴스 헤드라인 외에 뉴스 기사 본문을 크롤링하여 추가 피쳐로 사용 시도
<br>

**3. Model & Algorithms**
  * KcBERT, KoELECTRA 모델의 훈련을 담당
    * KcBERT : 뉴스 기사만 학습한 KoBERT 모델도 있지만, 동일한 데이터셋으로 훈련했을 때 뉴스 기사의 comment까지 학습한 KcBERT 모델이 더 좋은 성능을 보임
    * KoELECTRA : 기존 BERT의 문제점인 학습 데이터 사용의 비효율성을 극복하기 위한 ELECTRA 아키텍쳐 기반으로 학습하여 더 좋은 성능을 보임
  * 모델 차원에서 attention dropout, hidden dropout을 적용하고 AdamW optimizer를 사용하여 weight decay 효과를 보임으로써 성능 향상
<br>

**5. Report**
  * 많은 언어모델을 사용하지 않았음에도 불구하고, 주제와 비슷한 내용의 사전학습된 데이터를 학습한 모델에 집중하여 정확도 0.83으로 상위 4% 달성
  * 정확도 향상을 위해 다양한 optimizer를 탐색하는 과정을 거치며 일반화 능력을 향상시키는 시도를 경험할 수 있었고, 실질적으로 성능을 향상시킨 optimizer를 찾을 수 있었음
<br>

**6. Review**
  * 언어모델의 미세조정에만 집중한 나머지 fully connected layer 같은 다른 모델과의 결합을 고려해보지 못했음 -> 만약에 추가로 적용해 봤다면 성능을 향상시킬수도 있었을 것 같음
  * 자원 부족 등으로 인해 기사 본문을 추가 feature로 활용하지 못해 아쉬움(부록 참고)
<br><br>
