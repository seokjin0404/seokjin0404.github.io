---
title:  "[Week 4] Day13"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-02-08
last_modified_at: 2022-02-08
---



## 오늘 학습한 내용

- [x] Activation functions
- [x] 다양한 Gradient Descent Methods의 특징 및 비교
- [x] CNN 발전 과정

<br>

## Activation functions

* 모델의 비선형성을 위해 사용한다. 분류 문제에서 구분선이 비선형적인 경우가 많다.
* Activation function이 없으면 층을 깊게 쌓아도 linear neural network와 같다.
* sigmoid의 경우 입력값이 0과 1에 가까울수록 gradient가 작아서 gradient vanishing이 일어난다. 학습이 잘 일어나지 않게 된다. 
* ReLU, Leaky ReLU, tanh 등 다양한 activation function이 있는데, ReLU가 가장 일반적으로 사용된다.



<br>

## Gradient Descent Methods

* momentum 

 현재 gradient와 이전 배치에서 얻은 gradient(momentum)를 포함해서 update 시킨다. gradient의 방향이 계속 바뀌어도 학습이 잘된다. 관성의 의미를 잘 생각하면 좋을 것 같다.



<img src="https://user-images.githubusercontent.com/86605720/152819692-27f9883a-160a-459e-aeb6-82d5875b1390.png" alt="image" style="zoom:50%;" />

* Nesterov Accelerated Gradient

 local minimum에 잘 수렴하지 못하는 momentum의 단점을 극복한다.

* Adagrad

 adaptive method : parameter가 지금까지 얼마나 변해왔는지 변해오지 않았는지를 고려한다. 많이 변한 parameter는 적게 변화시키고, 변하지 않은 parameter는 많이 변화시키고자 한다. G는 지금까지 gradient가 얼마나 변해왔냐는 정도를 나타낸다. 

 학습이 진행될수록 G가 커져서 학습이 잘 되지 않는다는 단점이 있다.

<img src="https://user-images.githubusercontent.com/86605720/152822142-67bbe344-6c2e-4496-9b3f-ce89dc3338f3.png" alt="image" style="zoom:50%;" />

* Adadelta

 Adagrad의 G가 무한히 커지는 단점을 해결하기 위해 사용한다. learning rate가 없다.

* RMSprop
* Adam ( Adaptive Moment Estimation)

 이전의 gradient를 사용하는 momentum의 성질과 gradient square에 따라 adaptive하게 learning rate을 바꾸는 성질을 모두 사용한다. 가장 일반적으로 사용되는 optimizer이다. 

<img src="https://user-images.githubusercontent.com/86605720/152822912-0c3fcb77-004a-4215-825b-761607feaa38.png" alt="image" style="zoom:50%;" />

<br>

## regularization

* generalization을 위해 사용한다.
* 학습을 방해하는 것이 목적으로 학습 데이터에만 잘 동작하는 overfitting 방지
* early stopping, parameter norm penalty, data augmentation, batch normalization 등 다양한 방법이 있다.



<br>

## CNN 발전

* CNN 연산 방법
* FC layer에 비해 적은 parameter
* layer가 깊어지고 parameter 수는 적어지는 방향으로 발전했다.
* AlexNet 

 ILSVRC에서 AlexNet이 좋은 성적을 거둔 뒤로 이와 같은 딥러닝 기반 영상 인식이 이 대회에서 좋은 성적을 거두게 됐다.

* VGGNet 

 AlexNet과 다르게 3X3 크기의 filter만을 사용한다. 3X3의 convolution layer를 2번 사용하면 5X5의 convolution layer를 1번 사용하는 것과 같은 receptive field를 가지면서 더 적은 수의 parameter를 갖는다.

* GoogLeNEt

 1X1 convolution을 사용하는데, depth 방향으로 차원을 줄여준다. 3X3 convolution을 사용하기 전에 1X1 convolution layer를 넣어주면 30퍼센트 가량의 parameter 수를 줄일 수 있다.

* ResNet

 ResNet이 나오기 전까지 층을 너무 깊게 쌓으면 오히려 성능이 더 안 좋아진다는 인식이 있었다. skip connection을 통해서 network를 더 깊게 쌓을 수 있는 가능성을 제공했다.



<br>

## 피어세션

* 과제 코드 리뷰를 하고 모르는 내용을 나눴다.
* 면접 질문을 분담해서 발표했다.



​		