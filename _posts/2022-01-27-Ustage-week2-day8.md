---
title:  "[Week 2] Day7"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-26
last_modified_at: 2022-01-26
---

# 오늘 학습한 내용

- [x] (Pytorch 5강) 
- [x] (Pythorch 6강)
- [x] (Custom Dataset 및 Custom DataLoader)

---

# (Pytorch 5강) 데이터셋, 데이터로더

## 1. Custom dataset

* dataset은 데이터를 입력 받는 클래스이다.
* image, text 다양한 이미지를 입력받는데, 데이터에 따라 다르게 정의한다.
* Custom dataset은 torch.utils.data에서 Dataset class를 상속받아 만들 수 있다.
* 기본적인 구조는 다음과 같다.
  * ``__init__`` : 데이터나 디렉토리를 초기화한다.
  * ``__len__`` : 데이터의 길이를 정해준다.
  * ``__getitem__`` : index를 주어졌을 때 값을 반환한다. dataloader에서 호출된다.  

___



<br>

## 2. dataloader의 parameter

* sampler와 random shuffle

[example sampler](https://www.scottcondron.com/jupyter/visualisation/audio/2020/12/02/dataloaders-samplers-collate.html#Samplers)

* num_workers

 머신러닝을 효율적으로 하기 위해서는 CPU와 GPU가 원활하게 돌아가야한다. CPU는 데이터를 전처리 하고 모델에 데이터를 feed하는 역할을 하고 GPU는 모델을 학습시킨다. 단순히 GPU만 빠르다고 효율적인 것이 아니라 CPU의 속도가 느리면 GPU가 쉬는 시간이 생긴다. dataloader의 parameter 중에 num_workers가 있는데 CPU 코어 개수를 할당해주는 것이다.  하지만 num_workers를  무작정 늘려주면 병목현상이 일어나기 때문에 적절한 num_workers를 지정해 주는 것이 필요하다.

[num_workers](https://jybaek.tistory.com/799)

* collate_fn

dataloader에서 data와 label을 전달받으면 (data1, label1),(data2, label2), (data3, label3)... 이런식으로 같은 데이터들끼리 받는데, (data1, data2, data3 ...), (label1, label2, label3 ..) 이런식으로 data끼리 label끼리 전달받을 수 있다. 하나의 배치에 다른 크기의 data가 들어오면 padding을 시켜서 크기를 맞춰줄 수도 있다.

* dataset, batch_size 등등..
* drop_last : 마지막 batch의 크기가 다르면 학습에 넣어주지 않는다.

* transformer 함수
* transforms.ToTensor : 데이터의 크기를 0~255에서 0~1로 scaling 해준다.

---

<br>

# 피어세션 및 느낀점

1. pandas 라이브러리가 익숙하지 않아서 과제를 푸는데 조금 햇갈렸다.
2. 매일 배운 내용을 기록하는 것도 좋지만 특정 topic을 잡고 자세하게 쓰는 것이 더 좋다는 생각이 든다. 매일 쓰지 않으면 벌칙이 있는데 일주일에 몇 회씩 정해두고 쓰게하는게 좋지 않을까 생각이 든다.