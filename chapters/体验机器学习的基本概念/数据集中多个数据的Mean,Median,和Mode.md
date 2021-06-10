# 数据集中多个数据的Mean,Median,和Mode

## 打开实验文件

单击右方的[在线代码段Url网址](http://www.pythontutor.com/visualize.html#code=import%20numpy%0A%0Aspeed%20%3D%20%5B99,86,87,88,111,86,103,87,94,78,77,85,86%5D%0A%0Ax%20%3D%20numpy.mean%28speed%29%0A%0Aprint%28x%29%0A%0A%23%20import%20numpy%0A%23%20speed%20%3D%20%5B99,86,87,88,111,86,103,87,94,78,77,85,86%5D%0A%23%20x%20%3D%20numpy.median%28speed%29%0A%23%20print%28x%29%0A%0A%23%20import%20numpy%0A%23%20speed%20%3D%20%5B99,86,87,88,86,103,87,94,78,77,85,86%5D%0A%23%20x%20%3D%20numpy.median%28speed%29%0A%23%20print%28x%29%0A%0A%23%20from%20scipy%20import%20stats%0A%23%20speed%20%3D%20%5B99,86,87,88,111,86,103,87,94,78,77,85,86%5D%0A%23%20x%20%3D%20stats.mode%28speed%29%0A%23%20print%28x%29%0A%0A%23The%20mode%28%29%20method%20returns%20a%20ModeResult%20object%20that%20%0A%23%20contains%20the%20mode%20number%20%2886%29,%20and%20count%20%28how%20many%0A%23%20times%20the%20mode%20number%20appeared%20%283%29%29.%0A%0A&cumulative=false&heapPrimitives=nevernest&mode=edit&origin=opt-frontend.js&py=py3anaconda&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

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


