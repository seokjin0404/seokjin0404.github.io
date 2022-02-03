---
title:  "[Week 2] Day10"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-02-03
last_modified_at: 2022-02-03
---

# 오늘 학습한 내용

- [x] (Pytorch 8강) 
- [x] (Pythorch 9강)
- [x] (Pytorch 10강)

___

<br/>

# Pytorch 8강 Multi-GPU 학습

**Model parallel**

* 모델을 나눠서 다른 GPU에서 병렬적으로 학습시킨다.
* GPU가 데이터를 동시에 처리해야 의미가 있다. batch 처리가 중요하다.
* 병목 현상이 일어나지 않게 pipeline을 잘 만들어서 GPU가 계속 사용돼야한다.

**Data parallel**

* 데이터를 나눠서 미니 배치를 병렬적으로 돌린다. 모델을 각각의 GPU에 복사하고 연산한 결과값을 하나의 GPU로 모아서 loss를 한번에 계산한다.  그리고 각각의 GPU에서 gradient를 계산하고 다시 하나의 GPU에서 평균을 구해서 gradient를 update한다. 하나의 GPU가 데이터를 모으고 다시 나눠주는 일을 하기 때문에 GPU 사용에 불균형이 생긴다.
* `torch.nn.DataParallel()` 로 구현가능

**DistributedDataParallel**

* Data parallel 과는 다르게 데이터를 모으는 과정이 없고 각각 GPU에서 개별적으로 gradient를 계산하고 update한다. GPU만큼 CPU를 할당하는 방식을 사용한다.

* ``torch.utils.data.distrivuted.DistributedSampler()`` 로 sampler를 만들어야 한다.
* ``torch.utils.data.DataLoader()`` 로 다음의 parameter를 사용한다.
* ``shuffle = False``, ```pin_memory = True```, ```num_workers``` : 보통 GPU의 4배를 사용한다.

<br/>

---

# 피어세션

* 다음주부터 https://github.com/boostcamp-ai-tech-4/ai-tech-interview 에서 하루에 한문제씩 설명할 예정이다.

* 멘토링까지 해서 이것저것 준비할게 많은 것 같다.