# power()

## 本质意义： power()从数学本质意义上来说，是对一个数值进行指数的运算，得出相应的数值。 在这里指的是对多个不同数值进行多个不同指数的运算，得出一组数值。

> 注明:
>  
- ndarray的英文意思是：N-dimensional array, 缩写为**n**-**d**-array。

### 在线调试环境1

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”。

### 在线调试环境2

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

```python
import numpy as np

x1 = np.arange(6)
print(x1)
print(np.power(x1, 3))

x2 = [1.0, 2.0, 3.0, 3.0, 2.0, 1.0]
print(np.power(x1, x2))

x3 = np.array([[1, 2, 3, 3, 2, 1], [1, 2, 3, 3, 2, 1]])
print(x3)
print(np.power(x1,x3))
```

```python
import numpy as np

x1 = np.arange(6)
print(x1)
x2 = np.array([1, 2, 3, 3, 2, 1])
print(x1 ** x2)
```

## 参考文献及资料

1. [numpy.power(x1, x2, /, out=None, *, where=True, casting='same_kind', order='K', dtype=None, subok=True[, signature, extobj]) = <ufunc 'power'>](https://numpy.org/doc/stable/reference/generated/numpy.power.html#numpy.power)


