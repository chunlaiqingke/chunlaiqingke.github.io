# P7 损失函数
Loss : 单个样本的方差 1/2(y^ - y)^2
Cost J(w,b) : m个样本的方差
逻辑回归的Loss不是普通的差方，而是-(yilogyi - (1-yi)log(1-yi))
因为逻辑回归这样才能是个凸函数，否则不是凸函数，很难达到全局最优解


# P8 梯度下降
repeat w = w - a dJ/dw   b = b - a dj/db

# P11 计算图
J= 3(a + bc)
U=bc, V = a+U, J = 3V
计算图：反映了网络的原始结构，正向传播和反向传播的过程

# P19 python中的矩阵广播
B = np.array([[1,2,3],
            [4,5,6]])
C = np.array([100, 101, 102])

B + C
结果：
array([[101, 103, 105],
[104, 106, 108]])

# P20 python中使用numpy的一些技巧
不要使用(5,)这种秩为1的向量
建议使用(5, 1)这种张量的形式
可以使用reshape方法进行转换

# P26 多个例子中的向量化
为什么神经网络的每个神经元的计算都是使用逻辑回归

# P28 激活函数
选择激活函数的法则
#### sigmoid函数：0- 1的输出
#### tanh函数： 一般情况比较优
#### ReLu的缺点：小于0 的时候导数是0，Leaky ReLu 效果要好点，但是实际使用的频率不太高
* 如果输出 0 - 1 之间， 而且是二分类，选择sigmoid函数，然后其他所有单元都用ReLU，修正线性单元，如果不确定隐藏层用什么激活函数，使用ReLu
* ReLU比tanh和sigmoid要快的多，因为ReLU没有函数接近0时减慢学习速率

# P29 为什么需要非线性激活函数
如果没有非线性激活函数，整个网络就可以表示成了一个线性函数，隐藏层就可以不需要了，表示不了复杂的函数形式，覆盖不了所有的业务。
只有当解决回归问题的时候才可以不需要非线性激活函数