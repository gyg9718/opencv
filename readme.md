# cv2

### cv2.imread('img')
 - img : 이미지 파일이름
 - 이미지를 가져옴(컬러)
### cv2.imread('img', cv2.IMREAD_GRAYSCALE)
 - 위 코드(cv2.imread('img')와 다르게 디폴트가 아닌 흑백으로 가져옴.
 - img : 이미지 파일이름
### cv2.cvtColor(imgBGR, cv2.COLOR_BGR2RGB) 
 - BGR 순으로 읽는것을 RGB순으로 읽게함.

### cv2.nameWindow('window')
 - 괄호안에 있는 이름의 창을 만듬
 - window : 창 이름
### cv2.imshow('window', 이미지) 
 - 따음표 안에 있는 이름의 창에 이미지를 넣음.
 - window : 창 이름
### cv2.waitKey() 
 - 키가 눌릴때까지 기다림.(이게 없으면 창이 바로 닫힘)


## OpenCV 그리기 함수
 - 영상에 선, 도형, 문자열을 출력하는 그리기 함수를 제공
 - 선그리기 : 직선, 화살표, 마커 등
 - 도형 그리기 : 사각형, 원, 타원, 다각형 등 
 - 문자열 출력
## 주의점 
 - 그리기 알고리즘을 이용하여 영상의 픽셀 값 자체를 변경
  -> 원본영상이 필요하면 복사본을 만들어서 그리기 & 출력
 - 그레이 스케일 영상에는 컬러로 그리기 안 됨
  -> cv2.cvtColor()함수로 BGR컬러 영상으로 변환한 후 그리기 함수 호출  
### 직선 그리기
### cv2.line(img, pt1, pt2, color, thickness=None, lineType=None, shift=None) -> img
 - img : 그림을 그릴 영상
 - pt1, pt2 : 직선의 시작점과 끝점. (x, y)튜플.
 - color : 선 색상 또는 밝기. (B, G, R)튜플 또는 정수값.
 - thickness : 선 두께. 기본값은 1.
 - lineType : 선 타입.cv2.LINE_4,cv2>LINE_8,LINE_AA중 선택. 기본값은 cv2.LINE_8
 - shift : 그리기 좌표값의 축소 비율. 기본값은 0.
### 사각형 그리기
### cv2.rectangle(img, pt1, pt2, color, thickness=None, lineTpe=None, shift=None) -> img
### cv2.rectangle(img, rec, color, thickness=None, lineType=None, shift=None) -> img
 - img : 그림을 그릴 영상
 - pt1, pt2 : 사각형의 두 꼭지점 좌표.(x, y)튜플.
 - rec : 사각형 위치 정보. (x, y, w, h)튜플.
 - color : 선 색상 또는 밝기.(B, G, R)튜플 또는 정수값.
 - thickness : 선 두께. 기본값은 1.음수(-1)를 지정하면 내부를 채움.
 - lineType : 선타입.cv2.LINE_4, cv2.LINE_8, cv2.LINE_AA 중 선택. 기본값은 cv2.LINE_8
 - shift : 그리기 좌표 값의 축소 비율. 기본값은 0.

### 원그리기
### cv2.circle(img, center, radius, color, thickness=None, lineTpe=None, shift=None) -> img 
 - img : 그림을 그릴 영상
 - center : 원의 중심 좌표.(x, y)튜플
 - radius : 원의 반지름
 - color : 선 색상 또는 밝기.(B, G, R)튜플 또는 정수값.
 - thickness : 선 두께. 기본값은 1.음수(-1)를 지정하면 내부를 채움.
 - lineType : 선타입.cv2.LINE_4, cv2.LINE_8, cv2.LINE_AA 중 선택. 기본값은 cv2.LINE_8
 - shift : 그리기 좌표 값의 축소 비율. 기본값은 0.
### 다각형 그리기
### cv2.polylines(img, pts, isClosed, color, thickness=None, lineTpe=None, shift=None) -> img
 - img : 그림을 그릴 영상
 - pts : 다각형 외각 점들의 좌표 배열.numpy.ndarray의 리스트.
 - isClosed : 폐곡선 여부. True 또는 False 지정.
 - color : 선 색상 또는 밝기.(B, G, R)튜플 또는 정수값.
 - thickness : 선 두께. 기본값은 1.음수(-1)를 지정하면 내부를 채움.
 - lineType : 선타입.cv2.LINE_4, cv2.LINE_8, cv2.LINE_AA 중 선택. 기본값은 cv2.LINE_8
 - shift : 그리기 좌표 값의 축소 비율. 기본값은 0.
 
### 문자열 출력
### cv2.putText(img, text, org, fonFace, fonScale, color, thickeness=None, lineType=None, bottomLeftOrigin=None) -> img
 - img : 그림을 그릴 영상 
 - text : 출력할 문자열
 - org : 영상에서 문자열을 출력할 위치의 좌측 하단 좌표.(x, y)튜플
 - fontFace : 폰트 종류. cv.FONT_HERSHEY_로 시작하는 상수 중 선택
 - fontScale : 폰트 크기 확대/축소 비율
 - color : 선 색상 또는 밝기. (B, G, R)튜플 또는 정수값.
 - thickness:선 두께. 기본값은 1.음수(-1)를 지정하면 내부를 채움.
 - lineType : 선 타입. cv2_LINE_4, cv2_LINE_8, cv2_LINE_AA 중 선택.
 - bottonLeftOrigin : True이면 영상의 좌측 하단을 워넞믕로 간주. 기본값은 false.
 
 ## 카메라 동영상 처리하기
 
 ### 카메라 열기
 ### cv2.VideoCapture(index, apiPreference=None) -> retval
  - index : camera_id + domain_offset_id
  - apiPreference : 선호하는 카메라 처리 방법을 지정
  - retval : cv2.VideoCapture 객체

 ### cv2.VideoCapture.open(index, apiPreference=None) -> retval
  - retval : 성공하면 true, 실패하면 false

### 동영상, 정지 영상 시퀀스, 비디오 스트림 열기
### cv2.VideoCapture(filename, apiPreference=None) -> retval
 - filename : 비디오 파일 이름, 정지 영상 시퀀스, 비디오 스트림 URL등(e.g)'video.avi', 'img_%02d.jpg', 'protocol://host:port/scrip?params|auth'
 - apiPreference : 선호하는 동영상 처리 방법을 지정
 - retval : cv2.VideoCapture 객체
### cv2.VideoCapture(filename, apiPreference=None) -> retval
  - retval : 성공하면 true, 실패하면 false

### 비디오 캡쳐가 준비되었는지 확인
### cv2.VideoCapture.isOpened() -> retval
  - retval : 성공하면 true, 실패하면 false
### 프레임 받아오기
### cv2.VideoCapture.read(image=None) -> retval, image
   - retval : 성공하면 true, 실패하면 false
   - image : 현재 프레임(numpy.ndarray)
### 카메라, 비디오 장치 속성 값 참조
### cv2.VideoCapture.get(propid) -> retval
 - propid : 속성상수.(OpenCV문서 참조)
 
 |--------------------|---------------|
 |CAP_PROP_FRAME_WIDTH|프레임 가로 크기|
 |CAP_PROP_FRAME_HEIGHT|프레임 세로 크기|
 |CAP_PROP_FPS|초당 프레임 수|
 |CAP_PROP_FRAME_COUNT|비디오 파일의 총 프레임 수|
 |CAP_PROP_POS_MSEC|밀리초 단위로 현재 위치|
 |CAP_PRO_POS_FRAMES|현재 프레임 번호|
 |CAP_PROP_EXPOSURE|노출|
# matplotlib
(import matplot.pyplot as plt)

### plt.subplot(121), plt.axis('off'), plt.imshow(이미지) 
 - subplot 뒤 괄호안 순서대로 행, 열, (위치) plt.axis 는 창 안에 눈금표시 on/off(default : on).
### plt.subplot(122), plt.axis('off'), plt.imshow(이미지, camp='gray')
 - 위plt.subplot(121), plt.axis('off'), plt.imshow(이미지)와 똑같고, 흑백으로 가져옴
### plt.show()
 - 창을 띄움.
