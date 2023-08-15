# Code：计算出Loss_function的输出数值

## 打开实验文件

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”，然后会显示出相应的图形。

### 这里的log函数都是以自然对数e=2.71828...为底的.

```python
print(math.log(1.))
print(math.log(0.95))
print(math.log(0.9))
print(math.log(0.8))
print('...')
print(math.log(0.2))
print(math.log(0.1))
print(math.log(0.05))
print(math.log(0.01))
print('...')
print(math.log(0.001))
print(math.log(0.0001))
print(math.log(0.00001))
print(math.log(0.000001))
print(math.log(0.0000001))
print(math.log(0.00000001))
print(math.log(0.000000001))
print(math.log(0.0000000001))
print(math.log(0.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001))
```

```python
import numpy as np

b = 5.2
print(np.log(b))
print(math.e ** 1.6486586255873816)
```

```python
import math

softmax_output = [0.7, 0.1, 0.2]	# An example output from the output layer of the neural network
target_output = [1, 0, 0]	# Ground truth

print(softmax_output[0]*target_output[0])
print(softmax_output[1]*target_output[1])
print(softmax_output[2]*target_output[2])

print(math.log(softmax_output[0]))
print(math.log(softmax_output[1]))
print(math.log(softmax_output[2]))

print(math.log(softmax_output[0])*target_output[0])
print(math.log(softmax_output[1])*target_output[1])
print(math.log(softmax_output[2])*target_output[2])

loss = -(math.log(softmax_output[0])*target_output[0] + 
		 math.log(softmax_output[1])*target_output[1] + 
		 math.log(softmax_output[2])*target_output[2])

print(loss)
```

```python
softmax_outputs = [[0.7, 0.1, 0.2],
                   [0.1, 0.5, 0.4],
                   [0.02, 0.9, 0.08]]

class_targets = [0, 1, 1] # dog, cat, cat

for targ_idx, distribution in zip(class_targets, softmax_outputs):
    print(distribution[targ_idx])
```

```python
import numpy as np

softmax_outputs = [[0.7, 0.1, 0.2],
                   [0.1, 0.5, 0.4],
                   [0.02, 0.9, 0.08]]

class_targets = np.array([[1, 0, 0],
						  [0, 1, 0],
						  [0, 1, 0]])

# Probabilities for target values -
# only if categorical labels
if len(class_targets.shape) == 1:
	correct_confidences = softmax_outputs[
		range(len(softmax_outputs)),
		class_targets
]

elif len(class_targets.shape) == 2:
	correct_confidences = np.sum(
		softmax_outputs * class_targets,
		axis=1
	)

# Losses
neg_log = -np.log(correct_confidences)

average_loss = np.mean(neg_log)
print(average_loss)
```

```python
import numpy as np

softmax_outputs = np.array([[0.7, 0.2, 0.1],	# Probabilities of 3 samples
							[0.5, 0.1, 0.4],
							[0.02, 0.9, 0.08]])

class_targets = np.array([0, 1, 1])	# Target (ground-truth) labels for 3 samples

predictions = np.argmax(softmax_outputs, axis=1)	# Calculate values along second axis (axis of index 1)

if len(class_targets.shape) == 2:	# If targets are one-hot encoded - convert them
	class_targets = np.argmax(class_targets, axis=1)
	
accuracy = np.mean(predictions==class_targets)	# True evaluates to 1; False to 0

print('acc:', accuracy)
```

```python
import numpy as np

class Layer_Dense:
	def __init__(self, n_inputs, n_neurons):
		self.weights = 0.01 * np.random.randn(n_inputs, n_neurons)
		self.biases = np.zeros((1, n_neurons))

	def forward(self, inputs):
		self.output = np.dot(inputs, self.weights) + self.biases

class Activation_ReLU:
	def forward(self, inputs):
		self.output = np.maximum(0, inputs)

class Activation_Softmax:
	def forward(self, inputs):
		# Get unnormalized probabilities
		exp_values = np.exp(inputs - np.max(inputs, axis=1,
		keepdims=True))

		# Normalize them for each sample
		probabilities = exp_values / np.sum(exp_values, axis=1,
		keepdims=True)

		self.output = probabilities

class Loss:
	def calculate(self, output, y):
		sample_losses = self.forward(output, y)
		data_loss = np.mean(sample_losses)
		return data_loss

class Loss_CategoricalCrossentropy(Loss):
	def forward(self, y_pred, y_true):
		# Number of samples in a batch
		samples = len(y_pred)

		# Clip data to prevent division by 0
		# Clip both sides to not drag mean towards any value
		y_pred_clipped = np.clip(y_pred, 1e-7, 1 - 1e-7)

		# Probabilities for target values -
		# only if categorical labels
		if len(y_true.shape) == 1:
			correct_confidences = y_pred_clipped[
				range(samples),
				y_true
		    ]
		# Mask values - only for one-hot encoded labels
		elif len(y_true.shape) == 2:
			correct_confidences = np.sum(
				y_pred_clipped * y_true,
				axis=1
			)
		# Losses
		negative_log_likelihoods = -np.log(correct_confidences)
		return negative_log_likelihoods

# Create dataset
N = 100 # number of points per class
D = 2 # dimensionality
K = 3 # number of classes
X = np.zeros((N*K,D)) # data matrix (each row = single example)
y = np.zeros(N*K, dtype='uint8') # class labels

# Create Dense layer with 2 input features and 3 output values
dense1 = Layer_Dense(2, 3)

# Create ReLU activation (to be used with Dense layer):
activation1 = Activation_ReLU()

# Create second Dense layer with 3 input features (as we take output
# of previous layer here) and 3 output values
dense2 = Layer_Dense(3, 3)

# Create Softmax activation (to be used with Dense layer):
activation2 = Activation_Softmax()

# Create loss function
loss_function = Loss_CategoricalCrossentropy()

# Perform a forward pass of our training data through this layer
dense1.forward(X)

# Perform a forward pass through activation function
# it takes the output of first dense layer here
activation1.forward(dense1.output)

# Perform a forward pass through second Dense layer
# it takes outputs of activation function of first layer as inputs
dense2.forward(activation1.output)

# Perform a forward pass through activation function
# it takes the output of second dense layer here
activation2.forward(dense2.output)

# Let's see output of the first few samples:
print(activation2.output[:5])

# Perform a forward pass through loss function
# it takes the output of second dense layer here and returns loss
loss = loss_function.calculate(activation2.output, y)

# Print loss value
print('loss:', loss)
```

## 参考文献及资料

1. [Neural Networks from Scratch](https://nnfs.io/)
2. [Python/p007-Categorical-Cross-Entropy-Loss.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p007-Categorical-Cross-Entropy-Loss.py) | [Python/p008-Categorical-Cross-Entropy-Loss-applied.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p008-Categorical-Cross-Entropy-Loss-applied.py)
4. [CS231n Convolutional Neural Networks for Visual Recognition](https://cs231n.github.io/neural-networks-case-study/)
5. [zip(*iterables, strict=False) from **docs.python.org**](https://docs.python.org/3/library/functions.html#zip) | [Python zip() Function](https://www.w3schools.com/python/ref_func_zip.asp)
7. [numpy.argmax](https://numpy.org/doc/stable/reference/generated/numpy.argmax.html) | [NumPy argmax()](https://www.programiz.com/python-programming/numpy/methods/argmax)
