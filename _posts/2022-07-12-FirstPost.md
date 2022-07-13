---
title: 1st Post
author: HEY
date: 2022-07-12 11:33:00 +0800
categories: [Machine Learning]
tags: [Python]
math: true
mermaid: true
---


## Gradient Descent Algorithm (w/ Linear Regression)

간단한 수식과 실습을 통해 Gradient Descent Algorithm을 이해


### 1 . Intro

뭔진 모르겠는데 하여튼 데이터가 아래와 같이 있음.

복잡하니 그냥 간단하게 1개 input에 1개 output으로 생각. 아래와 같이 데이터 표현.

<div style="text-align: center">

$ (x_{1}, y_1) $
<br>
$ (x_{2}, y_2) $
<br>
...
<br>
$ (x_{n}, y_n) $
<br>
</div>

총 n개의 (x, y) 쌍 표현됨. 우리가 원하는 것은.

변수들간의 관계를 가장 잘 설명해주는 하나의 수식 (가정, hypothesis).

여기서는 간단하게 선형 linear로 가정.

<div style="text-align: center">

$ h(\theta, x) = \theta_1 x + \theta_0 $ 

</div>
<br>

parameter 혹은 coefficient라고도 부르는 $\theta_1$은 기울기 slope, $\theta_0$는 절편 bias.

(두개 변수들간의 관계를 가장 잘 설명하는 수식) = (수식으로 예측된 결과값이 데이터와 가장 일치)를 의미.

즉 예측값의 오차가 가장 작은 것으로 정의.

보통 Cost function 이라 부르는 혹은 평균제곱오차 Mean Squared Error(mse)를 최소화 하는 것을 목표로 함.

<div style="text-align: center">

$$ C(x;\theta_i) = \frac{1}{2 n} \sum_{i=1}^{n} (h(\theta_i, x_i) - y_i)^2 $$

$$         = \frac{1}{2 n} \sum_{i=1}^{n} ((\theta_1 x_i + \theta_0) - y_i)^2 $$

</div>

위의 cost function 을 최소화 하는 기울기 m, b를 구하는 게 목표임.

이제 문제는 어떻게 구하는가. 사람이면 미분할텐데 귀찮음. 그럼 컴퓨터한테 어떻게 구하라고 할까.

