## TIL
- data-centric 프로젝트에서 랭체인(LangChain)을 이용한 로컬LLM 활용하기
  - 로컬LLM을 이용한 model-based data cleansing
  - 데이터의 문제점: 1000개의 Labeling Error, 1600개의 Random Noise, 200개의 Normal Dataset
  - model-based 클렌징에서의 접근 : 쉬운 task에서 점점 어려운 task로 나아가는게 정확도가 높지 않을까?
- 클렌징 순서에 대한 고민
  - 생성형 모델을 사용하여 노이즈 데이터를 디노이징할때, 같은 레이블의 데이터를 예시로 few shot하면 훨씬 디노이징 품질이 올라가지않을까?
    - 그러면 일단 labeling error를 고쳐야겠다
  - labeling error를 고치기 위해서는 라벨별 예시를 few shot으로 밀어 넣던지, AE기반 모델로 레이블이 맞는 데이터를 학습시키는 방법
    - 레이블이 맞는 데이터 예시가 필요하다->Normal data를 찾아서 넣기는 어려움->노이즈가 있는 데이터는 레이블은 맞으니깐 노이즈가 살짝 있는 데이터를 활용하자
- 정리하자면,
  - 노이즈가 있는 데이터를 rule-based 방법론으로 찾기
  - 해당 데이터를 이용하여 AE모델을 학습하거나, 생성형 모델을 few-shot하여 labeling error를 고치자
  - labeling error가 고쳐진 데이터를 few-shot하여 생성형 모델을 통해 디노이징을 시도하자


- 해커톤 회고록 쓰기


## Retrospect
- 