# 在online的JupyterNotebook上使用Matplotlib绘出Step function

## 打开实验文件

### 在线调试环境1

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”。

### 在线调试环境2

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

```python
import numpy as np
import matplotlib.pyplot as plt
  
def step_function(x):
    # 阶跃函数
    return np.array(x > 0, dtype=np.int)  # 先计算bool值，再转成int
  
def show(x, y, ylim):
    # 画图
    plt.plot(x, y)
    plt.ylim(ylim)  # y轴范围
    plt.show()  # plot在内存画，show一次性将内存的显示出来
 
def show_step(x):
    # 展示阶跃函数图像
    y = step_function(x)
    ylim = (-0.1, 1.1)
    show(x, y, ylim)
  
x = np.arange(-5.0, 5.0, 0.1)  # x范围
 
show_step(x)
```

## 参考文献及资料

1. [Step function](https://en.wikipedia.org/wiki/Step_function)
2. [matplotlib：tutorials](https://matplotlib.org/tutorials/index.html)


