# 数据集中多个数据的Scatter Plot

## 打开实验文件

- 单击右方的[Online Python Editor for Machine learning | Data Science](https://pythonbaba.com/online-python-code-editor-and-ide-for-data-science/)。
- 在打开的网页中，单击中间的“Click to see the Demo Code Execution”，后会显示出Python的在线编辑器。
- 把下面的python代码段拷贝到在线编辑器左边的空白栏中，然后单击上方的按键“Run”。

```python
import matplotlib.pyplot as plt

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

plt.scatter(x, y)
plt.show()
```

```python
import numpy
import matplotlib.pyplot as plt

x = numpy.random.normal(5.0, 1.0, 1000)
y = numpy.random.normal(10.0, 2.0, 1000)

plt.scatter(x, y)
plt.show()
```

## 参考文献及资料

1. [Scatter Plot](https://www.w3schools.com/python/python_ml_scatterplot.asp)
1. [散点图](https://www.w3school.com.cn/python/python_ml_scatterplot.asp)


