---
title:  "[Week 1] Day5"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-21
last_modified_at: 2022-01-22
published: false
---

# 오늘 학습한 강의

- [x] (Python 4-1강) 
- [x] (Python 4-2강)
- [x] (AI Math 9강)
- [x] (AI Math 10강)



# (Python 4-1강) python object oriented programming

* 객체 지향 언어를 사용하는 이유 : 코드를 효율적으로 재사용하기 위해

* 유명한 비유로 class를 설계도, instance는 설계도를 바탕으로 구현된 실체라고 한다.

* attribute : 속성 정보를 저장

  ```python
  class SoccerPlayer(object):
  	def __init__(self, name, number):
  		self.name = name
  		self.number = number
      def __str__(self):
          return 
  # __init__ : 객체를 초기화해주는 함수
  # __str__ :  객체를 출력할 수 있게 해주는 함수
  ```

* 이 외에도 다양한 예약함수가 있음

* method : 객체를 초기화 하고 class 내부 함수를 정의함

* self : 생성된 instnace

* 상속 : 부모 class로부터 속성과 method를 상속받을 수 있다.

```python
class Person(object):
	def __init__(self, name, age)
		self.name = name
		self.age = age
class Korean(Person):
	Pass

# Korean이 부모 class Person으로부터 attribute를 상속받았다. 코드를 효율적으로 재생산할 수 있다.
```



# 피어세션

* 일주일간 회고한 결과 좋은 점으로 팀원들이 매일 블로그에 공부한 내용을 포스트 한것을 꼽았다.
* 모든 내용을 담아야할지, 처음보는 내용을 깊게 담을지 팀원들 포스팅을 보며 조율해야겠다.
* 아쉬운점은 초기에 계획했던 심화과제 발표가 잘 안지켜진 것 같다.
* 다음주부터는 심화과제를 풀기 위해 요구되는 강의를 잘 알아보고 커리큘럼을 잘 구성해야겠다.
* further question이나 참고자료를 review해주는것도 좋은것 같다. 

​		

