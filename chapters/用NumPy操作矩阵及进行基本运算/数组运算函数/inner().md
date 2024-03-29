# inner()

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

arrayA = np.array([4,0,0])
arrayB = np.array([2.12,2.12,0])

print(np.inner(arrayA, arrayB))

arrayC = np.array([0,1,0,1,0,1,1,0,1,1,1,0])
arrayD = np.array([-2.06435964536982,3.36218007211868,-0.628767424024859,-6.62350000397214,-0.327586812055479,-6.00811845087255,-2.57612599221276,12.2248103400252,-1.78245158375325,-8.61919831628837,13.895354849534,-1.3772261177545])

bias = -0.98739979981118

print(np.inner(arrayC, arrayD) + bias)
```

## 参考文献及资料

1. [numpy.inner(a, b, /)](https://numpy.org/doc/stable/reference/generated/numpy.inner.html#numpy.inner)
2. [用成45度角的两个向量体会数量积的计算公式](https://github.com/quanbinn/Learn-Mathematical-Olympiad-The-Interactive-Way/blob/master/chapters/%E7%BA%BF%E6%80%A7%E4%BB%A3%E6%95%B0/%E7%94%A8%E6%88%9045%E5%BA%A6%E8%A7%92%E7%9A%84%E4%B8%A4%E4%B8%AA%E5%90%91%E9%87%8F%E4%BD%93%E4%BC%9A%E6%95%B0%E9%87%8F%E7%A7%AF%E7%9A%84%E8%AE%A1%E7%AE%97%E5%85%AC%E5%BC%8F.md)
3. [【Excel示例文件】深度学习的数学.rar中的3-5 NN（求解器）.xlsx](http://www.ituring.com.cn/book/2593)中的“测试”Sheet


