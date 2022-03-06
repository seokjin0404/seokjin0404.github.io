---
title:  "[Week 2] Day7"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-26
last_modified_at: 2022-01-26
published: false
---

# 오늘 학습한 내용

- [x] (Pytorch 4강) 
- [x] (Pythorch 5강)
- [x] (Custom Model 제작)



# (Pytorch 4강) AutoGrad & Optimizer

* nn.Module

  * 딥러닝을 구성하는 Layer의 base이다.

  * Layer뿐만 아니라, 또 다른 module을 담을 수 있다.

  * 학습의 대상이 되는 parameter가 정의된다.

  * ```python
    super().__init__()
    ```

  * pytorch에서 레이어 혹은 모델을 구성할 때 nn.Module을 상속받는다.
  * nn.Sequential, nn.ModuleList, nn.ModuleDict를 익힌다.

* nn.Parameter
  * Tensor 객체의 상속 객체
  * nn.Module 내의 attribute가 될 때는require_grad = True로 지정돼서 학습의 대상이된다.
  * nn.Module 내에서 파라미터를 nn.Parameter를 이용하지 않고 Tensor로 선언해서 사용하면 state_dict를 사용할 때 학습가능한 파라미터로 표시되지 않는다.
* 5강의 자세한 내용은 내일 2번 기초과제를 풀고 작성할 예정

---

# Custum Model 제작

* Pytorch 공식 documentation 을 읽어본다.
* tensor를 조작과 연산을 연습한다.
* 인덱싱 index_select, gather 등의 함수 사용법을 익힌다.
* torch.nn.Module 과 관련된 함수를 익히고 모델을 직접 분석해봤다.
* github에 올라온 모델을 참조하는 법을 배웠다.



___

# 피어세션

* 기본과제 1에 대한 내용을 나눴다.
* 내일 기본과제2를 하루종일 풀어보고 기본과제2에 대한 내용을 나눠야겠다.
* 내가 아직 풀어보지 못한 과제를 미리 풀어온 사람들에게 미리 설명을 듣고 (hook, apply) 모르는 부분을 물어볼 수 있어서 좋았다.
* 내가 풀어본 과제를 설명을 준비하면서 헷갈렸던 부분을 확실히 알 수 있게 됐다.(gather 함수로 임의의 3차원 텐서의 대각원소 뽑아내기) 