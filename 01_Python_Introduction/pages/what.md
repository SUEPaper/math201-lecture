---
transition: slide-up
layout: center
---

# 什么是数值计算？

---
layout: full
transition: slide-up
---

# 解析解 与 数值解

#### 解析解： 如果一个方程或者方程组存在的某些解，是由有限次常见运算的组合给出的形式，则称该方程存在解析解。

典型案例：

$$
x^2 + px - q = 0
$$

$$
x = \frac{\sqrt{p^2 + 4q} -p}{2}
$$

<br/>

#### 数值解：是指给出一系列对应的自变量，采用数值方法求出的解。采用的方法有限元法、数值逼近、插值法。

---
layout: full
transition: slide-left
---
# 简单理解的方式

- Analytical solutions can be obtained exactly with pencil and paper;

<br/>

- Numerical solutions cannot be obtained exactly in finite time and typically cannot be solved using pencil and paper.

## 案例

Find the root of  $f(x)=x-5$

Analytical soluation:

$f(x)=x-5=0$, add $+5$ to both sides to get the answer $x = 5$

Numerical solution:

1. Let's guess $x=1: f(1)=1-5=-4$. A negative number. 
2. Let's guess $x=6: f(6)=6-5=1$. A positive number.
3. The answer must be between them. Let's try $x=\frac{6+1}{2}: f(\frac{7}{2})<0$.
4. So it must be between $\frac{7}{2}$ and 6 ..etc.

This is called bisection method.

---
transition: slide-left
layout: center
---

# 为什么要用数值分析？


---
transition: slide-up
---
# 原因

1. 大多数方程无法得到解析解，尤其是偏微分方程。

<br/>

2. 人类历史上最伟大的发明诞生了。

<v-click>

<img src = "/Eniac.jpg" class = "h-90 mx-auto">

</v-click>

---
layout: full
transition: slide-up
---
# Coding

因此你们不仅要学数值计算方法，更重要的是要让计算机去帮你们求解方程的数值解。

所以需要解锁你们潜藏在内心的编程的洪荒之力，让计算机来帮你们去干重复性工作，而且它还不会出错（除非你代码写错了）。

<img src = "/python-code.webp" class = "h-90 mx-auto">

---
layout: center
transition: slide-up
---

# 解个方程的解而已，有啥用呢？

---
layout: full
transition: slide-up
---

# 人工智能

<img src = "/ChatGPT.png" class = "h-90 mx-auto">

ChatGPT镜像站点列表：https://github.com/xx025/carrot

---
layout: full
transition: slide-up
---

# 动画

<Youtube id="mvRTLP0aQNw" width="720" height="1080"/>

---
layout: full
transition: slide-up
---

# 游戏

<Youtube id="LamMQ47ccdc" width="720" height="1080"/>

---
layout: full
transition: slide-up
---

# CAE

<img src = "/cae.jpg" class = "h-90 mx-auto">

---
layout: full
transition: slide-left
---

# 卡脖子技术

<img src = "/chip.webp" class = "h-90 mx-auto">
