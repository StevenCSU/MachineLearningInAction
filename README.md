# MachineLearningInAction
# 机器学习实战
## Ch02. k-近邻算法

### k-近邻算法概述
简单的说，k-近邻算法采用测量不同特征值之间的距离方法进行分类

**优点：** 精度高、对异常值不敏感、无数据输入假定

**缺点：** 计算复杂度高、空间复杂度高

**适用数据范围：** 数值型和标称型

工作原理：存在一个样本数据集合，也称作样本数据集，并且样本集中每个数据都存在标签，即我们知道样本集中每一数据与所属分类的对应关系。输入没有标签的新数据后，将新数据的每个特征与样本集中数据对应的特征进行比较，然后算法提取样本中集中特征最相似数据（最近邻）的分类标签。一般来说，我们只选择样本数据集中前k个最相似的数据，这就是k-近邻算法中k的出处，通常k是不大于20的整数。


## 决策树的构造
**优点：计算复杂度不高，输出结果易于理解，对中间值的缺失不敏感，可以处理不想关特征数据。**

**缺点：可能会产生过度匹配问题。**

**适用数据类型：数值型和标称型**

创建分支的伪代码函数createBranch():
```
if so return 类标签
Else
    寻找划分数据集的最好特征
    划分数据集
    创建分支节点
        for 每个划分的子集
            调用函数creatBranch并增加返回结果到分支节点中
    return 分支节点
```

_决策树的一般流程_
1.收集数据：可以使用任何方法。
2.准备数据：树构造算法只适用于标称型数据，因此数值型数据必须离散化。
3.分析数据：可以使用任何方法，构造树完成之后，我们应该检查图形是否符合预期。
4.训练算法：构造树的数据结构。
5.测试算法：使用经验树计算错误率。
6.使用算法：此步骤可以适用于任何监督学习算法，而使用决策树可以更好地理解数据的内在含义。

> 划分数据集的大原则是：将无序的数据变得更加有序
