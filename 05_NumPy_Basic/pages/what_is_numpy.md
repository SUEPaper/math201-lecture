---
layout: center
---

# 1. 简介与安装


NumPy(Numerical Python 的简称)提供了高效存储和操作密集数据缓存的接口。在某些方面，NumPy数组与Python内置的列表类型非常相似。但是随着数组在维度上变大，NumPy数组提供了更加高效的存储和数据操作。NumPy数组几乎是整个Python数据科学工具生态系统的核心。因此，不管你对数据科学的哪个方面感兴趣，花点时间学习如何有效地使用NumPy都是非常值得的。

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

<img src = "/numpy-02.png" class = "h-90 mx-auto">

---
layout: center
---

除此之外，numpy数组还具有以下特点：

1. 更紧凑，高维时尤为明显
2. 向量化后运算速度比列表更快
3. 在末尾添加元素时不如列表高效
4. 元素类型一般比较固定


