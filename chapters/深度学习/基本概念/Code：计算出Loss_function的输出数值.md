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
softmax_outputs = [[0.7, 0.1, 0.2],
                   [0.1, 0.5, 0.4],
                   [0.02, 0.9, 0.08]]

class_targets = [0, 1, 1] # dog, cat, cat

print(softmax_outputs[[0, 1, 2], class_targets])
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

## 参考文献及资料

1. [Neural Networks from Scratch](https://nnfs.io/)
2. [Python/p007-Categorical-Cross-Entropy-Loss.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p007-Categorical-Cross-Entropy-Loss.py)
3. [Python/p008-Categorical-Cross-Entropy-Loss-applied.py](https://github.com/Sentdex/NNfSiX/blob/master/Python/p008-Categorical-Cross-Entropy-Loss-applied.py)
4. [CS231n Convolutional Neural Networks for Visual Recognition](https://cs231n.github.io/neural-networks-case-study/)