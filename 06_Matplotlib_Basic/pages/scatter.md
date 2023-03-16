---
layout: center
---

# 散点图

---


# 散点图

## 使用`plt.plot`画散点图

```python
from matplotlib import pyplot as plt
import numpy as np 

x = np.linspace(0, 10, 30)
y = np.sin(x)

plt.plot(x, y, 'o', color='black')

plt.show()
```

---

<img src = "/scatter_01.png" class = "h-90 mx-auto">

---

`plot`支持不同散点的类型，如下案例所示。详细说明请看[MarkrStyle](https://matplotlib.org/stable/api/_as_gen/matplotlib.markers.MarkerStyle.html)说明文档。

<img src = "/marks.png" class = "h-40 mx-auto">

```python
from matplotlib import pyplot as plt
import numpy as np 

rng = np.random.RandomState(0)
for marker in ['.', ',', 'o', 'v', '^', '<', '>', '1', '2', '3', '4', '8', 's', 'p', '*', 'h', 'H', '+', 'x',  'D', 'd', '|', '_', 'P', 'X']:
    plt.plot(rng.rand(10), rng.rand(10), marker,
             label="marker='{0}'".format(marker))
plt.legend(numpoints=1)
plt.xlim(0, 1.8)

plt.show()
```

---

<img src = "/scatter_02.png" class = "h-90 mx-auto">

---

# 使用`plt.scatter`画散点图

```python
from matplotlib import pyplot as plt
import numpy as np 

x = np.linspace(0, 10, 30)
y = np.sin(x)

plt.scatter(x, y, marker='o')

plt.show()
```

---


<img src = "/scatter_03.png" class = "h-90 mx-auto">

---

## 不同散点类型

`plt.scatter`支持不同散点的类型，如下案例所示。详细说明请看[MarkrStyle](https://matplotlib.org/stable/api/_as_gen/matplotlib.markers.MarkerStyle.html)说明文档。

```python
from matplotlib import pyplot as plt
import numpy as np 

rng = np.random.RandomState(0)
for marker in ['.', ',', 'o', 'v', '^', '<', '>', '1', '2', '3', '4', '8', 's', 'p', '*', 'h', 'H', '+', 'x',  'D', 'd', '|', '_', 'P', 'X']:
    plt.plot(rng.rand(10), rng.rand(10), marker,
             label="marker='{0}'".format(marker))
plt.legend(numpoints=1)
plt.xlim(0, 1.8)

plt.show()
```

---

<img src = "/scatter_04.png" class = "h-90 mx-auto">

---

## 点的透明度

`plt.scatter`和`plt.plot`的主要区别在于，`plt.scatter`可以针对每个点设置不同属性（大小、填充颜色、边缘颜色等），还可以通过数据集合对这些属性进行设置。

让我们通过一个随机值数据集绘制不同颜色和大小的散点图来说明。为了更好的查看重叠的结果，我们还使用了alpha关键字参数对点的透明度进行了调整：

```python
from matplotlib import pyplot as plt
import numpy as np 

rng = np.random.RandomState(0)
x = rng.randn(100)
y = rng.randn(100)
colors = rng.rand(100)
sizes = 1000 * rng.rand(100)

plt.scatter(x, y, c=colors, s=sizes, alpha=0.3,
            cmap='viridis')
plt.colorbar()  # 显示颜色对比条

plt.show()
```

---

<img src = "/scatter_05.png" class = "h-90 mx-auto">

---

## 点的大小
`plt.scatter`函数中可选参数“s”用于增加 matplotlib 中散点的大小。

```python
import matplotlib.pyplot as plt
import numpy as np
  
x = [1,2,3,4,5,6,7,8,9,10,11,12]
y = [1,2,3,4,5,6,7,8,9,10,11,12]
points_size = [100,200,300,400,500,600,700,800,900,1000,1100,1200]
  
plt.xticks(np.arange(13))
plt.yticks(np.arange(13))
  
plt.scatter(x, y, s=points_size, c='g')
  
plt.title("Scatter Plot with increase in size of scatter points ", fontsize=22)
  
plt.xlabel('x-axis', fontsize=20)
plt.ylabel('y-axis', fontsize=20)
  
plt.show()
```

---

<img src = "/scatter_06.png" class = "h-90 mx-auto">

---

# `plot` 和 `scatter` 对比

性能提醒除了上面说的`plt.plot`和`plt.scatter`对于每个散点不同属性的支持不同之外，还有别的因素影响对这两个函数的选择吗？对于小的数据集来说，两者并无差别，当数据集增长到几千个点时，`plt.plot`会明显比`plt.scatter`的性能要高。造成这个差异的原因是`plt.scatter`支持每个点使用不同的大小和颜色，因此渲染每个点时需要完成更多额外的工作。而`plt.plot`来说，每个点都是简单的复制另一个点产生，因此对于整个数据集来说，确定每个点的展示属性的工作仅需要进行一次即可。对于很大的数据集来说，这个差异会导致两者性能的巨大区别，因此，对于大数据集应该优先使用`plt.plot`函数。