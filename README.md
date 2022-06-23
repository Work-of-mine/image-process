# image-process
http://127.0.0.1:8889/?token=bdb3f00276480d39583fcc6a387dd6108d48ff8fc9bbc0de<br>
file:///C:/Users/Central%20Computer%20Lab/AppData/Roaming/jupyter/runtime/nbserver-8732-open.html<br>
http://localhost:8889/?token=bdb3f00276480d39583fcc6a387dd6108d48ff8fc9bbc0de<br>
http://localhost:8888/notebooks/image%20processing%20jayaram/Untitled.ipynb<br>

token/password bdb3f00276480d39583fcc6a387dd6108d48ff8fc9bbc0de<br>
pip install opencv_python<br>
pip install matplotlib<br>

PROGRAM 1<br>
import cv2<br>
img=cv2.imread('butterflypic.jpg',0)<br>
cv2.imshow('image',img)<br>
cv2.waitKey(0)<br>
cv2.destroyAllWindows()<br>

PROGRAM 2<br>
import matplotlib.image as mping<br>
import matplotlib.pyplot as plt<br>
img=mping.imread('butterflypic.jpg')<br>
plt.imshow(img)<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145365/173806136-56fc3fac-33a2-49f4-8ec1-c53624b88ff7.png)<br><br>

PROGRAm 3<br>
from PIL import Image<br>
img=Image.open("butterflypic.jpg")<br>
img=img.rotate(180)<br>
img.show()<br>
cv2.waitKey(0)<br>
cv2.destroyAllWindows()<br>

PROGRAm 4<br>
from PIL import ImageColor<br>
img1=ImageColor.getrgb("red")<br>
print(img1)<br>
OUTPUT:<br>
(255, 0, 0)<br>

PROGRAM 5<br>
from PIL import ImageColor<br>
img=Image.new('RGB',(200,400),(255,255,0))<br>
img.show()<br>


PROGRAM 6<br>
import cv2<br>
import matplotlib.pyplot as plt<br>
import numpy as np<br>
img=cv2.imread('butterflypic.jpg')<br>
plt.imshow(img)<br>
plt.show()<br>
img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)<br>
plt.imshow(img)
plt.show()<br>
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)<br>
plt.imshow(img)<br>
plt.show()<br>


OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145365/173813837-cd414d2d-dc09-4985-b41b-10c5607db435.png)
![image](https://user-images.githubusercontent.com/98145365/173813887-14844208-6714-4025-9963-234528b779de.png)
![image](https://user-images.githubusercontent.com/98145365/173813939-4d41a836-bd42-4044-92b7-e18e96b273fa.png)

PROGRAM 7<br>
from PIL import Image<br>
image=Image.open('butterflypic.jpg')<br>
print("Filename:",image.filename)<br>
print("Format:",image.format)<br>
print("Mode:",image.mode)<br>
print("Size:",image.size)<br>
print("Width:",image.width)<br>
print("Height:",image.height)<br>
image.close()<br>

OUTPUT:<br>
Filename: butterflypic.jpg<br>
Format: JPEG<br>
Mode: RGB<br>
Size: (1024, 535)<br>
Width: 1024<br>
Height: 535<br>

program8<br>
import cv2 <br>
img=cv2.imread('butterflypic.jpg')<br>
print('originally image length width',img.shape) <br>
cv2.imshow('original image',img) <br>
cv2.waitKey(0) <br>
imgresize=cv2.resize(img,(150,160))<br>
cv2.imshow('Resized image',imgresize)<br>
print('Resized image length width',imgresize.shape) <br>
cv2.waitKey(0)<br>

output<br>
originally image length width (535, 1024, 3)<br>
Resized image length width (160, 150, 3)<br>

Program9:<br>
import cv2 <br>
img=cv2.imread('butterflypic.jpg') <br>
cv2.imshow("RGB",img) <br>
cv2.waitKey(0) <br>
img=cv2.imread('butterflypic.jpg',0) <br>
cv2.imshow("Gray",img) <br>
cv2.waitKey(0) <br>
ret, bw_img=cv2.threshold(img,127,100,cv2.THRESH_BINARY) <br>
cv2.imshow("Binary",bw_img) <br>
cv2.waitKey(0) <br>
cv2.destroyAllWindows()<br>

PROGRAM 11:<br>
import cv2<br>
import matplotlib.image as mping<br>
import matplotlib.pyplot as plt <br>
img=mping.imread('hgfc.jpg') <br>
plt.imshow(img)<br>
plt.show()<br>
![image](https://user-images.githubusercontent.com/98145365/175017356-395ef46b-757c-4eb1-bb6a-12c7d63b22f1.png)<br>
hsv_img= cv2.cvtColor(img, cv2.COLOR_RGB2HSV)<br>
light_blue=(1,190,200) <br>
dark_blue=(18,255,255)<br>
mask=cv2.inRange(hsv_img, light_blue, dark_blue)<br>
result=cv2.bitwise_and(img,img, mask=mask)<br>
plt.subplot (1,2,1)<br>
plt.imshow(mask, cmap="gray")<br>
plt.subplot(1,2,2)<br>
plt.imshow(result)<br>
plt.show()<br>
![image](https://user-images.githubusercontent.com/98145365/175017728-47a3218e-5e7c-427b-9fdb-aa0422000a67.png)<br>
![image](https://user-images.githubusercontent.com/98145365/175017848-2c760595-0eb8-4009-b9d9-2dd5a8bbf0e4.png)<br>
<br>
light_white= (0, 0, 200)<br>
dark_white = (145, 60, 255)<br>
mask_white = cv2.inRange (hsv_img, light_white, dark_white)<br>
result_white = cv2.bitwise_and (img, img, mask=mask_white)<br>
plt.subplot(1, 2, 1)<br>
plt.imshow(mask_white, cmap="gray")<br>
plt.subplot(1, 2, 2)<br>
plt.imshow(result_white)<br>
plt.show()<br>
![image](https://user-images.githubusercontent.com/98145365/175017961-bd603fa8-50db-4edd-a519-01851eb4f8a8.png)<br>

![image](https://user-images.githubusercontent.com/98145365/175017979-af84f66d-75e3-4bba-b334-71683c410c01.png)<br>

final_mask= mask + mask_white<br>
final_result=cv2.bitwise_and(img,img,mask=final_mask)<br>
plt.subplot(1, 2, 1)<br>
plt.imshow(final_mask, cmap="gray")<br>
plt.subplot(1, 2, 2)<br>
plt.imshow(final_result)<br>
plt.show()<br>

![image](https://user-images.githubusercontent.com/98145365/175018052-ac837edb-6656-44f8-9f57-3a27aa458dfb.png)<br>

![image](https://user-images.githubusercontent.com/98145365/175018080-0923dcec-2a88-4a3f-aada-f04c0c09cdc1.png)<br>

blur= cv2.GaussianBlur (final_result, (7, 7), 0) <br>
plt.imshow(blur) <br>
plt.show()<br>
![image](https://user-images.githubusercontent.com/98145365/175018117-85841ae3-fdde-4e6e-80c8-0252100112f0.png)<br>

PROGRAM 12
import cv2
import matplotlib.image as mping
import matplotlib.pyplot as plt
img1=cv2.imread('img1.jpg')
img2=cv2.imread('img2.jpg')
fimg1=img1+img2 
plt.imshow(fimg1)
plt.show()
fimg2=img1-img2
plt.imshow(fimg2)
plt.show()
cv2.imwrite('output.jpg', fimg2)
fimg3=img1*img2 
plt.imshow(fimg3)
plt.show()
cv2.imwrite('output.jpg', fimg3)
fimg4=img1/img2 
plt.imshow(fimg4)
plt.show()
cv2.imwrite('output.jpg', fimg4)
![image](https://user-images.githubusercontent.com/98145365/175023051-c4f5b5b7-2024-4987-aa4a-48a7b1c5804d.png)
![image](https://user-images.githubusercontent.com/98145365/175023200-e3b8c7f8-8669-47c7-a424-1ed8bf0e1f2b.png)
![image](https://user-images.githubusercontent.com/98145365/175023227-4a060f09-216c-4c0e-9247-7d242a5945ab.png)
![image](https://user-images.githubusercontent.com/98145365/175023292-a645d1a3-63d9-474e-97ed-c84389832059.png)

PROGRAM 23/6/22<br>
import cv2 <br>
img = cv2.imread("D:\img1.jpg")<br>
gray=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY) <br>
hsv=cv2.cvtColor(img,cv2.COLOR_BGR2HSV)<br>
lab=cv2.cvtColor(img,cv2.COLOR_BGR2LAB) <br>
hls=cv2.cvtColor(img,cv2.COLOR_BGR2HLS)<br>
yuv=cv2.cvtColor(img,cv2.COLOR_BGR2YUV) <br>
cv2.imshow("GRAY image", gray)<br>
cv2.imshow("HSV image",hsv)<br>
cv2.imshow("LAB image",lab)<br>
cv2.imshow("HLS image", hls)<br>
cv2.imshow("YUV image",yuv)<br>
cv2.waitKey(0)<br>
cv2.destroyAllWindows()<br>
![image](https://user-images.githubusercontent.com/98145365/175261328-88985f9c-08eb-43fb-be1f-eb72c0c39bf5.png)

![image](https://user-images.githubusercontent.com/98145365/175260889-abf9c5da-48c9-40a6-81d4-2eb8f6ca0b6a.png)







