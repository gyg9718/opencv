# opencv 패키지를 모두 다운받아 빌드하는 방식
```
패키지 업데이트
sudo apt-get update

패키지 업그레이드
sudo apt-get upgrade


sudo apt install cmake build-essential pkg-config git


아래부터 (opencv) 컴파일에 필요한 모든 패키지를 설치하는 단계
sudo apt install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev libdc1394-22-dev libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev

패키지 설치 . . .
sudo apt install libgtk-3-dev libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
sudo apt install libatlas-base-dev liblapacke-dev gfortran
sudo apt install libhdf5-dev libhdf5-103
sudo apt install python3-dev python3-pip python3-numpy

컴파일 준비작업 실행
sudo nano /etc/dphys-swapfile

```
