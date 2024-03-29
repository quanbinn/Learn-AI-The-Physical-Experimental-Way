# array()

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

print(np.array([1, 2, 3]))
print(np.array([1, 2, 3.0]))
print(np.array([[1, 2], [3, 4]]))

print(np.array([1, 2, 3], ndmin=2))
print(np.array([1, 2, 3], dtype=complex))
print(np.array([1, 2, 3], dtype=complex))

x = np.array([(1,2),(3,4)],dtype=[('a','<i4'),('b','<i4')])
print(x['a'])

print(np.array(np.mat('1 2; 3 4')))
print(np.array(np.mat('1 2; 3 4'), subok=True))
```

## 参考文献及资料

1. [numpy.array(object, dtype=None, *, copy=True, order='K', subok=False, ndmin=0, like=None)](https://numpy.org/doc/stable/reference/generated/numpy.array.html#numpy.array)
2. [The N-dimensional array (ndarray)](https://numpy.org/doc/stable/reference/arrays.ndarray.html) | [N维数组（ndarray）](https://www.numpy.org.cn/reference/arrays/ndarray.html)
3. [NumPy: N-dimensional array (ndarray)](https://www.w3resource.com/numpy/ndarray/index.php#:~:text=N-dimensional%20array%20An%20ndarray%20is%20a%20%28usually%20fixed-size%29,integers%20that%20specify%20the%20sizes%20of%20each%20dimension.)


