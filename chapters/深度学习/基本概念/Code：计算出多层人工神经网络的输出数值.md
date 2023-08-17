# Code：计算出多层人工神经网络的输出数值

## 打开实验文件

### 在线调试环境

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”。

## 重要知识：

- np.random.randn(numberOfRows, numberOfColumns)中的rand**n**是random **n**ormal distributation的缩写组合，这个函数中的输入变量是数据的行数和列数，输出结果是一个满足正态分布的矩阵。

```python
import numpy as np

x = np.random.randn(3,5)
print(x)

# y = 0.01 * np.random.randn(3,5)
# print(y)
```

- np.zeros()的输入变量是一个touple, touple包含着数据的行数和列数, 输出结果是一个矩阵。

```python
import numpy as np

x = np.zeros((2,5))
print(x)
```

#### 创建1层包含n个人工神经元（hard coding）

```python
import numpy as np

inputs = [[1, 2, 3, 2.5], [2., 5., -1., 2], [-1.5, 2.7, 3.3, -0.8]]
weights = [[0.2, 0.8, -0.5, 1],
[0.5, -0.91, 0.26, -0.5],
[-0.26, -0.27, 0.17, 0.87]]
biases = [2, 3, 0.5]

weights2 = [[0.1, -0.14, 0.5],
[-0.5, 0.12, -0.33],
[-0.44, 0.73, -0.13]]
biases2 = [-1, 2, -0.5]

layer1_outputs = np.dot(inputs, np.array(weights).T) + biases
layer2_outputs = np.dot(layer1_outputs, np.array(weights2).T) + biases2

print(layer2_outputs)
```

#### 创建生成1层包含n个人工神经元的类

```python
import numpy as np 

np.random.seed(0)

X = [[1, 2, 3, 2.5],
     [2.0, 5.0, -1.0, 2.0],
     [-1.5, 2.7, 3.3, -0.8]]

class Layer_Dense:
    def __init__(self, n_inputs, n_neurons):
        self.weights = 0.10 * np.random.randn(n_inputs, n_neurons)
        self.biases = np.zeros((1, n_neurons))
    def forward(self, inputs):
        self.output = np.dot(inputs, self.weights) + self.biases

layer1 = Layer_Dense(4,5)
layer2 = Layer_Dense(5,2)

layer1.forward(X) #print(layer1.output)
layer2.forward(layer1.output)
print(layer2.output)
```

## 参考文献及资料

1. [Neural Networks from Scratch in Python](https://nnfs.io/)
2. [Python/p004-Layers-and-Object.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p004-Layers-and-Object.py)
3. [CS231n Convolutional Neural Networks for Visual Recognition](https://cs231n.github.io/neural-networks-case-study/)


