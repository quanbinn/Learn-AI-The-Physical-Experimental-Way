# 在线体验1张图片的RGB颜色空间

## 打开实验文件

- 下载右方的[Computer Vision Nanodegree Program, Exercises代码仓库](https://github.com/udacity/CVND_Exercises)。
- 单机右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 单击File的第2个下拉菜单“Open...” ,浏览器会打开一个新的页面。单击右上方的"Upload", 会弹出对话框，选中CVND_Exercises-master\1_1_Image_Representation中的2. Visualizing RGB Channels.ipynb，和images文件夹中的waymo_car.jpg。
- 然后单击2. Visualizing RGB Channels.ipynb这个文件，会出现下面的代码段，然后单击上方的按键“运行”。

```python
import matplotlib.pyplot as plt
import matplotlib.image as mpimg

%matplotlib inline

# Read in the image
image = mpimg.imread('waymo_car.jpg')

plt.imshow(image)

# Isolate RGB channels
r = image[:,:,0]
g = image[:,:,1]
b = image[:,:,2]

# Visualize the individual color channels
f, (ax1, ax2, ax3) = plt.subplots(1, 3, figsize=(20,10))
ax1.set_title('R channel')
ax1.imshow(r, cmap='gray')
ax2.set_title('G channel')
ax2.imshow(g, cmap='gray')
ax3.set_title('B channel')
ax3.imshow(b, cmap='gray')
```

## 参考文献及资料

1. [Become a Computer Vision Expert](https://www.udacity.com/course/computer-vision-nanodegree--nd891)

