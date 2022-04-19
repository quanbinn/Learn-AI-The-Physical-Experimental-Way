# 使用NumPy调试Sigmoid function的代码

## 在线调试环境

- 单机右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

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