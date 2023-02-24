---
theme: unicorn
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
drawings:
  persist: True
# page transition
transition: slide-left
# use UnoCSS
css: unocss
---

# Matplotlib 基础

## 上海电力大学

数理学院数学系

#### 邓化宇

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/SUEPaper/math201-lecture/tree/main" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

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
plt.savefig("matplotlib_01.svg")
plt.show()

```

</div>

---

# 图

<img src = "matplotlib_01.svg" class = "h-90 mx-auto">

---

# 参数方程绘图：红心

参数方程

$$
    \begin{cases}
        x = 16sin^3(t)\\
        y = 13cos(t) - 5cos(2t) - 2cos(3t) -  cos(4t)
    \end{cases}
$$

<div class="overflow-auto h-xs">

```py

import matplotlib.pyplot as plt
import numpy as np

t = np.linspace(0, 2 * np.pi, 200)
x = 16 * np.sin(t) ** 3
y = 13 * np.cos(t) - 5 * np.cos(2 * t) - 2 * np.cos(3 * t) - np.cos(4 * t)
plt.plot(x,y,color = "red", linewidth = 1.5)

plt.show()

```

</div>

---


# 红心图

<img src = "matplotlib_02.svg" class = "h-90 mx-auto">

---

# 作业:绘制创意心

例：

<div class="overflow-auto h-xs">

```py

import matplotlib.pyplot as plt
import numpy as np

t = np.linspace(0, 2 * np.pi, 200)
x = 16 * np.sin(t) ** 3
y = 13 * np.cos(t) - 5 * np.cos(2 * t) - 2 * np.cos(3 * t) - np.cos(4 * t)
plt.plot(x, y, color = "red", linewidth = 1.5)
for scale in np.arange(0.2,0.8,0.2):
    plt.plot(scale * x, scale * y, color = "red", linewidth = 1.5)
# plt.plot(x + 8 , y, color = "red", linewidth = 1.5) # 向右平移
plt.plot(x, -y, color = "red", linewidth = 1.5)

plt.savefig("matplotlib_03.svg")
plt.show()

```
</div>

---

# 创意红心图

<img src = "matplotlib_03.svg" class = "h-90 mx-auto">

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

<img src = "matplotlib_04.svg" class = "h-90 mx-auto">

---

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

plt.savefig("matplotlib_05.svg")
plt.show()

```
</div>

---

# 3D螺旋线

<img src = "matplotlib_05.svg" class = "h-90 mx-auto">

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

<img src = "matplotlib_06.svg" class = "h-90 mx-auto">

---

# 其他种类绘图

详见：
[课程网站](https://suepaper.github.io/math201/docs/category/matplotlib%E6%95%99%E7%A8%8B)
[matplotlib官网](https://matplotlib.org/stable/index.html)
