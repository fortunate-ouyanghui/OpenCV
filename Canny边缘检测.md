- Canny()函数
```C
import cv2
import numpy as np
import matplotlib.pyplot as plt

"""
Canny边缘检测流程:
1.使用 高斯滤波器 平滑图像
2.计算图像 梯度的大小和方向
3.非极大值抑制 ,消除边缘检测带来的杂散响应
4.双阈值检测 ,确定强边缘和弱边缘
5.边缘跟踪,连接边缘
"""

img = cv2.imread('./imgs/canny.png',cv2.IMREAD_GRAYSCALE)

"""
cv2.Canny(image, threshold1, threshold2)
image: 输入图像
threshold1: 下阈值
threshold2: 上阈值
若梯度值大于上阈值,则被认为是边缘
若梯度值小于下阈值,则被认为不是边缘
若梯度值在上阈值和下阈值之间,且其连接的像素点为边缘,则被认为是边缘，否则认为不是边缘
"""
canny_img=cv2.Canny(img,50,100)
res=np.hstack((img,canny_img))
cv2.namedWindow("res",cv2.WINDOW_NORMAL)
cv2.resizeWindow("res",800,600)
cv2.imshow("res",res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
- 结果
