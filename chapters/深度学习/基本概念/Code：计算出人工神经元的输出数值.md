# Code：计算出人工神经元的输出数值

## 本质意义： 。

## 打开实验文件

### 在线调试环境1

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”。

### 在线调试环境2

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

#### 单个神经元

```python
inputs = [1.2, 5.1, 2.1]
weights = [3.1, 2.1, 8.7]
bias = 3.0

output = inputs[0]*weights[0] + inputs[1]*weights[1] + inputs[2]*weights[2] + bias
print(output)

inputs = [1.0, 2.0, 3.0, 2.5]
```

#### 一层中的多个神经元

```python
inputs = [1.0, 2.0, 3.0, 2.5]

weights1 = [0.2, 0.8, -0.5, 1.0]
weights2 = [0.5, -0.91, 0.26, -0.5]
weights3 = [-0.26, -0.27, 0.17, 0.87]

bias1 = 2.0
bias2 = 3.0
bias3 = 0.5

output = [inputs[0]*weights1[0] + inputs[1]*weights1[1] + inputs[2]*weights1[2] + inputs[3]*weights1[3] + bias1,
          inputs[0]*weights2[0] + inputs[1]*weights2[1] + inputs[2]*weights2[2] + inputs[3]*weights2[3] + bias2,
          inputs[0]*weights3[0] + inputs[1]*weights3[1] + inputs[2]*weights3[2] + inputs[3]*weights3[3] + bias3]
print(output)
```

#### 用for loop替换上面的一层中的多个神经元的hard coding

```python
inputs = [1, 2, 3, 2.5]

weights = [[0.2, 0.8, -0.5, 1],
          [0.5, -0.91, 0.26, -0.5],
          [-0.26, -0.27, 0.17, 0.87]]
	       
biases = [2, 3, 0.5]

layer_outputs = []		# Output of current layer

for neuron_weights, neuron_bias in zip(weights, biases):		# For each neuron
	neuron_output = 0		# Zeroed output of given neuron
	
	for n_input, weight in zip(inputs, neuron_weights):			# For each input and weight to the neuron
		neuron_output += n_input*neuron_weights		# Multiply this input by associated weight and add to the neuron’s output variable

	neuron_output += neuron_bias			# Add bias
	layer_outputs.append(neuron_output)			# Put neuron’s result to the layer’s output list

print(layer_outputs)
```

#### 使用numpy中的dot()对单个神经元进行计算（使用了数学上矩阵数量积乘法的概念）

```python
import numpy as np

inputs = [1.0, 2.0, 3.0, 2.5]
weights = [0.2, 0.8, -0.5, 1.0]
bias = 2.0

outputs = np.dot(weights, inputs) + bias

print(outputs)
```

#### 使用numpy中的dot()对一层中的多个神经元进行计算（使用了数学上矩阵数量积乘法的概念）

```python
import numpy as np

inputs = [1.0, 2.0, 3.0, 2.5]
weights = [[0.2, 0.8, -0.5, 1],
[0.5, -0.91, 0.26, -0.5],
[-0.26, -0.27, 0.17, 0.87]]
biases = [2.0, 3.0, 0.5]

layer_outputs = np.dot(weights, inputs) + biases

print(layer_outputs)
```

#### 使用numpy中的dot()对一层中的多个神经元进行计算（多组输入数据）（使用了数学上矩阵数量积和向量积乘法的概念）

```python
import numpy as np

inputs = [[1.0, 2.0, 3.0, 2.5],
 [2.0, 5.0, -1.0, 2.0],
 [-1.5, 2.7, 3.3, -0.8]]
weights = [[0.2, 0.8, -0.5, 1.0],
 [0.5, -0.91, 0.26, -0.5],
 [-0.26, -0.27, 0.17, 0.87]]
biases = [2.0, 3.0, 0.5]

layer_outputs = np.dot(inputs, np.array(weights).T) + biases

print(layer_outputs)
```

## 参考文献及资料

1. [Neural Networks from Scratch in Python](https://nnfs.io/)
2. [p001-Basic-Neuron-3-inputs.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p001-Basic-Neuron-3-inputs.py) | [p002-Basic-Neuron-Layer.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p002-Basic-Neuron-Layer.py)
3. [p003-Dot-Product.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p003-Dot-Product.py)
