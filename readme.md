# 정밀도
 #### 정밀도란 이미지가 얼마나 많은 색상을 표현할 수 있느냐를 의미한다. 
 ##### 정밀도는 색상을 표현하는 방법 중 하나이다. 정밀도가 높을수록 많은 색상을 표현할 수 있어 데이터의 폭이 넓어지고 더 자연스러운 이미지로 표시된다. 반대로 정밀도가 낮을수록 육안으로 확인하기 힘들 정도로 이미지의 변형이 가해지며 데이터의 개수가 줄어든다. 일반적으로 정밀도가 높을수록 데이터의 양이 많아져 정밀한 처리를 할 수 있다. 정밀도가 높을수록 데이터의 처리 결과는 더 정밀하다.

## 비트표현
 ```
 비트는 색상의 표현 개수를 설정한다. 색상을 표현하는 방식은 n-bit로 표현하며 n은 비트의 수를 의미한다. 이때 n의 이미는 2^n이므로 1-bit는 2의 값을 갖게된다. 
 1-bit의 경우 0과 1의 값만 갖게 되는데 중요한점은 두가지 색상이 아닌 두가지 숫자로 색상을 표현한다는 점이다. 
 가령 8-bit의 경우 2^8이 되어 256가지 값을 갖게 된다. 
 (색상을 표현할 때 적어도 8비트여야 유의미한 데이터를 얻게되어 색상을 표현할 수 있다 
 즉, 8비트 정밀도를 사용할 때 흑백 색상을 원활하게 표현할 수 있다.)
 ```
 - 1비트 이미지 - 이진화(binary)이미지 
 - 4비트 이미지 - 저화질 이미지
 - 8비트 이미지 - 고화질 이미지

## Opencv 정밀도 표현법
#### Opencv에서는 8비트 정밀도 이미지를 표현할 때 UB의 정밀도 값을 가장 많이 활용한다. 여기서 UB는 unsinged 8-bit integers를 의미한다.
 -  unsiged - 부호없음, integers - 정수형 -> unsinged 8-bit integers - 부호가 없는 8비트 정수형 (대부분의 정밀도 표현은 0~255의 값으로 색상을 표현한다.)
#### Python Oencv의 정밀도 표현법
```
color = np.zeros((height, width, 3), np.unit8)
gray = np.zeros((rows, cols, 1), np.unit8)
```
#### 아래의 표는 Python Opencv의 정밀도 표이다.
|OpenCV 형식|데이터 형식|의미|
|------|---|---|
|np.unit8|byte|8-bit unsinged integers|
|np.int8|sbyte|8-bit singed integers|
|np.unit16|unit16|16-bit unsinged integers|
|np.int16|int16|16-bit singed integers|
|np.float32|float|32-bit floating point number|
|np.double|double|64-bit floating point number|

# 채널
 - 채널은 그래픽스 이미지의 색상 정보를 담고 있다. 채널은 일반적으로 Red, Green, Blue와 추가로 Alpha로 구성된다. 이밖에도 Hue, Saturation, Value 등의 채널도 있다.
 색상을 표시할때는 주로 3~4개의채널을 사용하고 흑백 이미지를 표현할 때는 1채널을 사용한다(밝기만 조절하면 되어서).
 
 ### 색상표현
  ##### 색상 이미지에서 RGB값만 추출한다고 해서 추출된 이미지가 빨간색으로 표현디ㅗ지는 않는다. 그 이유는 분리된 이미지를 한가지 채널로만 색상을 표현해야 하기 떄문이다.
  ##### 각성분만 따로 분리해서 출력하면 흑백사진으로 나온다. 
  
 ### OpenCV 채널표현법
 #### Python OpenCV에서의 채널 표현
 ```
 color = np.zeros((height, width, 3), np.unit8)
 gray = np.zeros((rows, cols, 1), np.unit8)
 ```
