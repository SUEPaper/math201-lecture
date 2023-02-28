---
layout: center
---

# 多子图

---

# 图形窗口的分割

matplotlib.pyplot.subplot 方法

该subplot()函数采用三个参数来描述图窗的布局。布局按行和列组织，由第一个 和第二个参数表示。第三个参数表示当前图的索引

<div class="overflow-auto h-xs">

```py

import matplotlib.pyplot as plt
import numpy as np

plt.rcParams["font.sans-serif"]=["SimHei"] #设置字体
plt.rcParams["axes.unicode_minus"]=False #该语句解决图像中的“-”负号的乱码问题


t = np.arange(0.1, 2 * np.pi, 0.01)
y = np.sin(t ** 2)

plt.subplot(2,2,1)
plt.plot(t, y, linewidth = 2, color = "blue")
plt.title("sin")

theta = np.linspace(0, 2*np.pi, 200)# 参数离散取点
x0 = 2
y0 = 1 # 椭圆中心
a = 2
b = 1 # 椭圆长短轴半径
x = x0 + a * np.cos(theta)
y = y0 + b * np.sin(theta)

plt.subplot(2,2,2)
plt.plot(x, y, linewidth = 2, color = "red")
plt.title("椭圆") # 子图标题

x = np.linspace(1, 0.01, 5)
y = np.exp(x)

plt.subplot(2,2,3)
plt.plot(x, y, linewidth = 2)
plt.title("exp")

x = np.linspace(1, 0.1, 10)
y = np.sqrt(x)

plt.subplot(2,2,4)
plt.plot(x, y, linewidth = 2)
plt.title("sqrt")

plt.suptitle("分窗口绘制子图")#图的总标题

plt.show()

```
</div>

---

# 多子图
例：

<img src = "/matplotlib_04.png" class = "h-90 mx-auto">
