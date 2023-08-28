# min()

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

a = np.arange(4).reshape((2,2))
print(a)

print(np.min(a))           # Minimum of the flattened array
print(np.min(a, axis=0))   # Minima along the first axis
print(np.min(a, axis=1))   # Minima along the second axis

b = np.arange(5, dtype=float)
b[2] = np.NaN
print(np.min(b))
print(np.nanmin(b))

print(np.min([[-50], [10]], axis=-1, initial=0))
print(np.min([6], initial=5))
print(min([6], default=5))
```

## 参考文献及资料

1. [numpy.min(a, axis=None, out=None, keepdims=<no value>, initial=<no value>, where=<no value>)](https://numpy.org/doc/stable/reference/generated/numpy.min.html#numpy.min)


