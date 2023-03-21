---
# try also 'default' to start simple
# theme: seriph
theme: light-icons
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: true
# use UnoCSS
css: unocss
---

# vscode Python debug

Presentation slides for developers

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# What is debug

调试（英语：Debug）是发现和减少计算机程序或电子仪器设备中程序错误的一个过程。如果软件无法按预期工作，计算机程序员就会研究代码以确定发生错误的原因  

---

# why debug is important

计算机编程中会出现 bug 和错误，因为它是一种抽象的、概念性的活动。计算机以电子信号的形式处理数据。编程语言将这些信息抽象化，以便人类能够更有效地与计算机交互。任何类型的软件都有多个抽象层，不同的组件进行通信，以使应用程序正常工作。出现错误时，查找和解决问题可能很困难。调试工具和策略有助于更快地解决问题并提高开发人员的工作效率。因此，软件质量和最终用户体验都得到了改善

---

# how to debug Python

## 断点

断点（英语：Breakpoint）是程序中为了调试而故意停止或者暂停的地方。

调试设置断点可以让程序执行到该行程序时停住，借此观察程序到断点位置时，其变量、寄存器、I/O等相关的变量内容，有助于深入了解程序运作的机制，发现、排除程序错误的根源。

## 如何设置断点

1. 在行号的左侧单击
2. F9

---

# how to debug Python

## 进入调试

当设置好断点后，进入调试

## 如何进入

1. 右上角点击调试按钮
2. F5
   
---

# how to debug Python

## 工具栏

调试工具栏也将在此时可用。调试工具栏包含的按钮可让您前进、后退以及根据您当前在断点中的位置跳转到代码的不同部分。关于您的代码的元数据也将出现在VARIABLES(变量)面板中，您可以在其中观察和监视局部变量和全局变量的更改。

* __继续(F5)__ – 这将越过断点并继续执行程序的其余部分，直到遇到下一个断点。

* __Step over (F10)__ – 这将使调试器进入下一行。

* __进入 (F11)__ – 这将使调试器进入以下函数。

* __退出 (F12)__ – 这将使调试器退出函数并进入下一步。

* __重新启动 (Ctrl+shift+F5)__ – 重新启动整个调试器。

* __停止 (shift+F5)__ – 停止调试过程并退出。

---

# how to debug Python

## 案例

```py
def jiecheng(num):
    ans = 1
    for i in range(num):
        ans = ans * i
    return ans

for i in range(5):
    print(jiechen(i))
```
此函数为阶乘的递归实现

---

# how to debug Python

## 案例

让我们运行我们的调试器，我们看到 'jiechen' 这个函数不存在。

![](/debug4.png)

发现原因为jiechen这个函数没有定义,为拼写错误

---

正常拼写后再次调试，出现错误，1的阶乘为0。

<img src = "/debug6.png" class = "h-100 mx-auto">

---

设置断点，继续调试，发现此时的i为0，因为range(num)会生成是从0到num-1，所以设置为range(1,num+1)使得其生成1到num

<img src = "/debug7.png" class = "h-100 mx-auto">

---

结果输出正确

<img src = "/debug8.png" class = "h-100 mx-auto">





