# 数据集中多个数据的Mean,Median,和Mode

## 在线调试环境

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

```python
import numpy

speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]

x = numpy.mean(speed)

print(x)

# import numpy
# speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]
# x = numpy.median(speed)
# print(x)

# import numpy
# speed = [99,86,87,88,86,103,87,94,78,77,85,86]
# x = numpy.median(speed)
# print(x)

# from scipy import stats
# speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]
# x = stats.mode(speed)
# print(x)

#The mode() method returns a ModeResult object that 
# contains the mode number (86), and count (how many
# times the mode number appeared (3)).
```

## 参考文献及资料

1. [Mean Median Mode](https://www.w3schools.com/python/python_ml_mean_median_mode.asp)
2. [平均中位数模式](https://www.w3school.com.cn/python/python_ml_mean_median_mode.asp)


