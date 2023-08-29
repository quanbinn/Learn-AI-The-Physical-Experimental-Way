# r_

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

print(np.r_[np.array([1,2,3]), 0, 0, np.array([4,5,6])])
print(np.r_[-1:1:6j, [0]*3, 5, 6])

a = np.array([[0, 1, 2], [3, 4, 5]])
print(np.r_['-1', a, a]) # concatenate along last axis

print(np.r_['0,2', [1,2,3], [4,5,6]]) # concatenate along first axis, dim>=2

print(np.r_['0,2,0', [1,2,3], [4,5,6]])
print(np.r_['1,2,0', [1,2,3], [4,5,6]])

print(np.r_['r',[1,2,3], [4,5,6]])
```

## 参考文献及资料

1. [numpy.r_ = <numpy.lib.index_tricks.RClass object>](https://numpy.org/doc/stable/reference/generated/numpy.r_.html) 
