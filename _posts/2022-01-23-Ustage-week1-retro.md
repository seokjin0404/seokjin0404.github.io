---
title:  "[Week 1] 주간 회고"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-23
last_modified_at: 2022-01-23
published: false
---

# 1. 학습내용 정리

 학습내용 정리는 다음과 같습니다.  첫날과 둣째날은 그날 강의로 학습한 모든 내용을 담으려했지만, 원래 알고 있던 내용까지 담으려하니 효율적이지 못한것 같았습니다. 셋째날과 넷째날은  새로 알게된 내용의 개념을 담으려 했지만, 단순히 개념 요약을 하는 것은 제가 정리한 내용보다 타 블로그에 키워드를 검색해서 보는게 더 효과적일 것이라 생각했습니다. 그래서 목요일 통계학입문 부분에서는 개념을 설명하는 것보다는 제가 학습하면서 깨달은 부분을 복습하면서 읽을때, 바로 이해될 수 있도록 직관적인 예시를 달았습니다.

 다음주부터는 직관적인 예시와 개념 자체는 더 잘 정리된 블로그나 타 사이트 링크를 걸어두고, 교수자님이 소개해주신 다른 자료에 대한 review와 further question에 대해 고민한 내용을 담을 생각입니다.

 

* [Day1](https://seokjin0404.github.io/ustage/Ustage-week1-day1/)

- [x] (Python 1-1강) 
- [x] (Python 1-2강)
- [x] (Python 1-3강)
- [x] (AI Math 1강)
- [x] (AI Math 2강)

* [Day2](https://seokjin0404.github.io/ustage/Ustage-week1-day2/)

- [x] (Python 2-1강) 
- [x] (Python 2-2강)
- [x] (AI Math 3강)
- [x] (AI Math 4강)

* [Day3](https://seokjin0404.github.io/ustage/Ustage-week1-day3/)

- [x] (Python 2-3강) 
- [x] (Python 2-4강)
- [x] (AI Math 5강)
- [x] (AI Math 6강)

* [Day4](https://seokjin0404.github.io/ustage/Ustage-week1-day4/)

- [x] (Python 3-1강) 
- [x] (Python 3-2강)
- [x] (AI Math 7강)
- [x] (AI Math 8강)

* [Day5](https://seokjin0404.github.io/ustage/Ustage-week1-day5/)

- [x] (Python 4-1강) 
- [x] (Python 4-2강)
- [x] (AI Math 9강)
- [x] (AI Math 10강)

---

# 과제 수행 과정 및 결과 정리

## 심화과제 1

![image](https://user-images.githubusercontent.com/86605720/150679312-b25c3c7f-62ba-4597-a48d-f6799c1794b9.png)

심화과제 1번을 모두 풀었고, 피어세션에서 저는 3번 풀이를 발표했습니다.

저는 심화과제 1번의 경우 3번 linear regression에서 gradient_w와 gradient_b를 작성하는것이 어려웠는데

수업 중 loss function의 그레디언트 벡터를 손으로 유도해보라는 교수님 말을 듣고 해보니 직관적으로 이해가 돼서

gradient_w = - np.inner(train_x,(train_y - _y)),  gradient_b = - np.sum(train_y-_y)와 같이 작성해서 정답을 구했습니다.

## 심화과제 3번

![image](https://user-images.githubusercontent.com/86605720/150679726-c22aa155-01b9-4bff-9943-2ef738f08882.png)

TODO 1,2,3을 편미분을 이용해서 구했고 정규분포의 모수를 추정했습니다.

TODO 4,5로 각 경우에 따른 그래프를 그려보니 mle를 직관적으로 이해할 수 있었고

비슷한 예시를 정리해서 [DAY4](https://seokjin0404.github.io/ustage/Ustage-week1-day4/)에 정리해두었습니다.

# 피어세션 정리

* 심화과제를 번호를 나눠서 조원들끼리 발표하는 시간을 가지려했는데 심화과제 1번만 서로 풀이를 공유했고 심화과제2번과 3번은 나누지 않았습니다. 다음주부터는 커리큘럼을 잘 설정해서 과제 풀이가 업로드되기 전에 서로의 풀이를 공유해야할 것 같습니다.
* 멘토링 시간을 가졌는데, 멘토님께서 배우는 내용을 그 자체로만 기억하는 것을 넘어서 어디에 활용될 수 있을지 고민해보라고 하셨습니다. 교수님들이 수업 중에 제안하는 further question이나 참고자료를 보고 더 심도있게 이해해야할 것 같습니다.
* 피어세션 시간에 서로 모르는 것을 질문하자고 했는데, 난이도가 어렵지 않다고 생각했는지 질문이 많지 않았던 것 같습니다. 교육을 좀 더 받으면 kaggle 풀이를 같이 리뷰해보고 논문을 분석하는 시간을 가져봐야할 것 같습니다.



