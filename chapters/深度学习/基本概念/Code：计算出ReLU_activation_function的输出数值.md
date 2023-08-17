# Code：计算出ReLU activation function的输出数值

## 重要知识点：
- np.random.seed(0)：从调试代码的结果来看，当seed()的变量取某一个特定值的时候，生成的随机数都是固定的。
- **看来计算机的随机数生成理论是一个重要的知识点。背后是概率和统计的数学背景，编程理论应该是唐纳德的随机数理论**。

## 打开实验文件

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”，然后会显示出相应的图形。

```python
sums_of_input = [0, 2, -1, 3.3, -2.7, 1.1, 2.2, -100]
values_of_output = []

for i in sums_of_input:
	if i > 0:
		values_of_output.append(i)
	else:
		values_of_output.append(0)

print(values_of_output)
```

```python
sums_of_input = [0, 2, -1, 3.3, -2.7, 1.1, 2.2, -100]

values_of_output = []

for i in sums_of_input:
	values_of_output.append(max(0, i))

print(values_of_output)
```

```python
import numpy as np

sums_of_input = [0, 2, -1, 3.3, -2.7, 1.1, 2.2, -100]
values_of_output = np.maximum(0, sums_of_input)

print(values_of_output)
```

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

class Activation_ReLU:
    def forward(self, inputs):
        self.output = np.maximum(0, inputs)

layer1 = Layer_Dense(4,5)
activation1 = Activation_ReLU()

layer1.forward(X)

#print(layer1.output)
activation1.forward(layer1.output)
print(activation1.output)
```

## 参考文献及资料

1. [Neural Networks from Scratch in Python](https://nnfs.io/)
2. [Python/p005-ReLU-Activation.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p005-ReLU-Activation.py)
3. [CS231n Convolutional Neural Networks for Visual Recognition](https://cs231n.github.io/neural-networks-case-study/)