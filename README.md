# 이미지 노이즈 제거 클래스 분류기
오토인코더를 사용한 이미지 노이즈 제거 과정을 거친 CNN 이미지 분류기

# 팀원
성결대학교 정보통신공학과 23-1 머신러닝(월 4-6)

TEAM SELF-LEARNING

20190895 김찬영

20190954 허진환

20190948 지성원

20190919 우상욱

## Overview
- 라이브러리 불러오기 및 이미지 출력
- 이미지 정규화 및 가공, 이미지 노이즈 추가
- 오토인코더 모델 생성
- 오토인코더 모델 학습
- 오토인코더 모델 성능 파라미터 및 결과 출력

![intuition](/img/intro.png?raw=true "Title")

## 오토인코더 개론
![intuition](/img/autoencoderkor.png?raw=true "Title")

### 오토인코더
데이터 인코딩(representation learning) 작업을 수행하는 인공 신경망의 한 유형으로, 오토인코더의 특징으로는 입력 데이터를 입력 및 출력으로 사용한다.

![intuition](/img/AutoencoderDenoising.png?raw=true "Title")

### 코드레이어
오토인코더는 네트워크에 병목 현상을 만들어 줌으로서 동작한다.

이 병목 현상은 네트워크가 원래 입력의 압축된(encoded) 버전을 생성하도록 한다. 

오토인코더는 입력 데이터와 상관관계가 있는 경우에 잘 작동한다.(입력 데이터가 모두 독립적인 경우에는 잘 작동하지 않을 수 있음)

참고 문헌: “Intro to Autoencoders by Jeremy Jordan”

![Code layer](/img/AutoencoderDenoising2.png)

### 오토인코더 수학적 원리
Encoder: ``` h(x) = sigmoid (W * x + b) ```

Decoder: ``` x̂ = sigmoid (W* * h(x) + c) ```

![math](/img/AutoencoderDenoising3.png)

### 재구성 오차
오토인코더의 목표는 입력 X와 네트워크 출력 X^ 사이의 재구성 오차를 최소화하는 것이다. 

![reconstruction](/img/AutoencoderDenoising4.png)



오토인코더의 차원 축소(잠재 공간)는 선형 활성화 함수를 사용하는 경우 PCA(주성분 분석)와 매우 유사하다.

## Output

![output](/img/conclusion.png)

1열 : 노이즈 추가된 이미지

2열 : 오토인코더를 통해 노이즈 제거된 이미지