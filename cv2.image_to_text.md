## 필수 패키지
pip install opencv-python
pip install pytesseract
## 이미지에서 글자 인식하기(OCR)
```python
improt cv2
import pytesseract

#이미지 파일로드
image = cv2.imread('image.jpg')

#이미지 전처리를 위해 흑백으로 변환
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

#이미지에서 텍스트 추출
text = pytesserct.image_to_string(gray, lang='eng')

print(text)
```
