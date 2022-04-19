# 用Multiple Regression找出不同类型的数据间的相互关系

## 打开实验文件

- 单击右方的[Online Python Editor for Machine learning | Data Science](https://pythonbaba.com/online-python-code-editor-and-ide-for-data-science/)。
- 在打开的网页中，单击中间的“Click to see the Demo Code Execution”，后会显示出Python的在线编辑器。
- 把下面的python代码段拷贝到在线编辑器左边的空白栏中，然后单击上方的按键“Run”。
- **注明: 单击[cars.csv](https://www.w3school.com.cn/python/cars.csv), 会自动下载cars.csv文件**.

```python
import pandas
from sklearn import linear_model

df = pandas.read_csv("cars.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

# 预测重量为 2300kg、排量为 1300ccm 的汽车的二氧化碳排放量：

predictedCO2 = regr.predict([[2300, 1300]])

print(predictedCO2)
```

```python
import pandas
from sklearn import linear_model

df = pandas.read_csv("cars.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

print(regr.coef_)
```

```python
import pandas
from sklearn import linear_model

df = pandas.read_csv("cars.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

predictedCO2 = regr.predict([[3300, 1300]])

print(predictedCO2)
```

## 参考文献及资料

1. [Multiple Regression](https://www.w3schools.com/python/python_ml_multiple_regression.asp)
1. [多项式回归](https://www.w3school.com.cn/python/python_ml_polynomial_regression.asp)


