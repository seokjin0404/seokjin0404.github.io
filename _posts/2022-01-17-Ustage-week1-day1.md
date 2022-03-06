---
title:  "[Week 1] Day1"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-17
last_modified_at: 2022-01-17
published: false
---

# 오늘 학습한 강의

- [x] (Python 1-1강) 
- [x] (Python 1-2강)
- [x] (Python 1-3강)
- [x] (AI Math 1강)
- [x] (AI Math 2강)



---



# 1. 벡터가 뭔가요?

* 숫자를 원소로 가지는 list 또는 array, 공간에서 한 점

* 벡터의 연산

  * 벡터는 원점으로부터 상대적 위치를 표현한다.
  * 벡터의 덧셈과 뻴셈은 다른 벡터로부터 상대적인 위치이동을 의미한다.
  * numpy에서 차원이 같아야 연산이 가능하다.

* 성분곱(Hadamard product)

  * 크기가 같은 행렬 또는 벡터를 각 성분끼리 곱하는 연산

* 벡터의 노름(norm)

  * 원점으로부터 거리를 의미하는데 L1노름 ,L2노름 다양하게 정의할 수 있다.

  * 정규화 등에 사용될 수 있는데, 어떤 norm을 사용할지는 데이터의 성질에 따라서 결정할 수 있다.

  * 기하적인 특징을 이해해서 목적에 따라 적절하게 이용

    참고링크 : [https://ratsgo.github.io/machine%20learning/2017/05/22/RLR/](https://ratsgo.github.io/machine%20learning/2017/05/22/RLR/)

* 두 벡터 사이의 거리 및 각도

  * 길이 : 벡터의 뺄셈 이후 L2 노름을 적용
  * 각도 : 두 백터의 내적을 각 벡터의 L2 노름으로 나눠준 뒤 arcos 적용

---

# 2. 행렬은 뭔가요?

* 백터를 원소로 가지는 2차원 배열

* 행렬은 n개의 행벡터, 각각의 행 벡터는 m개 성분을 갖는 것으로 

* 행렬을 이해하는 방법

  * 공간에서 여러 점

  * 선형 변환의 연산자

    참고영상 : [https://www.youtube.com/watch?v=kYB8IZa5AuE](https://www.youtube.com/watch?v=kYB8IZa5AuE)

    행렬의 열벡터가 변환된 행렬의 기저 벡터가 되는데, 선형변환을 직관적으로 이해하는데 도움을 주는 영상

* 행렬곱

  * 연산자 numpy에서 @를 사용
  * np.inner 활용
    * i번째 행벡터와 j번째 행벡터 사이의 내적을 성분으로 가지는 행렬
    * 두 행렬 X와 Y에 대해서 X @ Y.T 와 np.inner(X,Y)는 같은 결과를 갖는다.

  * 역행렬 이해하기

    * 모든 경우에서 가능한 것은 아니고, 행과 열의 숫자가 같고, determinant가 0인 경우에 가능

      참고영상: [https://www.youtube.com/watch?v=uQhTuRlWMxw&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=7]( https://www.youtube.com/watch?v=uQhTuRlWMxw&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=7)

    * Moore-Penrose 역행렬
      * 역행렬을 계산할 수 없을 때 사용
      * numpy에서 np.linalg.pinv를 사용
      * 행이 열보다 길때 항등행렬을 만드려면 유사역행렬을 원래 행렬에서 왼쪽에서 곱해주면 된다.

---

# 피어세션

* 6주 동안 피어세션 같이 할 조원들이 정해졌는데, 그동안 지켜야될 규칙을 만들었다.
* 다른 조들과 다른 규칙을 하나 꼽자면, 매일 공부한 내용을 블로그에 포스팅해야된다는 것이다.
* 공부하다 모르는 부분, 과제에 대해 질문하고 토론하는 시간이 될 것 같다.
* 돌아가면서 피어세션에 나눈 내용을 기록해주기로 했는데, 5주차에 moderator를 맡기로 해서 그 주만은 결석이 없어야할 것 같다.



---

# 느낀점

* 컨텐츠 유출 때문에 자세한 내용을 담기 힘들 것 같아서 하루에 배운 내용 전체적으로 요약하는 느낌인데 다음부터는 모르는 부분이나 스페셜 과제를 풀때 알아야 되는 내용이 있으면 따로 조사해서 자세하게 기록하는 파트를 포스팅에 담아야겠다.
* 벡터 norm과 행렬연산에 대해 링크를 달아놨는데, 다음부터는 팀원들과 더 쉽게 공유할 수 있게 정리를 해놔야겠다. ~~오늘 포스팅도 시간나면 수정해야지~~