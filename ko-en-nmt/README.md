# Seq2seq with attention을 이용한 한글-영어 기계번역
**■ Background**
* s2s with attention을 이용한 기계번역을 구현한 예시는 주로 영어-스페인어 위주로 스페인어와 영어 단어의 유사성, 스페인어 언어 구조의 규칙성 등의 사유로 번역 결과가 매끄러운 경우가 많이 관찰됨
* 영어와 한국어는 문장 구조, 어휘 등 차이점이 많은ㄷ 그럼엗 불구하고 기계번역을 잘 구현할 수 있을지 직접 실험해 보고자 함
<br><br>

**■ Tools**
* Python, Keras, Tensorflow
<br><br>

**■ Summary**<br><br>
**1. Data Collection**
  * [Ai-Hub에서 한국어-영어 번역(병렬) 말뭉치](https://play.google.com/store/apps/details?id=com.towneers.www&hl=ko&gl=US) 중 구어체 데이터셋에서 2만 문장을 대상으로 훈련
<br>

**2. Data Processing**
  * 특수문자만 제거 후 Subword Tokenizer인 SentencePiece로 토큰화
  * 2만 개의 대용량 데이터의 전처리를 효율적으로 수행하기 위해 tf.data.dataset 모듈 사용하여 훈련/검증 데이터셋 생성
<br>

**3. Model & Algorithms**
  * Seq2seq with attention
    * seq2seq 모델은 시퀀스 길이와 순서를 자유롭게 하여 두 언어간 번역 같은 task에 탁월한 성능을 보유, attention 매커니즘을 추가하여 중요한 단어에 집중할 수 있도록 함
    * rnn 구조의 encoder와 decoder에 각각 2개의 gru 레이어 사용, decoder에 Bahdanau attention을 추가하여 전체 architecture 구성
    * 훈련 및 검증 데이터셋의 BLEU score의 중위수가 각각 0.66, 0.62 달성
<br>

**5. Report**
  * BLEU score는 0.6 정도로 예상보다 좋은 점수가 나왔지만, attention plot을 살펴본 결과 번역된 개별 문장의 퀄리티는 생각보다 높지 않은 것으로 보임
  * 긴 문장의 경우 같은 단어만 계속 반복되는 등의 문제가 보이는 데 반해, 비교적 짧은 문장은 더 매끄러운 번역이 관찰됨
<br>

**6. Review**
  * BLEU score와 attention plot 결과 간 격차를 줄이기 위한 방안이 필요
  * 한국어 형태소 분석 시 [조사를 제거한 후 SentencePiece Unigram을 적용 시 성능이 향상된다는 연구](http://hiai.co.kr/wp-content/uploads/2019/12/논문증빙_2019_06.pdf)가 있어 발전된 tokenizer를 사용하는 것을 고려
  * attention을 적용했음에도 long-term dependency problem을 해결하지 못했음 => transformer 모형의 적용 고려
<br><br>
