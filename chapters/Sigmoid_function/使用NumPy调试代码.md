# 使用NumPy调试Sigmoid function的代码

## 打开实验文件

单击右方的[在线代码段Url网址](http://www.pythontutor.com/visualize.html#code=import%20numpy%20as%20np%0A%0Aprint%28np.exp%28-6%29%29%0Aprint%28np.exp%28-4%29%29%0Aprint%28np.exp%28-2%29%29%0Aprint%28np.exp%280%29%29%0A%0Adef%20sigmoid%28x%29%3A%0A%20%20%20%20return%201/%281%2Bnp.exp%28-x%29%29%0A%0Aprint%28sigmoid%28-6%29%29%0Aprint%28sigmoid%28-4%29%29%0Aprint%28sigmoid%28-2%29%29%0Aprint%28sigmoid%280%29%29%0Aprint%28sigmoid%282%29%29%0Aprint%28sigmoid%284%29%29%0Aprint%28sigmoid%286%29%29&cumulative=false&curInstr=34&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=py3anaconda&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

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

## 参考文献及资料

1. [NumPy：Quickstart tutorial (Universal Functions)](https://numpy.org/devdocs/user/quickstart.html#universal-functionsl)