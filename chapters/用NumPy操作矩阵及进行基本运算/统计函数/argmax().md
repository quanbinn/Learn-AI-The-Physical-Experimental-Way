# argmax()

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

a = np.arange(6).reshape(2,3) + 10
print(a)

print(np.argmax(a))
print(np.argmax(a, axis=0))
print(np.argmax(a, axis=1))

ind = np.unravel_index(np.argmax(a, axis=None), a.shape)
print(ind)
print(a[ind])

b = np.arange(6)
b[1] = 5
print(b)

print(np.argmax(b))  # Only the first occurrence is returned.

x = np.array([[4,2,3], [1,0,3]])
index_array = np.argmax(x, axis=-1)
# Same as np.amax(x, axis=-1, keepdims=True)
print(np.take_along_axis(x, np.expand_dims(index_array, axis=-1), axis=-1))

# Same as np.amax(x, axis=-1)
print(np.take_along_axis(x, np.expand_dims(index_array, axis=-1), axis=-1).squeeze(axis=-1))

x = np.arange(24).reshape((2, 3, 4))
print(x)
```

## 参考文献及资料

1. [numpy.argmax(a, axis=None, out=None, *, keepdims=<no value>)[source]
](https://numpy.org/doc/stable/reference/generated/numpy.argmax.html#numpy.argmax)


