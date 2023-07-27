# Learn Deep & Reinforcement & Machine Learning The Physical Experimental Way
# 《用实体实验法学深度和强化和机器学习》

Learn-Mathematics-The--Experimental-Way

### 实验前的准备

- [**重要：首先购买实验道具**]() | [作者简介]() | [实验方法]() | [调试学习代码段的N个阶段](/chapters/实验前的准备/调试学习代码段的N个阶段.md)
- [**重要：安装Anaconda**](/chapters/环境配置/安装Anaconda.md) | [**重要：通过conda安装PyTorch**](/chapters/环境配置/通过conda安装PyTorch.md) | [**重要：通过conda安装TensorFlow**](/chapters/环境配置/通过conda安装TensorFlow.md)

### 基本数据类型

- 图像： [1张图像中的100个RGB值](/chapters/基本数据类型/图像/1张图像中的100个RGB值.md) | [在线体验RGB与HSV之间的相互转换](/chapters/基本数据类型/图像/在线体验RGB与HSV之间的相互转换.md) | [在线体验1张图片的RGB颜色空间](/chapters/基本数据类型/图像/在线体验1张图片的RGB颜色空间.md)

### 深度学习


- 神经网络
	- [输入图像实例的数据和神经网络的代价函数](/chapters/深度学习/神经网络/输入图像实例的数据和神经网络的代价函数.md) | [神经网络中用到的变量名和参数名的表示方法](/chapters/深度学习/神经网络/神经网络中用到的变量名和参数名的表示方法.md)
	- [第2层中3个神经单元的输入值和输出值](/chapters/深度学习/神经网络/第2层中3个神经单元的输入值和输出值.md) | [第3层中2个神经单元的输入值和输出值](/chapters/深度学习/神经网络/第3层中2个神经单元的输入值和输出值.md)
	- [用代价函数计算出1个学习实例的代价](/chapters/深度学习/神经网络/用代价函数计算出1个学习实例的代价.md)
	- [用偏导数的链式法则求出梯度的1个向量](/chapters/深度学习/神经网络/用偏导数的链式法则求出梯度的1个向量.md) | [用反向传播算法求出梯度的1个向量](/chapters/体验神经网络中的数学原理/用反向传播算法求出梯度的1个向量.md)

- 卷积神经网络

	- [输入图像实例的数据和神经网络的代价函数](/chapters/深度学习/卷积神经网络/输入图像实例的数据和神经网络的代价函数.md) | [卷积神经网络中用到的变量名和参数名的表示方法](/chapters/深度学习/卷积神经网络/卷积神经网络中用到的变量名和参数名的表示方法.md)
	- [过滤器和卷积层中的输入值和输出值](/chapters/深度学习/卷积神经网络/过滤器和卷积层中的输入值和输出值.md) | [池化层中的输入值和输出值](/chapters/深度学习/卷积神经网络/池化层中的输入值和输出值.md) | [输出层3个神经单元的输入值和输出值](/chapters/深度学习/卷积神经网络/输出层3个神经单元的输入值和输出值.md)
	- [用代价函数计算出1个学习实例的代价](/chapters/深度学习/卷积神经网络/用代价函数计算出1个学习实例的代价.md) | [用反向传播算法求出梯度的1个向量](/chapters/深度学习/卷积神经网络/用反向传播算法求出梯度的1个向量.md)

### 强化学习

- 基本概念

	- [马尔可夫决策过程中的“智能体-环境”的交互模型](/chapters/强化学习/基本概念/马尔可夫决策过程中的“智能体-环境”的交互模型.md) | [策略的回报和最优策略的最优回报](/chapters/强化学习/基本概念/策略的回报和最优策略的最优回报.md)
	- [行动值函数(action-value-function)](/chapters/强化学习/基本概念/行动值函数(action-value-function).md) | [状态值函数(state-value-function)](/chapters/强化学习/基本概念/状态值函数(state-value-function).md) | [Bellman方程](/chapters/强化学习/基本概念/Bellman方程.md)

- 蒙特卡洛控制算法

	- [预测](/chapters/强化学习/基本概念/蒙特卡洛控制算法/预测.md) | [用Q-table评估](/chapterss/强化学习/基本概念/蒙特卡洛控制算法/用Q-table评估.md) | [用ε-greedy策略改进](/chapterss/强化学习/基本概念/蒙特卡洛控制算法/用ε-greedy策略改进.md) | [用constant-α控制](/chapterss/强化学习/基本概念/蒙特卡洛控制算法/用constant-α控制.md)

- 基本的时序差分控制方法

	- [Sarsa](/chapters/强化学习/基本的时序差分控制方法/Sarsa.md) | [Q-learning](/chapters/强化学习/基本的时序差分控制方法/Q-learning.md) | [Expected-Sarsa](/chapters/强化学习/基本的时序差分控制方法/Expected-Sarsa.md)

- Q-Learning的基本原理

	- [定义状态和行动并且设定奖励值的大小](/chapters/强化学习/Q-Learning的基本原理/定义状态和行动并且设定奖励值的大小.md) | [设置奖励矩阵R和Q-table矩阵Q](/chapters/强化学习/Q-Learning的基本原理/设置奖励矩阵R和Q-table矩阵Q.md)
	- [Q-table中数值的第1个运算过程](/chapters/强化学习/Q-Learning的基本原理/Q-table中数值的第1个运算过程.md) | [第2个运算过程](/chapters/强化学习/Q-Learning的基本原理/第2个运算过程.md) | [第3个运算过程](/chapters/强化学习/Q-Learning的基本原理/第3个运算过程.md) | [第4个运算过程](/chapters/强化学习/Q-Learning的基本原理/第4个运算过程.md) | [第5个运算过程](/chapters/强化学习/Q-Learning的基本原理/第5个运算过程.md)

### 机器学习

- 基本概念
	- [数据集中多个数据的Mean,Median,和Mode](/chapters/机器学习/基本概念/数据集中多个数据的Mean,Median,和Mode.md) | [数据集中多个数据的Standard Deviation和Variance](/chapters/机器学习/基本概念/数据集中多个数据的Standard_Deviation和Variance.md) | [数据集中多个数据的Percentile](/chapters/机器学习/基本概念/数据集中多个数据的Percentile.md)
	- [数据集中多个数据的(Normal) Data Distribution](/chapters/机器学习/基本概念/数据集中多个数据的(Normal)_Data_Distribution.md) | [数据集中多个数据的Scatter Plot](/chapters/机器学习/基本概念/数据集中多个数据的Scatter_Plot.m)
	- [用Linear Regression找出不同类型的数据间的相互关系](/chapters/机器学习/基本概念/用Linear_Regression找出不同类型的数据间的相互关系.md) | [用Polynomial Regression找出不同类型的数据间的相互关系](/chapters/机器学习/基本概念/用Polynomial_Regression找出不同类型的数据间的相互关系.md) | [用Multiple Regression找出不同类型的数据间的相互关系](/chapters/机器学习/基本概念/用Multiple_Regression找出不同类型的数据间的相互关系.md) 
	- [用Scale找出不同类型的数据间的相互关系](/chapters/机器学习/基本概念/用Scale找出不同类型的数据间的相互关系.md)
	- [用Train/Test的方法评估机器学习模型](/chapters/机器学习/基本概念/用Train_Test的方法评估机器学习模型.md)
	- [体验决策树](/chapters/机器学习/基本概念/体验决策树.md)

- 遗传算法
/机器学习/遗传算法/
	- [在线体验求解函数式的极值 (Hold,未来代码重构)](/chapters/机器学习/遗传算法/在线体验求解函数式的极值.md)
	- [定义评价函数](/chapters/机器学习/遗传算法/定义评价函数.md) | [随机生成种群](/chapters/机器学习/遗传算法/随机生成种群.md) | [二进制与十进制的相互映射](/chapters/机器学习/遗传算法/二进制与十进制的相互映射.md) | [适应度函数](/chapters/机器学习/遗传算法/适应度函数.md)
	- [选择](/chapters/机器学习/遗传算法/选择.md) | [交叉](/chapters/机器学习/遗传算法/.md) | [变异](/chapters/机器学习/遗传算法/变异.md)

### 附录

- **用NumPy操作矩阵及进行基本运算等**
	- [生成随机数](/chapters/附录/生成随机数.md) | [用arange()创建等差数组](/chapters/附录/用arange()创建等差数组.md)
	- [两个向量的数量积(内积)](/chapters/附录/两个向量的数量积(内积).md) | [矩阵乘法](/chapters/附录/矩阵乘法.md)
	 
- **在线体验导数/正态分布/最小平方法等**
	- [计算偏导数](/chapters/附录/计算偏导数.md) | [在Excel里生成正态分布的随机数(Wait)](/chapters/附录/在Excel里生成正态分布的随机数.md)
	- [用Matplotlib绘出Step function (Hold,未来代码重构)](/chapters/附录/Step_function.md)
	- [用Matplotlib绘出最小平方法的线性拟合 (Hold,未来代码重构)](/chapters/附录/用Matplotlib绘出最小平方法的线性拟合.md)
	- [通过最小平方法的线性拟合体验Cost funciton(Wait)](/chapters/附录/通过最小平方法的线性拟合体验Cost_funciton.md)

- **Sigmoid function**
	- [在坐标纸上手绘出大致的曲线](/chapters/附录/Sigmoid_function/在坐标纸上手绘出大致的曲线.md) | [使用NumPy调试的代码](/chapters/附录/Sigmoid_function/使用NumPy调试代码.md)
	- [在online的Jupyter Notebook上使用Matplotlib绘出的曲线](/chapters/附录/Sigmoid_function/在online的JupyterNotebook上使用Matplotlib绘出曲线.md)

- **其它**
	- [使用蒙特卡罗方法计算圆周率近似值等](/chapters/附录/使用蒙特卡罗方法计算圆周率近似值等.md)

