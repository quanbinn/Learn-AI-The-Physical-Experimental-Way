# 使用NumPy调试Sigmoid function的代码

## 打开实验文件

单击右方的[在线代码段Url网址](http://www.pythontutor.com/visualize.html#code=import%20numpy%20as%20np%0A%0Aprint%28np.exp%28-6%29%29%0Aprint%28np.exp%28-4%29%29%0Aprint%28np.exp%28-2%29%29%0Aprint%28np.exp%280%29%29%0A%0Adef%20sigmoid%28x%29%3A%0A%20%20%20%20s%20%3D%201%20/%20%281%20%2B%20np.exp%28-x%29%29%0A%20%20%20%20return%20s%0A%0Aprint%28sigmoid%28-6%29%29%0Aprint%28sigmoid%28-4%29%29%0Aprint%28sigmoid%28-2%29%29%0Aprint%28sigmoid%280%29%29%0Aprint%28sigmoid%282%29%29%0Aprint%28sigmoid%284%29%29%0Aprint%28sigmoid%286%29%29%0A%0Ax%20%3D%20np.array%28%5B-6,%20-4,%20-2,%200,%202,%204,%206%5D%29%0Aprint%28sigmoid%28x%29%29&cumulative=false&heapPrimitives=nevernest&mode=edit&origin=opt-frontend.js&py=py3anaconda&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```python
import numpy as np

print(np.exp(-6))
print(np.exp(-4))
print(np.exp(-2))
print(np.exp(0))

def sigmoid(x):
    s = 1 / (1 + np.exp(-x))
    return s

print(sigmoid(-6))
print(sigmoid(-4))
print(sigmoid(-2))
print(sigmoid(0))
print(sigmoid(2))
print(sigmoid(4))
print(sigmoid(6))

x = np.array([-6, -4, -2, 0, 2, 4, 6])
print(sigmoid(x))
```

## 参考文献及资料

1. [NumPy：Quickstart tutorial (Universal Functions)](https://numpy.org/devdocs/user/quickstart.html#universal-functionsl)