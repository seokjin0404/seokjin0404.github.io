---
title:  "[Week 1] Day4"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-21
last_modified_at: 2022-01-21
published: false
---

# 오늘 학습한 강의

- [x] (Python 3-1강) 
- [x] (Python 3-2강)
- [x] (AI Math 7강)
- [x] (AI Math 8강)

# (Python 3-1) Python Data Structure

* stack
  * 선입후출 구조
  * pop()
    * ex) sort() 함수 return 값이 없고, sorted(list) list가 정렬되진 않지만 정렬된 list를 return 한다.
    * 나중에 들어온 요소가 삭제되고, 그 삭제된 값을 반환한다.
    * python의 list를 이용해 구현할 수 있다.
    * pop()에 index를 넣으면 그 요소를 삭제할 수 있다.
* queue
  * 선입선출 구조
  * put을 append, get으르 pop(0)사용
* tuple, set, dictionary
* collections
  * deque
    * stack과 queue를 지원한다.
    * 기존 list보다 메모리 구조가 효율적이고, linked list의 특성을 지원한다.
  * OrderedDict, defaultdict, Counter, nametyple 등 다양한 자료구조를 지원한다.

---

# Pythonic code

* split & join

* list comprehension

* enumerate & zip

* lambda & map & reduce

* iterable object

  * 기존의 list는 메모리 주소가 값을 가르키는 형태
  * iter() 함수로 메모리 구조가 linked list로 바뀜
  * next() 함수는 다음 메모리 주소의 값을 불러옴

* generator

* function passing arguments

  * Variable-length arguments

  * 가변인자

    * 기존 parameter이후에 나오는 값을 tuple로 저장한다.

    ```python
    def asterisk_test(a,b,args):
    	return a, b, sum(args)
    	
    print(asterisk_test(1,2,3,4,5)) // a = 1, b = 1 args = (3,4,5)
    ```

    ```python
    def asterisk_test_2(*args):
    	x, y, z = args // 함수 내부에서 3개로 unpacking 하기 때문에, 4개 이상 받으면 error
    	return x, y, z 
    	
    print(asterisk_test_2(3,4,5)) // parameter *args에 (3,4,5)가 tuple로 저장
    ```

  * 키워드 가변인자

    * asterisk 두개를 사용, 입력된 값은 dict type으로만 사용할 수 있다.
    * 가변인자, 키워드 가변인자 순으로 parameter를 받아야 한다.

    ```python
    def kwargs_test_3(one, two, *args, **kwargs):
    	print(one, two, sum(args), kwargs)
    	
    kwargs_test_3(3,4,5,6,7,8,9, first = 3, second =4 , third = 5)
    
    # 3 -> one, 4 -> two, kwargs -> fist, second, third가 key인 dictionary
    # args는 나머지 값이 tuple로
    ```

  * asterisk - unpacking

    * 함수의 parameter가 아닌 list나 tuple 등 앞에 *이 붙으면 unpacking이 일어난다.
    * 가변인자와 차이가 있으니 주의해야 한다.

    ```python
    for data in zip(([1,2],[3,4],[5,6])):
    	print(data)
    # 결과는 ([1,2], [3,4], [5,6]) 하나의 객체가 data에 할당되므로
    #([1,2], [3,4], [5,6]) 이 출력된다.
    
    for data in zip(*([1,2],[3,4],[5,6])):
    	print(data)
    # 결과는 (1,3,5), (2,4,6) *때문에 [1,2], [3,4], [5,6]으로 unpacking된 후 zip
    #([1,2], [3,4], [5,6]) 이 출력된다.
    ```

---

# (AI 8강) 통계학 맛보기

* 이번 강의를 통해 통계학이 딥러닝에 활용될 수 있는 사례를 몇가지 알 수 있다.
* 분류 문제에서 손실함수를 왜 cross entropy를 사용하는지에 대해 궁금했는데, 딥러닝을 통해 예측한 확률분포와 정답 label의 확률분포의 거리를 구하기 위함을 알았다.
* 분류 문제에서 loss function을 최소화하는 것이 쿨백 라이블러 발산을 최소화하는 것과 같다.
* 다른 문제에서도 어떤 손실함수를 사용하는 이유가 maximum likelihood  estimation과 관련있는 경우가 많다.
* 정규분포의 모수
  * 표본 평균의 평균은 모집단의 평균과 같고, 분산은 모분산과 비례하고 표본의 크기에 반비례한다.
  * 즉 표본이 커질수록 표본 평균의 값이 모집단의 평균과 같을 확률이 커지는 것이다.
* 최대가능도 추정법
  * 표본이 어떤 확률 분포를 따르는지 알고 싶을 때, 가장 가능성이 높은 모수를 추정하는 방법이다.
  * 심화과제와 관련된 직관적인 예시를 하나 들자면, 내가 만약 대한민국에서 성인 남자 3명을 무작위로 뽑았을 때, 세명의 키가 각각 170, 175, 180이라고 하자.
  * 그리고 최대가능도 추정법은 모수가 변수이므로 평균을 정해놓고 최대가능도를 비교해보는 것이다.
  * 우리나라 평균키가 170일 때, 170, 175, 180이 뽑힐 확률
  * 우리나라 평균키가 175일 때, 170, 175, 180이 뽑힐 확률
  * 우리나라 평균키가 180알 때, 170, 175, 180이 뽑힐 확률
  * 위처럼 특정 모수를 따르는 정규분포의 확률을 구해서 각 케이스 별로 구해보면
  * likelihood가 175일 때 가장 큰 값을 가질 것이다. 그래서 키에 대한 확률분포의 모수를 175로 추정하는 것이다.
  * 정규분포의 최대가능도 추정법 예제는 심화과제에서 풀어봤다. 