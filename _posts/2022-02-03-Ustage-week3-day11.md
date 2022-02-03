---
title:  "[Week 3] Day11"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-02-03
last_modified_at: 2022-02-03
---

## 학습 요약

- [x] 데이터의 종류에 따른 적절한 시각화 기법 선택의 중요성
- [x] 전달력과 가독성을 높이기 위한 시각화 기법
- [x] matplotlib 기초 문법 및 Bar plot, Line plot, scatter plot

<br>

## 데이터 이해하기

* 데이터셋의 종류
* 정형데이터, 시계열데이터, 지리데이터, 관계데이터
* 수치형 데이터, 범주형 데이터
* Pre-attentive attribute : 인지하기 쉽게 적절하게 사용하는 것에 주의

<br>

## Bar plot

* 그룹 데이터의 시각화
* 여러 그룹을 동시에 보여주기 위해 여러가지 방법이 있다.
* stacked bar plot : feature 전체에 대한 정보를 전달하는데는 좋지만, 각 그룹의 분포를 파악하기 힘들다.
* Overlapped Bar plot : 2개의 그룹을 비교할 때 사용하는데 가독성을 위해 투명도를 조절하는 것이 중요
* Grouped Bar Plot :  5개 ~7개 이하의 그룹을 비교할 때 효과적, seaborn에서 쉽게 구현 가능

<br>

## Line plot

* .plot() 함수를 사용한다. 시계열 분석에 용이하다.
* 선의 개수를 너무 많이 사용하는 것을 지양. 가독성을 위해서
* 너무 자세하게 noise까지 시각화할 필요 없다. 구간별 평균을 이용해서 전처리를 할 수도 있다.
* 기울기에 대한 정보가 중요하기 때문에, x축의 간격을 규칙적으로
* 점과 점 사이의 데이터를 보간하기 때문에 적절하게 관측한 점을 표시해야 한다. 그렇지 않으면 실제 관측하지 않고 보간돼서 나타난 점을 실제 있는 점으로 착각할 수도 있다.
* 이중축 사용 : 인과관계를 오인시킬 수 있기 때문에 지양. 가독성에도 좋지 않음. 두개의 plot을 비교하고 싶으면 각각 병렬적으로 보여주는 것이 더 좋다.

<br>

## Scatter plot

* 데이터의 feature간 관계를 추정하기 위해 사용한다.
* 색, 모양, 크기로 데이터를 구분할 수 있다. 가독성을 향상시키는 방향으로 적절히 선택하는 것이 중요
* 상관관계, 군집, 이상치 확인 등에 사용

<br>

## 피어세션

* pytorch 심화과제 리뷰
* Fashion MNINST를 분리하기 위해 resnet18을 사용했는데, imageNet으로 pretrained된 model, MNIST로 pretrained된 model, pretrained되지 않은 모델로 학습시켰는데, pretrained 되지 않은 모델, MNIST로 pretrained된 model, imageNet으로 pretrained model 순으로 성능이 미세하게 좋았다.
* imageNet으로 pretrained된 model을 사용하는데, layer1만 freeze, layer1과 layer2를 freeze, 아무것도 freeze하지 않고 학습시킨 결과 freeze를 사용하지 않은 순서로 성능이 미세하게 좋았다.
* 코드를 맞게 작성한것인지 확인해야 될 것 같고, 이유에 대해서 생각해볼 것 같다.
* eigen value, vector에 대한 면접질문 답변을 준비했는데, 내일은 R square에 대한 답변을 준비할 예정
