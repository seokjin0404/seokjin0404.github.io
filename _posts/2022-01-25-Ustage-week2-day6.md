---
title:  "[Week 2] Day6"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-23
last_modified_at: 2022-01-23
published: false
---

# Pytorch 1일차

* numpy operation과 유사하게 작동함
* tensor가 가질 수 있는 data type이 numpy와 유사하다.
* ex) torch.ones_like(x_data) : x_data와 같은 shape로 1을 채운 tensor
* view vs reshape
  * tensor의 shape를 바꿔준다.
  * contiguity 보장에 차이가 있다.
  * b = a.view(2,3)  : b가 a의 메모리를 가져와서 이후에 a를 바꾸면 b의 값도 바뀐다.
  * b = a.reshape(2,3) : 값을 copy하기 때문에 a와 b가 독립적으로 작동한다.
  * reshape보다는 view를 사용하는 것이 더 일반적이다.  

* mm vs matmul

  * 행렬곱을 수행하는 함수

  * a.mm(b) : broadcasting 연산을 지원하지 않는다.

  * a.matmul(b) : broadcasting을 지원한다.

  * 따라서 mm을 사용하는 것이 더 일반적이다. 왜냐하면 broadcasting이 지원되면

    의도치 않은 결과가 나올 수 있기 때문이다.

* 자동 미분의 지원

  * pytorch의 핵심으로 자동 미분을 지원한다.
  * tensor를 선언할 때, parameter로 requires_grad = True를 입력하면, 미분의 대상이 된다.
  * 미분의 대상이 된 변수를 포함하는 수식을 미분할 때는 backward() 함수를 사용하면 된다.

  ```python
  w = torch.tensor(2.0, requires_grad = True)
  y = w **2
  z = 10*y + 25
  z.backward() //자동 미분 연산 수행
  w.grad // w에 대한 z의 미분값
  ```



___

# 피어세션

1.  이번주엔 3개의 과제가 할당됐는데 목요일 오전까지 제출해야 한다.
2.  화요일에 금일 기본과제에 대해 토의하고 수요일에 두번째 기본과제를 토의할 것 같다.
3.  내일 피어세션 전에 github에 과제를 업로드할 예정



___

# 느낀점

1.  이번 과제에느 pytorch를 익히기 위해 읽어야할 자료들과 예제를 포함됐다.
2.  정말 정성스럽게 만들어주셨다는 생각이 들고 그 과제 파일 자체가 정말 좋은 학습 자료라는 생각이 들었다.
3. 강의 시간이 상대적으로 적었지만 과제에 큰 시간을 쏟아야할 것 같다.