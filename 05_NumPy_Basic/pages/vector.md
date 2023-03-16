---
layout: center
---

# 2. 向量(Vector): 一维数组

---

# 1. 向量初始化

通过Python列表可以创建NumPy数组，如下将列表元素转化为一维数组：
<img src = "/numpy-04.png" class = "h-20 mx-auto">

注意，确保列表元素类型相同，否则dtype=’object'，将影响运算甚至产生语法错误。

由于在数组末尾没有预留空间以快速添加新元素，NumPy数组无法像Python列表那样增长，因此，通常的做法是在变长Python列表中准备好数据，然后将其转换为NumPy数组，或是使用np.zeros或np.empty预先分配必要的空间：
<img src = "/numpy-05.png" class = "h-20 mx-auto">

通过以下方法可以创建一个与某一变量形状一致的空数组：
<img src = "/numpy-07.png" class = "h-20 mx-auto">


---

## 初始化
不止是空数组，通过上述方法还可以将数组填充为特定值：
<img src = "/numpy-08.png" class = "h-90 mx-auto">


---

## 初始化
在NumPy中，还可以通过单调序列初始化数组：
<img src = "/numpy-09.png" class = "h-90 mx-auto">


---

## 初始化
如果您需要[0., 1., 2.]这样的浮点数组，可以更改arange输出的类型，即arange(3).astype(float)，但有更好的方法：由于arange函数对类型敏感，因此参数为整数类型，它生成的也是整数类型，如果输入float类型arange(3.），则会生成浮点数。

---

## 初始化
arange浮点类型数据不是非常友好：
<img src = "/numpy-10.png" class = "h-90 mx-auto">

---

## 初始化
上图中，0.1对我们来说是一个有限的十进制数，但对计算机而言，它是一个二进制无穷小数，必须四舍五入为一个近似值。因此，将小数作为arange的步长可能导致一些错误。可以通过以下两种方式避免如上错误：一是使间隔末尾落入非整数步数，但这会降低可读性和可维护性；二是使用linspace，这样可以避免四舍五入的错误影响，并始终生成要求数量的元素。但使用linspace时尤其需要注意最后一个的数量参数设置，由于它计算点数量，而不是间隔数量，因此上图中数量参数是11，而不是10。

---
<img src = "/numpy-12.png" class = "h-90 mx-auto">
---

# 2.向量索引

对于数组数据的访问，numpy提供了便捷的访问方式：
<img src = "/numpy-13.png" class = "h-90 mx-auto">


---

## 切片操作
上图中，除“fancy indexing”外，其他所有索引方法本质上都是`views`：它们并不存储数据，如果原数组在被索引后发生更改，则会反映出原始数组中的更改。

上述所有这些方法都可以改变原始数组，即允许通过分配新值改变原数组的内容。这导致无法通过切片来复制数组：
<img src = "/numpy-14.png" class = "h-50 mx-auto">


---

## 切片操作
Also, such assignments must not change the size of the array, so tricks like
<img src = "/numpy-15.png" class = "h-50 mx-auto">

<!-- ![](./img/numpy-15.png) -->
won’t work in NumPy — use np.insert, np.append, etc. instead (described in the “2D” section below).

---

## 布尔索引
此外，还可以通过布尔索引从NumPy数组中获取数据，这意味着可以使用各种逻辑运算符：
<img src = "/numpy-16.png" class = "h-70 mx-auto">

<!-- ![](./img/numpy-16.png) -->

注意，不可以使用`3 <= a <= 5`这样的Python“三元”比较。

---

## 布尔索引
如上所述，布尔索引是可写的。如下图np.where和np.clip两个专有函数。
<img src = "/numpy-17.png" class = "h-80 mx-auto">

<!-- ![](./img/numpy-17.png) -->

---

# 3.向量操作

NumPy的计算速度是其亮点之一，其向量运算操作接近C++级别，避免了Python循环耗时较多的问题。NumPy允许像普通数字一样操作整个数组：
<img src = "/numpy-18.png" class = "h-80 mx-auto">

<!-- ![](./img/numpy-18.png) -->

---

## 浮点运算
浮点数的计算也是如此，numpy能够将标量广播到数组：
<img src = "/numpy-19.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-19.png) -->

---

## 数学函数
numpy提供了许多数学函数来处理矢量：
<img src = "/numpy-20.png" class = "h-70 mx-auto">

<!-- ![](./img/numpy-20.png) -->

---

## 向量运算
向量点乘（内积）和叉乘（外积、向量积）如下：
<img src = "/numpy-21.png" class = "h-60 mx-auto">

<!-- ![](./img/numpy-21.png) -->

---

## 三角函数
numpy也提供了如下三角函数运算：
<img src = "/numpy-22.png" class = "h-70 mx-auto">

<!-- ![](./img/numpy-22.png) -->

---

## 舍入
数组整体进行四舍五入：
<img src = "/numpy-23.png" class = "h-50 mx-auto">

<!-- ![](./img/numpy-23.png) -->

1. floor向上取整 
2. ceil向下取整
3. round四舍五入

np.around与np.round是等效的，这样做只是为了避免 from numpy import *时与Python  aroun的冲突（但一般的使用方式是import numpy as np）。当然，你也可以使用a.round()。

---

## 最大最小值等
numpy还可以实现以下功能：
<img src = "/numpy-24.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-24.png) -->

---

<!-- TODO: 不确定 -->
## 算数平均
As you can see from the formula above, both std and var ignore Bessel’s correction and give a biased result in the most typical use case of estimating std from a sample when the population mean is unknown. The standard approach to get a less biased estimation is to have n-1 in the denominator, which is done with ddof=1 (‘delta degrees of freedom’):
<img src = "/numpy-25.png" class = "h-70 mx-auto">

<!-- ![](./img/numpy-25.png) -->

---

