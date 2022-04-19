# 用Matplotlib绘出最小平方法的线性拟合

## 打开实验文件

### 在线调试环境1

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”。

### 在线调试环境2

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

```python
##最小二乘法
import numpy as np   ##科学计算库 
import scipy as sp   ##在numpy基础上实现的部分算法库
import matplotlib.pyplot as plt  ##绘图库
from scipy.optimize import leastsq  ##引入最小二乘法算法

'''
     设置样本数据，真实数据需要在这里处理
'''
##样本数据(Xi,Yi)，需要转换成数组(列表)形式
Xi=np.array([2,5,8,12])
Yi=np.array([1,4,5,6])

'''
    设定拟合函数和偏差函数
    函数的形状确定过程：
    1.先画样本图像
    2.根据样本图像大致形状确定函数形式(直线、抛物线、正弦余弦等)
'''

##需要拟合的函数func :指定函数的形状
def func(p,x):
    k,b=p
    return k*x+b

##偏差函数：x,y都是列表:这里的x,y更上面的Xi,Yi中是一一对应的
def error(p,x,y):
    return func(p,x)-y

'''
    主要部分：附带部分说明
    1.leastsq函数的返回值tuple，第一个元素是求解结果，第二个是求解的代价值(个人理解)
    2.官网的原话（第二个值）：Value of the cost function at the solution
    3.实例：Para=>(array([ 0.61349535,  1.79409255]), 3)
    4.返回值元组中第一个值的数量跟需要求解的参数的数量一致
'''

#k,b的初始值，可以任意设定,经过几次试验，发现p0的值会影响cost的值：Para[1]
p0=[1,20]

#把error函数中除了p0以外的参数打包到args中(使用要求)
Para=leastsq(error,p0,args=(Xi,Yi))

#读取结果
k,b=Para[0]
print("k=",k,"b=",b)
print("cost："+str(Para[1]))
print("求解的拟合直线为:")
print("y="+str(round(k,2))+"x+"+str(round(b,2)))

'''
   绘图，看拟合效果.
   matplotlib默认不支持中文，label设置中文的话需要另行设置
   如果报错，改成英文就可以
'''

#画样本点
plt.figure(figsize=(8,6)) ##指定图像比例： 8：6
plt.scatter(Xi,Yi,color="green",label="样本数据",linewidth=2) 

#画拟合直线
x=np.linspace(0,12,100) ##在0-15直接画100个连续点
y=k*x+b ##函数式
plt.plot(x,y,color="red",label="拟合直线",linewidth=2) 
plt.legend(loc='lower right') #绘制图例
plt.show()
```

## 参考文献及资料

1. [最小平方法与线性拟合](https://github.com/quanbinn/Learn-Mathematical-Olympiad-The-Interactive-Way/blob/master/chapters/%E7%BB%9F%E8%AE%A1/%E6%9C%80%E5%B0%8F%E5%B9%B3%E6%96%B9%E6%B3%95%E4%B8%8E%E7%BA%BF%E6%80%A7%E6%8B%9F%E5%90%88.md#12%E4%B8%8A%E4%B8%80%E6%AC%A1%E7%9A%84%E5%87%BD%E6%95%B0%E5%BC%8F%E5%8F%AF%E5%86%99%E4%B8%BAsmc237-m2--54mc--4c2---268m---32c--78-%E7%84%B6%E5%90%8E%E8%BF%99%E4%B8%80%E6%AD%A5%E6%B1%82smc%E7%9A%84%E6%9C%80%E5%B0%8F%E5%80%BC%E7%9A%84%E9%97%AE%E9%A2%98%E5%8F%AF%E7%AE%80%E5%8C%96%E4%B8%BA%E6%B1%82smc%E7%9B%B8%E5%AF%B9%E4%BA%8Em%E5%92%8Cc%E7%9A%84%E5%81%8F%E5%AF%BC%E6%95%B0%E4%B8%BA%E9%9B%B6%E7%9A%84%E9%97%AE%E9%A2%98%E4%BD%A0%E5%8F%AF%E4%BB%A5%E6%BC%94%E7%AE%97%E5%87%BA%E4%B8%A4%E4%B8%AA%E5%8C%85%E5%90%AB%E5%8F%98%E9%87%8Fm%E5%92%8Cc%E7%9A%84%E4%BA%8C%E5%85%83%E4%B8%80%E6%AC%A1%E6%96%B9%E7%A8%8B%E5%BC%8F%E5%A6%82%E4%B8%8B%E5%9B%BE%E6%89%80%E7%A4%BA)
2. [机器学习：Python中如何使用最小二乘法](https://www.cnblogs.com/lc1217/p/6514734.html)

