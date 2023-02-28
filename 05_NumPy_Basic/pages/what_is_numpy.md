---
layout: center
---

# 1. 简介与安装

本文参考: 

1. [NumPy Illustrated: The Visual Guide to NumPy](https://betterprogramming.pub/numpy-illustrated-the-visual-guide-to-numpy-3b1d4976de1d)
2. [A Visual Intro to NumPy and Data Representation](https://jalammar.github.io/visual-numpy/)
3. [《Python Data Science Handbook》](https://www.oreilly.com/library/view/python-data-science/9781491912126/)

NumPy(Numerical Python 的简称)提供了高效存储和操作密集数据缓存的接口。在某些方面，NumPy数组与Python内置的列表类型非常相似。但是随着数组在维度上变大，NumPy数组提供了更加高效的存储和数据操作。NumPy数组几乎是整个Python数据科学工具生态系统的核心。因此，不管你对数据科学的哪个方面感兴趣，花点时间学习如何有效地使用NumPy都是非常值得的。

<!-- ---
layout: center -->
---

# 1. NumPy 速查手册
<!-- <img src = "matplotlib_02.svg" class = "h-90 mx-auto"> -->

<!-- ---
layout: center -->
---

# 2. 安装
```bash showLineNumbers
pip install numpy
```

# 3. 使用

```python showLineNumbers
import numpy as np

a = np.array([1, 2, 3])
print(a)
```
```
[1 2 3]
```

---

# 4. NumPy数组 vs Python 列表

乍看上去，NumPy数组与Python列表极其相似。它们都用来装载数据，都能够快速添加或获取元素，插入和移除元素则比较慢。

当然相比python列表，numpy数组可以直接进行算术运算：

---

![](./public/numpy-02.png)

---
layout: center
---

除此之外，numpy数组还具有以下特点：

1. 更紧凑，高维时尤为明显
2. 向量化后运算速度比列表更快
3. 在末尾添加元素时不如列表高效
4. 元素类型一般比较固定
   
---

<!-- ![](./img/numpy-03.png) -->

---

# 5. NumPy的数据类型

<font size = 2>

| Data type | Description |
|---------------|-------------|
| ``bool_``     | Boolean (True or False) stored as a byte |
| ``int_``      | Default integer type (same as C ``long``; normally either ``int64`` or ``int32``)|
| ``intc``      | Identical to C ``int`` (normally ``int32`` or ``int64``)|
| ``intp``      | Integer used for indexing (same as C ``ssize_t``; normally either ``int32`` or ``int64``)|
| ``int8``      | Byte (-128 to 127)|
| ``int16``     | Integer (-32768 to 32767)|
| ``int32``     | Integer (-2147483648 to 2147483647)|
| ``int64``     | Integer (-9223372036854775808 to 9223372036854775807)|
| ``uint8``     | Unsigned integer (0 to 255)|

</font>

---

<font size = 2>

| Data type | Description |
|---------------|-------------|
| ``uint16``    | Unsigned integer (0 to 65535)|
| ``uint32``    | Unsigned integer (0 to 4294967295)|
| ``uint64``    | Unsigned integer (0 to 18446744073709551615)|
| ``float_``    | Shorthand for ``float64``.|
| ``float16``   | Half precision float: sign bit, 5 bits exponent, 10 bits mantissa|
| ``float32``   | Single precision float: sign bit, 8 bits exponent, 23 bits mantissa|
| ``float64``   | Double precision float: sign bit, 11 bits exponent, 52 bits mantissa|
| ``complex_``  | Shorthand for ``complex128``.|
| ``complex64`` | Complex number, represented by two 32-bit floats|
| ``complex128``| Complex number, represented by two 64-bit floats|

</font>
