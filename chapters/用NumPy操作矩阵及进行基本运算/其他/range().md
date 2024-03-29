# range()

## 本质意义： 。

### 在线调试环境1

- 单击右方的[Jupyter Notebook](https://mybinder.org/v2/gh/ipython/ipython-in-depth/master?filepath=binder/Index.ipynb)，稍后在浏览器里会显示Jupyter Notebook的运行环境。
- 在File的第一个下拉菜单“New Notebook” 的右侧箭头处选择“Python 3”，然后会显示一个新的页面
- 把下面的这段python代码拷贝到这个页面“In [ ]:”右侧的空白栏中， 然后单击上方的按键“运行”。

### 在线调试环境2

- 单击右方的[Python Online Compiler](https://trinket.io/python3/a5bd54189b)，稍后在浏览器里会显示python的运行环境。
- 把下面的这段python代码拷贝到这个页面左侧的空白栏中， 然后单击上方的按键“Run”。

```python
number_of_iteration = 5

for i in range(number_of_iteration):
    print("第",i+1,"次运行迭代任务中的第1步")    
    print("第",i+1,"次运行迭代任务中的第2步")    
    print("第",i+1,"次运行迭代任务中的第3步")    
    print("第",i+1,"次运行-----------------")
    print("第",i+1,"次运行迭代任务中的第n步")
    print("第",i+1,"次运行完迭代任务中的所有步骤")    
    print("-----------------------------------------")
```

```python
print(list(range(10)))
print(list(range(1, 11)))
print(list(range(0, 30, 5)))
print(list(range(0, 10, 3)))
print(list(range(0, -10, -1)))

print(list(range(0)))
print(list(range(1, 0)))
```

```python
r = range(0, 20, 2)
print(r)
print(11 in r)
print(10 in r)

print(r.index(10))

print(r[5])
print(r[:5])
print(r[-1])
```

## 参考文献及资料

1. [Ranges](https://docs.python.org/3/library/stdtypes.html#ranges)


