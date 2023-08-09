# Code：计算出Sigmoid function的输出数值

## 打开实验文件

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”，然后会显示出相应的图形。

```python
import matplotlib.pyplot as plt
import numpy as np

def sigmoid(x):
    array = []
    for item in x:
        array.append(1/(1+np.exp(-item)))
    return array

x = np.arange(-6, 6.1, 2)

plt.plot(x,sigmoid(x))
plt.show()
```

```python
import numpy as np

print(np.exp(-6))
print(np.exp(-4))
print(np.exp(-2))
print(np.exp(0))

def sigmoid(x):
    return 1/(1+np.exp(-x))

print(sigmoid(-6))
print(sigmoid(-4))
print(sigmoid(-2))
print(sigmoid(0))
print(sigmoid(2))
print(sigmoid(4))
print(sigmoid(6))
```

```python
layer_outputs = [4.8, 1.21, 2.385]

E = 2.71828182846

exp_values = []
for output in layer_outputs:
	exp_values.append(E ** output)  # ** - power operator in Python

print('exponentiated values are:',exp_values)
```

```python
layer_outputs = [4.8, 1.21, 2.385]

E = 2.71828182846

exp_values = []
for output in layer_outputs:
	exp_values.append(E ** output)  # ** - power operator in Python

print('exponentiated values are:',exp_values)

norm_base = sum(exp_values) # We sum all values
norm_values = []

for value in exp_values:
	norm_values.append(value / norm_base)
print('Normalized exponentiated values:')
print(norm_values)
print('Sum of normalized values:', sum(norm_values))
```

```python
import numpy as np

layer_outputs = [4.8, 1.21, 2.385]

exp_values = np.exp(layer_outputs)
print('exponentiated values are:', exp_values)

norm_values = exp_values / np.sum(exp_values)	# Now normalize values
print('normalized exponentiated values are:', norm_values)
print('sum of normalized values:', np.sum(norm_values))
```

```python
import numpy as np

layer_outputs = np.array([[4.8, 1.21, 2.385],
						  [8.9, -1.81, 0.2],
						  [1.41, 1.051, 0.026]])

print('Sum without axis')
print(np.sum(layer_outputs))

print('This will be identical to the above since default is None:')
print(np.sum(layer_outputs, axis=None))

print('Another way to think of it w/ a matrix == axis 0: columns:')
print(np.sum(layer_outputs, axis=0))

print('But we want to sum the rows instead, like this w/ raw py:')

for i in layer_outputs:
    print(sum(i))
    
print('So we can sum axis 1, but note the current shape:')
print(np.sum(layer_outputs, axis=1))

print('Sum axis 1, but keep the same dimensions as input:')
print(np.sum(layer_outputs, axis=1, keepdims=True))
```

```python
import numpy as np

print(np.exp(1))
print(np.exp(10))
print(np.exp(100))

print(np.exp(1000))
print(np.exp(-np.inf), np.exp(0))
```

```python
class Activation_Softmax:
	def forward(self, inputs):
		exp_values = np.exp(inputs - np.max(inputs, axis=1, keepdims=True))	# Get unnormalized probabilities
		probabilities = exp_values / np.sum(exp_values, axis=1, keepdims=True)	# Normalize them for each sample
		self.output = probabilities

softmax = Activation_Softmax()

softmax.forward([[1, 2, 3]])
print(softmax.output)

softmax.forward([[-2, -1, 0]]) # subtracted 3 - max from the list
print(softmax.output)

softmax.forward([[0.5, 1, 1.5]])
print(softmax.output)
```

```python
import numpy as np 

np.random.seed(0)

X = [[1, 2],
     [2.0, 5.0],
     [-1.5, 2.7]]

class Layer_Dense:
    def __init__(self, n_inputs, n_neurons):
        self.weights = 0.1 * np.random.randn(n_inputs, n_neurons)
        self.biases = np.zeros((1, n_neurons))
    def forward(self, inputs):
        self.output = np.dot(inputs, self.weights) + self.biases

class Activation_ReLU:
    def forward(self, inputs):
        self.output = np.maximum(0, inputs)

class Activation_Softmax:
    def forward(self, inputs):
        exp_values = np.exp(inputs - np.max(inputs, axis=1, keepdims=True))
        probabilities = exp_values / np.sum(exp_values, axis=1, keepdims=True)
        self.output = probabilities

dense1 = Layer_Dense(2,3)
activation1 = Activation_ReLU()

dense2 = Layer_Dense(3, 3)
activation2 = Activation_Softmax()

dense1.forward(X)
activation1.forward(dense1.output)

dense2.forward(activation1.output)
activation2.forward(dense2.output)

print(activation2.output[:5])
```

## 参考文献及资料

1. [Neural Networks from Scratch](https://nnfs.io/)
2. [Python/p006-Softmax-Activation.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p006-Softmax-Activation.py)
3. [CS231n Convolutional Neural Networks for Visual Recognition](https://cs231n.github.io/neural-networks-case-study/)