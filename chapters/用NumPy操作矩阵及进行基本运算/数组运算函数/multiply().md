# multiply()

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

print(np.multiply(2.0, 4.0))

x1 = np.arange(9.0).reshape((3, 3))
x2 = np.arange(3.0)
print(np.multiply(x1, x2))

x1 = np.arange(9.0).reshape((3, 3))
x2 = np.arange(3.0)
print(x1 * x2)
```

## 参考文献及资料

1. [numpy.multiply(x1, x2, /, out=None, *, where=True, casting='same_kind', order='K', dtype=None, subok=True[, signature, extobj]) = <ufunc 'multiply'>](https://numpy.org/doc/stable/reference/generated/numpy.multiply.html#numpy.multiply)


