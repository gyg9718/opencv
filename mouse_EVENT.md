# 마우스 이벤트 처리하기



### MouseEVent 처리 함수의 event 인자



|MouseEventTypes 열거형 상수|값|설명|
|:-----------------------:|:-:|:--:|
|cv2.EVENT_MOUSEMOVE|0|마우스가창위에서 움직이는 경우|
|cv2.EVENT_LBUTTONDOWN|1|마우스 왼쪽 버튼이 눌려지는 경우|
|cv2.EVENT_RBUTTONDOWN|3|마우스 오른쪽 버튼이 눌려지는 경우|
|cv2.EVENT_MBUTTONDOWN|3|마우스 가운데 버튼이 눌려지는 경우|
|cv2.EVENT_LBUTTONUP|4|마우스 왼쪽 버튼이 떼어지는 경우|
|cv2.EVENT_RBUTTONUP|5|마우스 오른쪽 버튼이 뗴어지는 경우|
|cv2.EVENT_MBUTTONUP|6|마우스 가운데 버튼이 떼어지는 경우|
|cv2.EVENT_LBUTTONDBCLK|7|마우스 왼쪽 버튼을 더블클릭하는 경우|
|cv2.EVENT_RBUTTONDBCLK|8|마우스 오른쪽 버튼을 더블클릭하는 경우|
|cv2.EVENT_MBUTTONDBCLK|9|마우스 가운데 버튼을 더블클릭하는 경우|
|cv2.EVENT_MOUSEWHEEL|10|마우스 휠을 앞뒤로 돌리는 경우|
|cv2.EVENT_MOUSEHWHEEL|11|마우스 힐을 좌우로 움직이는 경우|



### 마우스 이벤트 처리함수의 flags 인자
|MouseEventTypes 열거형 상수|값|설명|
|:-----------------------:|:-:|:--:|
|cv2.EVENT_FLAG_LBUTTON|1|마우스 왼쪽 버튼이 눌려져 있음|
|cv2.EVENT_FLAG_RBUTTON|2|마우스 오른쪽 버튼이 눌려져 있음|
|cv2.EVENT_FLAG_MBUTTON|4|마우스 가운데 버튼이 눌려져있음|
|cv2.EVENT_FLAG_CTRLKEY|8|CTRL키가 눌려져있음|
|cv2.EVENT_FLAG_SHIFTKEY|16|SHIFT키가 눌려져있음|
|cv2.EVENT_FLAG_ALTKEY|32|ALT키가 눌려져있음|
