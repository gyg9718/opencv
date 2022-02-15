# cv2

### cv2.imread('이미지 파일이름')
 - 이미지를 가져옴(컬러)
### cv2.imread('이미지 파일이름', cv2.IMREAD_GRAYSCALE)
 - 위 코드(cv2.imread('이미지 파일이름')와 다르게 디폴트가 아닌 흑백으로 가져옴.
### cv2.cvtColor(imgBGR, cv2.COLOR_BGR2RGB) 
 - BGR 순으로 읽는것을 RGB순으로 읽게함.

### cv2.nameWindow('창 이름')
 - 괄호안에 있는 이름의 창을 만듬
### cv2.imshow('창 이름', 이미지) 
 - 따음표 안에 있는 이름의 창에 이미지를 넣음.
### cv2.waitKey() 
 - 키가 눌릴때까지 기다림.(이게 없으면 창이 바로 닫힘)



# matplotlib
(import matplot.pyplot as plt)

### plt.subplot(121), plt.axis('off'), plt.imshow(이미지) 
 - subplot 뒤 괄호안 순서대로 행, 열, (위치) plt.axis 는 창 안에 눈금표시 on/off(default : on).
### plt.subplot(122), plt.axis('off'), plt.imshow(이미지, camp='gray')
 - 위plt.subplot(121), plt.axis('off'), plt.imshow(이미지)와 똑같고, 흑백으로 가져옴
### plt.show()
 - 창을 띄움.
