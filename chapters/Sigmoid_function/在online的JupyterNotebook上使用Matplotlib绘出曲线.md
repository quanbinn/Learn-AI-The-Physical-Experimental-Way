# 在online的JupyterNotebook上使用Matplotlib绘出Sigmoid function的曲线

## 打开实验文件

- 单机右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单机上方的按键“运行”，然后会显示出相应的图形。

```python
import matplotlib.pyplot as plt
import numpy as np
import math
def sigmoid(x):
    a = []
    for item in x:
        a.append(1/(1+math.exp(-item)))
    return a
x = np.arange(-10., 10., 0.2)
sig = sigmoid(x)
plt.plot(x,sig)
plt.show()
```

## 参考文献及资料

1. [NumPy：Quickstart tutorial (Universal Functions)](https://numpy.org/devdocs/user/quickstart.html#universal-functionsl)
2. [matplotlib：tutorials](https://matplotlib.org/tutorials/index.html)


