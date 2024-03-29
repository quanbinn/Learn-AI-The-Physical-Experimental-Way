# arrayName[start:end]

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

x = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
print(x[1:7:2])

print(x[-2:10])
print(x[-3:3:-1])
print(x[5:])

x = np.array([[[1],[2],[3]], [[4],[5],[6]]])
x.shape
print(x[1:2])
```

```python
import numpy as np

x = np.arange(10)
print(x[:-7])
```

## 参考文献及资料

1. [Slicing and striding](https://numpy.org/doc/stable/user/basics.indexing.html#slicing-and-striding) | [基本切片和索引](https://www.numpy.org.cn/reference/arrays/indexing.html#基本切片和索引)


