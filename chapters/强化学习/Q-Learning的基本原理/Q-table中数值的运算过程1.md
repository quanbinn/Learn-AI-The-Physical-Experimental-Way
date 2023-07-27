# Q-table中数值的运算过程1

## 开始做

### 1.对于所有的从现有状态行动到新状态的新数值的计算公式，如下图所示。注明：在下面的运算过程中，折扣因子γ均取值为0.8。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/1a0.jpeg)

#### 从状态B行动到状态F的新数值的计算公式和计算过程，如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/1a1.jpg)

#### 计算出从状态B行动到状态F的新的数值，然后用铅笔写在小木块上，随后放在矩阵Ｑ的实体模型里，如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/1a2.jpg)

### 2.计算出从状态D行动到状态B的新的数值，然后用铅笔写在小木块上，随后放在矩阵Ｑ的实体模型里，如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/2a1.jpg)

#### 计算出从状态E行动到状态F,从状态F行动到状态F的新的数值，然后用铅笔写在小木块上，随后放在矩阵Ｑ的实体模型里，如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/2a2.jpg)

#### 计算出从状态E行动到状态A,从状态D行动到状态C,从状态B行动到状态D,从状态C行动到状态D,从状态E行动到状态D的新的数值，然后用铅笔写在小木块上，随后放在矩阵Ｑ的实体模型里，如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/2a3.jpg)

#### 计算出从状态A行动到状态E　,从状态D行动到状态E,从状态F行动到状态B,从状态F行动到状态E的新的数值，然后用铅笔写在小木块上，随后放在矩阵Ｑ的实体模型里，如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/2a4.jpg)

#### 计算出从状态B行动到状态E,从状态E行动到状态F,从状态F行动到状态F的新的数值，然后用铅笔写在小木块上，随后放在矩阵Ｑ的实体模型里，如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/2a5.jpg)

### 3.单击右方的[QLearningExample](https://github.com/quanbinn/learn-dl-the-experimental-way/blob/master/issues%2Bhistory/excel/QLearningExample.xls)，在打开的网页下方单击“View raw ”，然后浏览器会下载并打开一个Excel文件“QLearningExample.xls”。打开“RL1”sheet, 你会看到Q-table中数值的运算过程1的结果Q(1)和Q(1)(Percentage), 分别如下图所示。

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/Q1-1.png)

![](/images/强化学习/Q-Learning的基本原理/Q-table中数值的运算过程1/Q1-2.png)

## 参考文献及资料

1. 维基百科
	- [Q-learning](https://en.wikipedia.org/wiki/Q-learning) 
	- [Markov decision process](https://en.wikipedia.org/wiki/Markov_decision_process) 

1. [Q-Learning using Excel](https://people.revoledu.com/kardi/tutorial/ReinforcementLearning/Q-Learning-Excel.htm)