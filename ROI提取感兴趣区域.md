 - 方法一：截取部分图像
```C
img=cv2.imread("/home/oyh/test/EDC/imgs/car.png",cv2.IMREAD_COLOR)
#显示函数
def img_show(window,img):
    cv2.namedWindow(window,cv2.WINDOW_NORMAL)
    cv2.resizeWindow(window,800,600)
    cv2.imshow(window,img)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
img1=img[904:1100,477:800]#h w->y x
img_show("img1",img1)
```
- 方法二：颜色通道提取
```C
#分离
b,g,r=cv2.split(img)
#合并
img2=cv2.merge((b,g,r))

#只保留R通道   B G R->0 1 2
img3=img.copy()
img3[:,:,0]=0
img3[:,:,1]=0
img_show("img3",img3)
```
