# arrayName[i]

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

x = np.arange(10)
print(x[2])
print(x[-2])

x.shape = (2, 5)  # now x is 2-dimensional
print(x[1, 3])
print(x[1, -1])

print(x[0])
print(x[0][2])
```

## 参考文献及资料

1. [Single element indexing](https://numpy.org/doc/stable/user/basics.indexing.html#single-element-indexing) | [索引](https://www.numpy.org.cn/user/basics/indexing.html)


