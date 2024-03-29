# dot()

## 本质意义： 。

### 在线调试环境1

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”。

### 在线调试环境2

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

```python
import numpy as np

A = np.array( [[1,0,2],[2,-1,3],[4,-2,-3]] )
B = np.array( [-4,5,6])

print(A.dot(B))

A1 = np.array([[4,2],[3,-2],[0,-1]])
B1 = np.array([[2,1,3],[-1,5,8]])

print(A1.dot(B1))
```

## 参考文献及资料

1. [numpy.dot(a, b, out=None)](https://numpy.org/doc/stable/reference/generated/numpy.dot.html#numpy.dot)
2. [用长方体的木头块体验矩阵乘法](https://github.com/quanbinn/Learn-Mathematical-Olympiad-The-Interactive-Way/blob/master/chapters/%E7%BA%BF%E6%80%A7%E4%BB%A3%E6%95%B0/%E7%94%A8%E9%95%BF%E6%96%B9%E4%BD%93%E7%9A%84%E6%9C%A8%E5%A4%B4%E5%9D%97%E4%BD%93%E9%AA%8C%E7%9F%A9%E9%98%B5%E4%B9%98%E6%B3%95.md)



