# arange()

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

print(np.arange(0, 5, 0.5, dtype=int))
print(np.arange(-3, 3, 0.5, dtype=int))

power = 40
modulo = 10000
x1 = [(n ** power) % modulo for n in range(8)]
x2 = [(n ** power) % modulo for n in np.arange(8)]
print(x1)
print(x2)

print(np.arange(3))
print(np.arange(3.0))
print(np.arange(3,7))
print(np.arange(3,7,2))
```

## 参考文献及资料

1. [numpy.arange([start, ]stop, [step, ]dtype=None, *, like=None)](https://numpy.org/doc/stable/reference/generated/numpy.arange.html#numpy.arange)


