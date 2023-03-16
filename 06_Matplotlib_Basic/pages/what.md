---
layout: center
---

# 什么是Matplotlib?

---
transition: fade-out
---

# 什么是Matplotlib?

Matplotlib是建立在NumPy数组基础上的多平台数据可视化程序库，最初被设计用于完善SciPy的生态环境。Matplotlib最重要的特性之一就是具有良好的操作系统兼容性和图形显示底层接口兼容性(graphics backend)。Matplotlib支持几十种图形显示接口与输出格式，这使得用户无论在哪种操作系统上都可以输出自己想要的图形格式。这种跨平台、面面俱到的特点已经成为Matplotlib最强大的功能之一，Matplotlib也因此吸引了大量用户，进而形成了一个活跃的开发者团队，晋升为Python科学领域不可或缺的强大武器。

## 安装

```bash
pip install matplotlib
```

---

# 语法

基本语法

画x和y, 默认是线图

```py
plot(x,y)
```

用于设置图像的名字

```python
plt.title()
```

用于设置X,Y轴的标签

```python
plt.xlabel()
plt.ylabel()
```

---

# 具体案例

在同一窗口绘制如下2条曲线，并加标注。

$y_1 = 2sinx,y_2 = 2cos(x^2),x \in [0,3\pi]$


<div class="overflow-auto h-xs">

```py

import matplotlib.pyplot as plt
import numpy as np

import matplotlib.pyplot as plt
plt.rcParams["font.sans-serif"]=["SimHei"] #设置字体
plt.rcParams["axes.unicode_minus"]=False #该语句解决图像中的“-”负号的乱码问题

a = 0
b = 3 * np.pi
N = 500
X = np.linspace(a,b,N)

Y1 = 2 * np.sin(X)
Y2 = np.cos(X**2)
plt.plot(X, Y1, linestyle = "-", linewidth = 2, color = "red")
plt.plot(X, Y2, linestyle = "--", linewidth = 2, color = "blue")
plt.xlabel("time")
plt.ylabel("振幅")
plt.legend(['y=2sin(x)','y=2cos(x^2)'],loc = "upper right")
plt.savefig("matplotlib_01.png")
plt.show()

```

</div>
---

# 图

<img src = "/matplotlib_01.png" class = "h-90 mx-auto">
