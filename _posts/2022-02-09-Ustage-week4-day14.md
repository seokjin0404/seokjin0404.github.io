---
title:  "[Week 4] Day14"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-02-09
last_modified_at: 2022-02-09
---





## 오늘 학습한 내용

- [x] Sequential model 발전
- [x] LSTM의 각 gate의 의미
- [x] Transformer



## RNN

* recurrent Neural Networks
* sequential Model은 몇 개의 입력이 들어오든 동작할 수 있어야 한다.
* Autogressive model : 고려하는 과거의 정보의 timespan이 정해져 있다.
* Markov model : 바로 이전의 정보만을 의존한다.
* Latemt autogressive model : 과거의 정보를 summarize하는 hidden state를 갖는다.
* RNN 문제점 Short-term dependencies : hidden state에 이전의 정보가 입력되고 activation function을 지나는데, 과거의 정보일수록 활성화 함수를 많이 거쳐서 Vanishing이 일어날 수 있다. 먼 과거일수록 잊혀지고 최근의 정보만을 사용하는 경향이 있다. 혹은 ReLU를 사용하면 gradient exploding이 일어난다.
* LSTM : 이 전의 정보를 summarize한 cell state, 이전의 output(hidden state), input 벡터가 입력된다.
  * Forget gate : 이전 output과 입력벡터를 고려해서 이전 cell state를 유지할지 결정한다.
  * Input gate : cell state에 어떤 정보를 입력할지 결정한다.
  * Update gate : forget gate와 input gate를 고려해서 cell state를 update한다.

<img src="https://user-images.githubusercontent.com/86605720/153013875-e12b0ab2-b602-4729-a6a1-f169e0ef1509.png" alt="image" style="zoom:40%;" />

* GRU : LSTM과 마찬가지로 hidden state가 output이다. cell state가 없다. 학습할 parameter가 더 적고 일반적으로 LSTM보다 성능이 좋다.



## 피어세션 및 느낀점

* 면접질문과 코드리뷰를 했고, 강의에서 자세하게 다루지 않고 소개하고 넘어가는 부분을 좀 더 자세히 알아보기로 했다. ex) activation function, batch normalization 등등
* 느낀점으로는 교수님께서 각 네트워크와 딥러닝 개념을 이해가 잘되게 직관적으로 설명해주시는 것 같다. 혼자 논문을 보고 공부했으면 중요하게 생각하지 못하고 넘어갔을 부분들이 어떤 의미가 있는지 인사이트를 제공해주셔서 만족스럽다. 특히 단순하게 개념과 키워드를 나열하는게 아니라 어떤 점을 보완하기 위해 발전했는지를 알려주시면서 공부할 가이드를 제시해주셔서 다음에 관련 논문을 읽을 때 더 수월하게 읽고 중요한 부분을 놓치지 않고 공부할 수 있을 것 같다.
