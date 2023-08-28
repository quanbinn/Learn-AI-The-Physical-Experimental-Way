# arrayName[:col_num]

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

x = np.arange(10, 1, -1)
print(x)

print(x[np.array([3, 3, 1, 8])])
print(x[np.array([3, 3, -3, 8])])

x = np.array([[1, 2], [3, 4], [5, 6]])
print(x[np.array([1, -1])])
print(x[np.array([3, 4])])

y = np.arange(35).reshape(5, 7)
print(y)
print(y[np.array([0, 2, 4]), np.array([0, 1, 2])])

print(y[np.array([0, 2, 4]), np.array([0, 1])])
print(y[np.array([0, 2, 4]), 1])
print(y[np.array([0, 2, 4])])
```

## 参考文献及资料

1. [Slicing and striding](https://numpy.org/doc/stable/user/basics.indexing.html#slicing-and-striding) | [基本切片和索引](https://www.numpy.org.cn/reference/arrays/indexing.html#基本切片和索引)


