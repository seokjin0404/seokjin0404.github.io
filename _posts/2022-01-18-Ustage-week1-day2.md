---
title:  "[Week 1] Day2"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-18
last_modified_at: 2022-01-18
published: false
---

# 오늘 학습한 강의

- [x] (Python 2-1강) 
- [x] (Python 2-2강)
- [x] (AI Math 3강)
- [x] (AI Math 4강)



---

# (Python 2-1) Variables

* Variable

  * 변수(variable)란 특정한 값(value)을 저장하는 장소로, 메모리 주소를 가지고 있다.

  * 선언 되는 순간 메모리 특정 영역에 물리적인 공간이 할당된다.

    ```python
    a = 1		# a 라는 이름을 가진 메모리 주소에 1을 저장한다. 
    a = a + 1	# 좌변의 a : 변수, 우변의 a : 기존 a에 저장된 값
    ```

  * 변수 이름을 작성할 때 키워드를 사용하지 말것

    [파이썬 키워드](https://realpython.com/python-keywords/)

  * data type에 따라 차지하는 공간이 달라진다.

  * Dynamic Typing

    실행하는 시점에 메모리 크기를 정해줘서 속도가 느리다. python을 포함한 interpreter 언어를 포함

    JAVA 같은 compiled 언어는 어떤 type인지 명확하게 선언해야 한다.

* list

  * 하나의 변수에 여려개의 data를 저장하기 위한 구조

  * 파이썬의 특징으로 int, float,string 등 다양한 type을 가질 수 있다.

  * copy 할 때 주의할 점

    ```python
    #다음과 같이 두개의 서로 다른 list를 선언하면,  a와 b는 서로 다른 메모리 공간을 가리킨다.
    a = [5, 4, 3, 2, 1]
    b = [1, 2, 3, 4, 5]
    ```

  * 잘못된 copy

    ```python
    b = a
    # b가 원래 가르키던 주소를 가르키지 않고 a가 가르키는 주소를 가르킴
    a.sort()
    print(b)
    # a를 바꿨는데, b를 출력하면 [1, 2, 3, 4, 5]가 출력될 것
    ```

  * 올바른 copy

    ```python
    import copy
    
    a = [5, 4, 3, 2, 1]
    b = [1, 2, 3, 4, 5]
    b = copy.deepcopy(a)
    a.sort()
    print(b)
    # a를 바꾼 뒤에 b를 출력하면 b는 그대로 [5, 4, 3, 2, 1]이 출력될 것
    
    b = a[:]
    # 1차원 list는 slicing을 통해서 deepcopy가 가능한데, 
    # 2차원 list는 불가능하다. copy.deepcopy()를 이용해야함
    ```



---

# (Python 2-2) Function and Console I/O

* 함수

  * parameter 유무, return value 유무에 따라 형태가 다르다.

    ```python
    def f(x):
    	return x
    ```

    shell에서 f(2)를 출력하면 반환값이 존재하기 때문에, 2가 출력된다.

    그리고 c = f(2)를 입력해주면 아무것도 출력되지 않는다.

    하지만 c를 입력하면 2가 출력된다.

    ![image](https://user-images.githubusercontent.com/86605720/149945519-bef734bc-f074-4609-93f6-b7b21122a7a6.png)

    비슷한 함수지만 반환값이 없고, 수행문만 존재하는 함수를 보자.

    ```python
    def f(x):
    	print(x)
    ```

    앞의 함수와 어떤 차이가 있을까?

    shell에서 f(2)를 입력하면, 2가 출력된다. 

    그리고 c = f(x)와 같이 입력하면,  마찬가지로 2가 출력된다.

    하지만 c를 입력하면, 아무것도 출력되지 않는다.

    반환값이 없기 때문에, c에는 None이 할당됐기 때문이다. 

    c = f(x)에서 2가 출력된 이유는 print(x)가 실행된 것이지 c의 값을 보여준 것이 아니다.

    ![image](https://user-images.githubusercontent.com/86605720/149946004-1f7c7c31-0a34-4006-b481-c3dbc88ef6e8.png)

    ```python
    def f(x):
    	return print(x)
    ```

     shell 에서 f(2)를 입력하면 어떤 결과가 출력될까? 2가 출력된다. print(x)가 실행됐기 때문이다.

    c = f(10)을 실행하면 어떻게 될까? 2가 출력되는데, 앞의 함수와 마찬가지로 print(x)가 실행됐기 때문이다.

    c를 입력하면 아무것도 출력되지 않는다. print에 return이 없기 때문에 c에 None이 할당됐기 때문이다.

    ![image](https://user-images.githubusercontent.com/86605720/149946682-509fd3a3-9eba-4a0e-a1be-87206acacdcc.png)

* console in/out
  * 위의 이미지같은 console창 .py로 끝나는 함수를 입력하면 그 파일을 실행할 수 있다.
  * input() 함수는 콘솔창에서 문자열을 입력 받는 함수다. type은 string으로 받는다.
  * print("Hello world!", "Hello Again")처럼 콤마를 사용하면 한칸씩 띄어서 출력된다.
  * 붙여서 출력하고 싶으면 +를 사용하면 된다. str으로 형변환 후 concatenate하는 식

---

# (AI Math 3) 경사하강법 순한맛

* 경사하강법

  * 미분을 활용해서 극대값, 극소값을 찾을 수 있다.
  * 기울기가 음수일 때,  오른쪽으로 움직이면 값이 감소하고 기울기가 양수일 때, 왼쪽으로 움직이면 값이 증가할 것

  ```python
  while(abs(grad) > eps):
  	var = var - lr * grad
      grad = gradient(var)
  ```

  2번째 줄에서 본 것처럼 update한 기울기를 뺴야한다.

  lr은 learning rate로 업데이트하는 속도를 조절하는 hyperparameter

* gradient vector

  * 각 변수별로 편미분한 값을 원소로 갖는 벡터
  * 기하적으로는 가장 급격하게 변하는 방향을 나타낸다.
  * 벡터가 입력인 다변수 함수에서는 종료조건으로 절대값이 아닌 norm을 계산함.

---

# (AI Math 4) 경사하강법 매운맛

* 경사하강법으로 선형회귀 계수 구하기
  * 기울기에 따른 2차 norm의 계산으로 손으로 써봤는데, 좀 더 정리해서 update할 예정
  * 이번주 심화과제로 관련문제가 올라왔는데, 올려도 되는지 물어보고 코드를 설명해야겠다.
* 확률적 경사하강법 (SGD)
  * 경사하강법의 한계
    * 볼록한 구간이 하나일 때, convex한 함수라하는데, non-convex한 함수에 대해 수렴이 보장되지 않는다.
    * non-convex인 함수이면 수렴한다고 해도 최소값이 아닐 수 있다. 최소값이 아닌 극소값에서 학습이 멈추기 때문이다.
    * 모든 데이터를 사용하기 때문에 메모리가 부족해서 out-of-memory가 발생할 수 있다.
  * sgd 원리
    * 전체 데이터가 아닌 일부의 mini batch 를 가지고 gradient vector를 계산한다.
    * 전체 데이터가 아니기 때문에, 목적식과 gradient vector가 실제값과 다르다.
    * 일반적인 경사하강법에서는 극소값에서 학습이 멈추지만, sgd의 경우 위와 같은 이유로 극소값에서 벗어날 수 있다.
    * non-convex한 함수에 대해 최소값을 찾을 수 있고, 메모리를 효율적으로 사용할 수 있다.

---

# 피어세션

* 초반이라 어려운 내용이 많지 않아서인지 나눌 얘기가 많지 않았다.
* 이번주에 심화과제가 3개 올라왔는데, 첫 심화 과제에 5개 문제가 있어서 내일 피어세션에 랜덤으로 각자 한문제씩 설명하기로 했다.
* 내일 있을 **피어세션이 피어씁니다**의 발표준비를 했다.

---

# 느낀점

* 과제와 퀴즈는 생각보다 쉬운것 같고, 심화과제가 어렵다. 시간을 다 쓴 것 같다!