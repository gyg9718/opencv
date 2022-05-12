# opencv 다운로드


## opencv 패키지를 모두 다운받아 빌드하는 방식
```
패키지 업데이트
sudo apt-get update

패키지 업그레이드
sudo apt-get upgrade
```
```
sudo apt install cmake build-essential pkg-config git
```
```
아래부터 (opencv) 컴파일에 필요한 모든 패키지를 설치하는 단계
sudo apt install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev libdc1394-22-dev libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev
```
```
패키지 설치 . . .
sudo apt install libgtk-3-dev libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
sudo apt install libatlas-base-dev liblapacke-dev gfortran
sudo apt install libhdf5-dev libhdf5-103
sudo apt install python3-dev python3-pip python3-numpy
```

```
컴파일 준비작업 실행
sudo nano /etc/dphys-swapfile 아래 이미지처럼 하얀색글씨중 100 -> 2048로 바꾸기
```
![image](https://user-images.githubusercontent.com/92916839/168038883-c0b87fd4-de3c-4128-b4ba-9e14c68607bb.png)
```
변경사항 저장 및 적용 목적으로 파일 재시작
sudo systemctl restart dphys-swapfile
```
```
2파일 클론
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git 
```

```
파일 컴파일 단계, 파일 저장할 폴더 만든뒤 작업디렉토리 이동
mkdir ~/opencv/build
cd ~/opencv/build
```

```
파일 컴파일 . . .
cmake -D CMAKE_BUILD_TYPE=RELEASE\

-D CMAKE_INSTALL_PREFIX=/usr/local\

-D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules\

-D ENABLE_NEON=ON\

-D ENABLE_VFPV3=ON\

-D BUILD_TESTS=OFF\

-D INSTALL_PYTHON_EXAMPLES=OFF\

-D OPENCV_ENABLE_NONFREE=ON\

-D CMAKE_SHARED_LINKER_FLAGS=-latomic\

-D BUILD_EXAMPLES=OFF ..

```

```
make -j$(nproc) 

sudo make install

sudo ldconfig
```
```
다시 swapsize를 2048 -> 100으로 바꾼 뒤 파일 재실행
sudo nano /etc/dphys-swapfile
sudo systemctl restart dphys-swapfile
```
### 설치 완료 확인 목적으로 현재 작업 디렉토리를 유지한채 python3명령한뒤 입력
  * import cv2
  * cv2.__version__
## 실행 끝. 
