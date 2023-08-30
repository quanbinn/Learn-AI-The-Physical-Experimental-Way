# Code：计算出特定的weight和bias的数值

## 本质意义： 。

## 打开实验文件

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”，然后会显示出相应的图形。

```python

```

```python

```

```python

```

```python

```

```python

```

```python
import numpy as np

class Layer_Dense:

	def __init__(self, n_inputs, n_neurons):
		self.weights = 0.01 * np.random.randn(n_inputs, n_neurons)
		self.biases = np.zeros((1, n_neurons))
	
	def forward(self, inputs):
		# Remember input values
		self.inputs = inputs
		# Calculate output values from inputs, weights and biases
		self.output = np.dot(inputs, self.weights) + self.biases

	def backward(self, dvalues):
		# Gradients on parameters
		self.dweights = np.dot(self.inputs.T, dvalues)
		self.dbiases = np.sum(dvalues, axis=0, keepdims=True)
		# Gradient on values
		self.dinputs = np.dot(dvalues, self.weights.T)

# ReLU activation
class Activation_ReLU:
	# Forward pass
	def forward(self, inputs):
		# Remember input values
		self.inputs = inputs
		# Calculate output values from inputs
		self.output = np.maximum(0, inputs)

	# Backward pass
	def backward(self, dvalues):
		# Since we need to modify original variable,
		# let's make a copy of values first
		self.dinputs = dvalues.copy()
		# Zero gradient where input values were negative
		self.dinputs[self.inputs <= 0] = 0

class Activation_Softmax:
	# Forward pass
	def forward(self, inputs):
		# Remember input values
		self.inputs = inputs
		# Get unnormalized probabilities
		exp_values = np.exp(inputs - np.max(inputs, axis=1,
		keepdims=True))
		# Normalize them for each sample
		probabilities = exp_values / np.sum(exp_values, axis=1,
		keepdims=True)
		self.output = probabilities
		# Backward pass

def backward(self, dvalues):
	# Create uninitialized array
	self.dinputs = np.empty_like(dvalues)
	# Enumerate outputs and gradients
	for index, (single_output, single_dvalues) in \
			enumerate(zip(self.output, dvalues)):
		# Flatten output array
		single_output = single_output.reshape(-1, 1)
		# Calculate Jacobian matrix of the output and
		jacobian_matrix = np.diagflat(single_output) - \
		np.dot(single_output, single_output.T)

		# Calculate sample-wise gradient
		# and add it to the array of sample gradients
		self.dinputs[index] = np.dot(jacobian_matrix,
		single_dvalues)

class Loss:
	# Calculates the data and regularization losses
	# given model output and ground truth values
	def calculate(self, output, y):
		# Calculate sample losses
		sample_losses = self.forward(output, y)
		# Calculate mean loss
		data_loss = np.mean(sample_losses)
		# Return loss
		return data_loss

class Loss_CategoricalCrossentropy(Loss):
	# Forward pass
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

		negative_log_likelihoods = -np.log(correct_confidences)
		return negative_log_likelihoods

	# Backward pass
	def backward(self, dvalues, y_true):

		# Number of samples
		samples = len(dvalues)
		# Number of labels in every sample
		# We'll use the first sample to count them
		labels = len(dvalues[0])
		# If labels are sparse, turn them into one-hot vector
		if len(y_true.shape) == 1:
			y_true = np.eye(labels)[y_true]

		# Calculate gradient
		self.dinputs = -y_true / dvalues
		# Normalize gradient
		self.dinputs = self.dinputs / samples

# Softmax classifier - combined Softmax activation
# and cross-entropy loss for faster backward step
class Activation_Softmax_Loss_CategoricalCrossentropy():

	# Creates activation and loss function objects
	def __init__(self):
		self.activation = Activation_Softmax()
		self.loss = Loss_CategoricalCrossentropy()

	def forward(self, inputs, y_true):
		# Output layer's activation function
		self.activation.forward(inputs)
		# Set the output
		self.output = self.activation.output
		# Calculate and return loss value
		return self.loss.calculate(self.output, y_true)

	# Backward pass
	def backward(self, dvalues, y_true):
		# Number of samples
		samples = len(dvalues)

		# If labels are one-hot encoded,
		# turn them into discrete values
		if len(y_true.shape) == 2:
			y_true = np.argmax(y_true, axis=1)

		# Copy so we can safely modify
		self.dinputs = dvalues.copy()
		# Calculate gradient
		self.dinputs[range(samples), y_true] -= 1
		# Normalize gradient
		self.dinputs = self.dinputs / samples


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
# of previous layer here) and 3 output values (output values)
dense2 = Layer_Dense(3, 3)
# Create Softmax classifier's combined loss and activation
loss_activation = Activation_Softmax_Loss_CategoricalCrossentropy()
# Perform a forward pass of our training data through this layer
dense1.forward(X)
# Perform a forward pass through activation function
# takes the output of first dense layer here
activation1.forward(dense1.output)
# Perform a forward pass through second Dense layer
# takes outputs of activation function of first layer as inputs
dense2.forward(activation1.output)
# Perform a forward pass through the activation/loss function
# takes the output of second dense layer here and returns loss
loss = loss_activation.forward(dense2.output, y)

# Let's see output of the first few samples:
print(loss_activation.output[:5])
# Print loss value
print('loss:', loss)

# Calculate accuracy from output of activation2 and targets
# calculate values along first axis
predictions = np.argmax(loss_activation.output, axis=1)
if len(y.shape) == 2:
	y = np.argmax(y, axis=1)
accuracy = np.mean(predictions==y)
# Print accuracy
print('acc:', accuracy)

# Backward pass
loss_activation.backward(loss_activation.output, y)
dense2.backward(loss_activation.dinputs)
activation1.backward(dense2.dinputs)
dense1.backward(activation1.dinputs)

# Print gradients
print(dense1.dweights)
print(dense1.dbiases)
print(dense2.dweights)
print(dense2.dbiases)
```

## 参考文献及资料

1. [Neural Networks from Scratch in Python](https://nnfs.io/)
2. [Python/p007-Categorical-Cross-Entropy-Loss.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p007-Categorical-Cross-Entropy-Loss.py) | [Python/p008-Categorical-Cross-Entropy-Loss-applied.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p008-Categorical-Cross-Entropy-Loss-applied.py)
3. [CS231n Convolutional Neural Networks for Visual Recognition](https://cs231n.github.io/neural-networks-case-study/)

