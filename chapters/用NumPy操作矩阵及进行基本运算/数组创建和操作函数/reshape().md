# reshape()

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

a = np.arange(6).reshape((3, 2))
print(a)

print(np.reshape(a, (2, 3))) # C-like index ordering	
print(np.reshape(np.ravel(a), (2, 3))) # equivalent to C ravel then C reshape
print(np.reshape(a, (2, 3), order='F')) # Fortran-like index ordering
print(np.reshape(np.ravel(a, order='F'), (2, 3), order='F'))

a = np.array([[1,2,3], [4,5,6]])
print(np.reshape(a, 6))
print(np.reshape(a, (3,-1))) # the unspecified value is inferred to be 2
```

## 参考文献及资料

1. [numpy.reshape(a, newshape, order='C')](https://numpy.org/doc/stable/reference/generated/numpy.reshape.html#numpy.reshape)


