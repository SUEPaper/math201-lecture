---
layout: center
---

# 参数方程绘图

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

<img src = "matplotlib_02.png" class = "h-90 mx-auto">

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

plt.savefig("matplotlib_03.png")
plt.show()

```
</div>

---

# 创意红心图

<img src = "matplotlib_03.png" class = "h-90 mx-auto">
