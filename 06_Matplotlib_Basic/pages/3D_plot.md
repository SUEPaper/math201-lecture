# 3D图像
Matplotlib 可以支持绘制3D的图形，通过关键字参数projection='3d'来创建3D视图, 三维 axes 激活后，我们可以在上面绘制不同的三维图表类型。

<div class="overflow-auto h-xs">

```py

import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

plt.rcParams["font.sans-serif"]=["SimHei"] #设置字体
plt.rcParams["axes.unicode_minus"]=False #该语句解决图像中的“-”负号的乱码问题

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

t = np.arange(0, 8 * np.pi, 0.1)
X = np.sin(t)
Y = np.cos(t)
Z = t

ax.plot(X, Y, Z)
ax.set_title('绘制螺旋线')

ax.set_xlabel('sin(t)')
ax.set_ylabel('cos(t)')

plt.savefig("matplotlib_05.png")
plt.show()

```
</div>

---

# 3D螺旋线

<img src = "/matplotlib_05.png" class = "h-90 mx-auto">

---

# 三维曲面绘图

meshgrid()
首先是平面网格点的生成 函数命令meshgrid() 用来生成 x-y 平面上的网格点矩阵。 调用形式
为：X, Y = np.meshgrid(x, y)

<div class="overflow-auto h-xs">

```py

import matplotlib.pyplot as plt
import numpy as np

fig = plt.figure()
ax = fig.add_subplot(projection='3d')

def f(x, y):
    return np.sin(np.sqrt(x ** 2 + y ** 2))

x = np.linspace(-6, 6, 30)
y = np.linspace(-6, 6, 30)

X, Y = np.meshgrid(x, y)
Z = f(X, Y)

ax.contour3D(X, Y, Z, 50, cmap='binary')
ax.set_xlabel('x')
ax.set_ylabel('y')
ax.set_zlabel('z')

plt.show()

```
</div>

---

# 三维曲面图

<img src = "/matplotlib_06.png" class = "h-90 mx-auto">

---
