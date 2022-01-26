# Seq2seq with attention을 이용한 한글-영어 기계번역
**■ Background**
* 긍정적 리뷰와 부정 리뷰를 구분하는 데 영향을 미치는 키워드가 존재하며, 이를 분류기로 구현했을 때 충분히 구분해 내는지 확인
<br><br>

**■ Tools**
* Python, Keras
<br><br>

**■ Summary**<br><br>
**1. Data Collection**
  * [Ai-Hub에서 한국어-영어 번역(병렬) 말뭉치](https://play.google.com/store/apps/details?id=com.towneers.www&hl=ko&gl=US) 중 구어체 데이터셋 2만 문장을 대상으로 훈련
<br>

**2. Data Processing**
  * 특수문자만 제거 후 Subword Tokenizer로 SentencePiece 사용
<br>

**3. Model & Algorithms**
  * Seq2seq with attention
    * rnn 구조의 encoder와 encoder에 각각 gru 사용
    * Bahdanau attention 사용(설명 추가)
<br>

**5. Report**
  * 각 평가는 긍정 혹은 부정적인 의견은 확연히 구분되는 문장 구성을 갖추고 있음을 확인했으며, 감성 분류 모델을 통해 해당 어플을 이용하는 고객이 불만족스러운 리뷰를 남겼을 때 자동으로 탐지할 수 있도록 함
  * 긍/부정 감성 별 주요 키워드를 시각화 함으로써 당근 마켓의 현안을 탐색학 도출된 장단점을 통해 고객경험을 효율적으로 관리하고 개선 사항을 쉽게 파악할 수 있음
<br>

**6. Review**
  * Word Cloud를 그릴 때, 긍/부정 리뷰에 초점을 둔 만큼 감성 구분 별 시각화를 진행했다면 내용을 파악하는 데 도움이 되었을 것으로 보임
  * BiLSTM으로 순방향과 역방향의 결과를 모두 활용하고 싶었지만 성능에서 큰 차이가 없어 사용하지 않았지만 CNN 레이어를 결합하는 등 모델 구조적인 측면에서 다양한 시도의 필요성이 보임
  * 프로젝트 당시 Lime 시각화 과정에서 LSTM의 모델을 동일하게 적용하지 못하고 dense 레이어로만 구현 -> 일관적인 결과 해석을 위해 해결 방안을 탐색 후 코드 개선 예정
<br><br>
