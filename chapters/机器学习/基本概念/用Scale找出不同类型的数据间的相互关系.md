# 用Scale找出不同类型的数据间的相互关系

## 打开实验文件

- 单击右方的[Online Python Editor for Machine learning | Data Science](https://pythonbaba.com/online-python-code-editor-and-ide-for-data-science/)。
- 在打开的网页中，单击中间的“Click to see the Demo Code Execution”，后会显示出Python的在线编辑器。
- 把下面的python代码段拷贝到在线编辑器左边的空白栏中，然后单击上方的按键“Run”。
- **注明: 单击[cars.csv](https://www.w3school.com.cn/python/cars.csv), 会自动下载cars.csv文件**.

```python
import pandas
from sklearn import linear_model
from sklearn.preprocessing import StandardScaler
scale = StandardScaler()

df = pandas.read_csv("cars2.csv")

X = df[['Weight', 'Volume']]

scaledX = scale.fit_transform(X)

print(scaledX)
```

```python
import pandas
from sklearn import linear_model
from sklearn.preprocessing import StandardScaler
scale = StandardScaler()

df = pandas.read_csv("cars2.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

scaledX = scale.fit_transform(X)

regr = linear_model.LinearRegression()
regr.fit(scaledX, y)

scaled = scale.transform([[2300, 1.3]])

predictedCO2 = regr.predict([scaled[0]])
print(predictedCO2)
```

## 参考文献及资料

1. [Scale](https://www.w3schools.com/python/python_ml_scale.asp)
1. [缩放](https://www.w3school.com.cn/python/python_ml_scale.asp)


