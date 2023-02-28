---
layout: center
---

# 2. 向量(Vector): 一维数组

本文参考: 

1. [NumPy Illustrated: The Visual Guide to NumPy](https://betterprogramming.pub/numpy-illustrated-the-visual-guide-to-numpy-3b1d4976de1d)
2. [A Visual Intro to NumPy and Data Representation](https://jalammar.github.io/visual-numpy/)
3. [《Python Data Science Handbook》](https://www.oreilly.com/library/view/python-data-science/9781491912126/)

向量在NumPy中用一维数组表示。

---

# 1. 向量初始化

通过Python列表可以创建NumPy数组，如下将列表元素转化为一维数组：
<img src = "numpy-04.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-04.png) -->

注意，确保列表元素类型相同，否则dtype=’object'，将影响运算甚至产生语法错误。

由于在数组末尾没有预留空间以快速添加新元素，NumPy数组无法像Python列表那样增长，因此，通常的做法是在变长Python列表中准备好数据，然后将其转换为NumPy数组，或是使用np.zeros或np.empty预先分配必要的空间：
<img src = "numpy-05.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-05.png) -->

通过以下方法可以创建一个与某一变量形状一致的空数组：
<img src = "numpy-07.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-07.png) -->

---

## 初始化
不止是空数组，通过上述方法还可以将数组填充为特定值：
<img src = "numpy-08.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-08.png) -->

---

## 初始化
在NumPy中，还可以通过单调序列初始化数组：
<img src = "numpy-09.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-09.png) -->

---

## 初始化
如果您需要[0., 1., 2.]这样的浮点数组，可以更改arange输出的类型，即arange(3).astype(float)，但有更好的方法：由于arange函数对类型敏感，因此参数为整数类型，它生成的也是整数类型，如果输入float类型arange(3.），则会生成浮点数。

---

## 初始化
arange浮点类型数据不是非常友好：
<img src = "numpy-10.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-10.png) -->

---

## 初始化
上图中，0.1对我们来说是一个有限的十进制数，但对计算机而言，它是一个二进制无穷小数，必须四舍五入为一个近似值。因此，将小数作为arange的步长可能导致一些错误。可以通过以下两种方式避免如上错误：一是使间隔末尾落入非整数步数，但这会降低可读性和可维护性；二是使用linspace，这样可以避免四舍五入的错误影响，并始终生成要求数量的元素。但使用linspace时尤其需要注意最后一个的数量参数设置，由于它计算点数量，而不是间隔数量，因此上图中数量参数是11，而不是10。

---

## 随机数
随机数组的生成如下：
<img src = "numpy-11.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-11.png) -->

---

## 随机数
There’s also a new interface for random arrays generation. It is:
- better suited for multi-threading,
- somewhat faster,
- more configurable (you can squeeze even more speed or even more quality by choosing a non-default so-called ‘bit generator’),
- able to pass two tricky synthetic tests that the old version fails.

---
<img src = "numpy-12.png" class = "h-90 mx-auto">

<!-- ![New-style random numbers generation](./img/numpy-12.png) -->

---

# 2.向量索引

对于数组数据的访问，numpy提供了便捷的访问方式：
<img src = "numpy-13.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-13.png) -->

---

## 切片操作
上图中，除“fancy indexing”外，其他所有索引方法本质上都是`views`：它们并不存储数据，如果原数组在被索引后发生更改，则会反映出原始数组中的更改。

上述所有这些方法都可以改变原始数组，即允许通过分配新值改变原数组的内容。这导致无法通过切片来复制数组：
<img src = "numpy-14.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-14.png) -->

---

## 切片操作
Also, such assignments must not change the size of the array, so tricks like
<img src = "numpy-15.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-15.png) -->
won’t work in NumPy — use np.insert, np.append, etc. instead (described in the “2D” section below).

---

## 布尔索引
此外，还可以通过布尔索引从NumPy数组中获取数据，这意味着可以使用各种逻辑运算符：
<img src = "numpy-16.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-16.png) -->

注意，不可以使用`3 <= a <= 5`这样的Python“三元”比较。

---

## 布尔索引
如上所述，布尔索引是可写的。如下图np.where和np.clip两个专有函数。
<img src = "numpy-17.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-17.png) -->

---

# 3.向量操作

NumPy的计算速度是其亮点之一，其向量运算操作接近C++级别，避免了Python循环耗时较多的问题。NumPy允许像普通数字一样操作整个数组：
<img src = "numpy-18.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-18.png) -->

---

## 浮点运算
浮点数的计算也是如此，numpy能够将标量广播到数组：
<img src = "numpy-19.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-19.png) -->

---

## 数学函数
numpy提供了许多数学函数来处理矢量：
<img src = "numpy-20.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-20.png) -->

---

## 向量运算
向量点乘（内积）和叉乘（外积、向量积）如下：
<img src = "numpy-21.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-21.png) -->

---

## 三角函数
numpy也提供了如下三角函数运算：
<img src = "numpy-22.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-22.png) -->

---

## 舍入
数组整体进行四舍五入：
<img src = "numpy-23.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-23.png) -->

1. floor向上取整 
2. ceil向下取整
3. round四舍五入

np.around与np.round是等效的，这样做只是为了避免 from numpy import *时与Python  aroun的冲突（但一般的使用方式是import numpy as np）。当然，你也可以使用a.round()。

---

## 最大最小值等
numpy还可以实现以下功能：
<img src = "numpy-24.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-24.png) -->

---

<!-- TODO: 不确定 -->
## 算数平均
As you can see from the formula above, both std and var ignore Bessel’s correction and give a biased result in the most typical use case of estimating std from a sample when the population mean is unknown. The standard approach to get a less biased estimation is to have n-1 in the denominator, which is done with ddof=1 (‘delta degrees of freedom’):
<img src = "numpy-25.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-25.png) -->

---

<!-- TODO: 不确定 -->
The effect of the Bessel’s correction quickly diminishes with increasing sample size. Also, it is not a one-size-fits-all solution, e.g. for the normal distribution ddof=1.5 is better:
<img src = "numpy-26.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-26.png) -->

---

# 排序
在numpy中，排序函数功能有所阉割：
<img src = "numpy-27.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-27.png) -->

对于一维数组，可以通过反转结果来解决reversed函数缺失的不足，但在2维数组中该问题变得棘手。

---

# 4.查找向量中的元素

不同于Python列表，NumPy数组没有索引方法。
<img src = "numpy-28.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-28.png) -->

<font size = 2>

- 可以通过`np.where(a==x)[0][0]`查找元素，但这种方法很不pythonic，哪怕需要查找的项在数组开头，该方法也需要遍历整个数组。
- 使用Numba实现加速查找，`next((i[0] for i, v in np.ndenumerate(a) if v==x), -1)`，在最坏的情况下，它的速度要比where慢。
- 如果数组是排好序的，使用`v = np.searchsorted(a, x); return v if a[v]==x else -1`时间复杂度为O(log N)，但在这之前，排序的时间复杂度为O(N log N)。

</font>

实际上，通过C实现加速搜索并不是困难，问题是浮点数据比较。

---

# 5.浮点数比较

np.allclose(a, b)用于容忍误差之内的浮点数比较。
<img src = "numpy-29.png" class = "h-90 mx-auto">

<!-- ![](./img/numpy-29.png) -->

- np.allclose假定所有比较数字的尺度为1。如果在纳秒级别上，则需要将默认atol参数除以1e9：`np.allclose(1e-9,2e-9, atol=1e-17)==False`。
- math.isclose不对要比较的数字做任何假设，而是需要用户提供一个合理的abs_tol值（np.allclose默认的atol值1e-8足以满足小数位数为1的浮点数比较，即`math.isclose(0.1+0.2–0.3, abs_tol=1e-8)==True`。

---

此外，对于绝队偏差和相对偏差，np.allclose依然存在一些问题。例如，对于某些值a、b， allclose(a,b)!=allclose(b,a)，而在math.isclose中则不存在这些问题。查看GitHub上的[浮点数据指南](https://floating-point-gui.de/errors/comparison/)和相应的[NumPy问题](https://github.com/numpy/numpy/issues/10161)了解更多信息。