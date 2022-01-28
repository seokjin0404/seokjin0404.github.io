---
​---
title:  "[Week 2] Day9"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-01-28
last_modified_at: 2022-01-28

​---
---

# 오늘 학습한 내용

- [x] (Pytorch 6강) 
- [x] (Pythorch 7강)
- [x] 과제 복습

---

</br>

# (Pytorch 6강)

**torch.state_dict()**

* model 내부 layer와 parameter를 표시한다.
* optimizer의 parameter 도 표시할 수 있다.
* python OrderDict 객체이다.



**torch.save(obj, f)**

* obj : 저장하고자 하는 객체

​	parameter를 저장할 때는 model.state_dict()를 사용하고, model 자체를 사용할 수도 있다.

​	model.state_dict() 를 사용하는 것이 더 일반적이다.

* f : 저장경로이다. parameter를 저장할 때 확장자로 .pt를 사용한다.



**torch.load(f)**

* 경로에 저장된 모델을 불러올 수 있다.
* ``new_model = torch.load(path)`` 



**torch.load_state_dict(f)**

* 경로에 저장된 parameter를 불러올 수 있다.
* ``new_model.load_state_dict(path)`` : new_model은 path에 parameter를 저장한 모델과 같은 형태여야 한다.



**checkpoint** 

* torch.save() 에서 obj 인자로 epoch, model.state_dict(), optimizer.state_dict() 등을 담은 dictionary를 저장한다.
* checkpoint = torch.load(path) 의 형식으로 불러온다.
* 학습의 중간과정을 저장할 수 있는데 earlystopping에 사용할 수 있다.



**transfer learning**

* 이미 학습된 모델로 나의 데이터셋을 사용하고 싶을 때 사용한다.
* torchvision.models

​		alexnet, vgg, resnet 등 컴퓨터비전에서 자주 사용되는 backbone model이 저장돼 있다.

* parameter로 ``pretrained=True`` 를 넣어줘야 재대로 학습된다.
* 일반적으로 vgg 넷을 사용해서 image classification을 할 때, 내가 분류하고자 하는 class의 갯수에 따라 마지막 단에 ``nn.Linear()`` 를 포함시킨다. 일반적으로 transfer learning에서 기존모델을 수정하는 것은 지양된다.
* frozen : ``model.parameters()`` 로 parmeter를 불러와 parameter를 학습 불가능하게 만든다. ``requires_grad = False``
* 그리고 추가한 layer를 학습 가능한 parameter로 만들어 준다.



___

# 피어세션

* 랩미팅을 다녀오느라 피어세션에 참여하지 못했다.
* 오늘 저녁에 멘토링을 했는데 다음 멘토링 시간부터 각자 관심 있는 ai issue에 대해 조사해 오고 이야기 나눠볼 것 같다.
* 인공지능의 초보 단계이기 때문에 견문을 넓히고, 마지막 프로젝트 product serving를 미리 생각해보라는 취지인 것 같다. 
* u stage가 끝나는 1주~2주 전에는 ai에 관한 면접질문을 준비해주시는 것 같다.
* 열심히 해야겠다 ..^^
