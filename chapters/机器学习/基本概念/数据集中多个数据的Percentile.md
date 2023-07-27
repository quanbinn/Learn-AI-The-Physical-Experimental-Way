# 数据集中多个数据的Percentile

## 在线调试环境

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

```python
import numpy

ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]

x = numpy.percentile(ages, 75)

print(x)

# import numpy
# ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]
# x = numpy.percentile(ages, 90)
# print(x)
```

## 参考文献及资料

1. [Percentile](https://www.w3schools.com/python/python_ml_percentile.asp)
1. [百分位数](https://www.w3school.com.cn/python/python_ml_percentile.asp)


