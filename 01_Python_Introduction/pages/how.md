---
layout: center
---

# (How)怎么学“任何东西”？

---
layout: full
transition: slide-up
---

# 数值计算实训课绝大部分同学来说并不轻松

不仅需要学习很多新知识, 在新环境中使用新工具

还需要锻炼出**独立解决问题的意识和能力**

更重要的是, **完成观念和心态上的转变**

<v-clicks>

* 我们与传统的课程大作业不同
   * 需要自学很多东西
   * 需要自学LaTeX，提交LaTeX报告（**一个数学系的学生不会LaTeX应该感到羞耻**）

<br/>

* 你遇到的所有问题(除了框架代码自身错误), 都是在锻炼你的能力
    * 老师助教不会手把手帮你解决所有问题
    * 独立解决这些问题, 是对你最大的训练

</v-clicks>

---
layout: full
transition: slide-up
---

# 专业世界观1 - 学术诚信

<b text-sky font-900> [MIT对学术诚信的诠释](https://integrity.mit.edu/) </b>,   尤其是<b text-sky font-900>[关于写代码的学术诚信](http://integrity.mit.edu/handbook/writing-code) </b>

<v-clicks>

* <b text-orange>独立完成学习任务</b>
* <b text-orange>在允许的范围内参考相关资料</b>
* <b text-orange>不参考别人的代码, 不分享自己的代码</b>

</v-clicks>

<v-click>

意义: 让你接受预期的训练, 锻炼出预期的能力

**这是需要大家发自内心去认可和执行的**: 我们很难约束大家

</v-click>

<v-click>

“凭什么不能参考别人的代码? 我都看懂了啊!”/“能抄对也是本事”

* <b text-red>“看懂”和 “自己独立完成”的效果是天差地别的</b>
    * 你表面上看到了做y能得到x, 但不知道原因z, 更不知道试错的uvw
    * 你收获了肤浅的理解, 让你重做一遍, 很可能还是搞不定

</v-click>

---
layout: full
transition: slide-up
---

# 专业世界观2 - 大佬三连

<v-clicks>

<b text-orange font-900> STFW - Search The Friendly Web </b>

* 只要我用的工具是大众的, 我几乎不可能是世界上第一个遇到问题的人
* 网上一定有人遇到过相同/类似问题, 我应该搜一下看看他们怎么解决

<br/>

<b text-orange font-900> RTFM - Read The Friendly Manual </b>

* 只要我用的工具是大众的, 应该有手册记录这个工具的所有细节
* 如果我想了解它的某个问题, 我应该去搜索手册的描述

<br/>

<b text-orange font-900> RTFSC - Read The Friendly Source Code </b>

* 只要我获得了项目代码, 理论上我就可以知晓它的一切行为
* 如果我想了解它具体是如何工作的, 我应该去读一下(关键)代码

<br/>

如果你在提问时收到了这些回复, 其背后的含义是:

* **你想要的答案很容易找到, 你很应该自己去获取**
* **相比于我直接告诉你答案, 你自己获取答案能学到更多**

</v-clicks>

---
layout: full
transition: slide-up
---

# 专业世界观3 - 科学提问
《[提问的智慧](https://github.com/ryanhanwu/How-To-Ask-Questions-The-Smart-Way/blob/main/README-zh_CN.md)》/《[别像弱智一样提问](https://github.com/tangx/Stop-Ask-Questions-The-Stupid-Ways/blob/master/README.md)》

* 提问能反映出你的学习态度: 主动尝试 vs. 被动依赖

**不是所有问题都值得问**

* 你以为自己热爱学习? 不, 别人只觉得你是伸手党

开源社区中的一个真实案例:

* 新手的提问: 两个不同的安装包有什么区别? <b text-sky font-900>我是新手</b>.
* 开发者的回答: **自己上网找答案**. 在开源社区中**不应该随便问这种配置问题**, 除非你有明确的证据证明代码或者文档有缺陷.

---
layout: full
transition: slide-up
---

# 鼓励的提问 vs. 不应该的提问

* 鼓励的提问
    * 心理辅导, 学习困惑等非具体技术问题
        * 可以私戳老师助教, 时间充裕的话还可以线上聊聊
    * bug report: 要有证据, 当一名专业的社区contributor
    * 经过思考的高质量问题
    * 属于训练环节, 但经历过合理尝试还无法解决的问题: [提问模板](https://ysyx.oscc.cc/docs/misc/ask.html)

<br>

* 不应该的提问 (背后含义: **你应该接受训练**)
    * 没有看出合理尝试和思考的提问
        * 可以不知道怎么尝试和思考, 但不代表可以跳过训练获得答案
        * 接受训练: 方法 -> 看讲义总结归纳, 细节 -> RTFM/RTFSC
    * 自己动手试试就能得到答案的提问


---
layout: full
transition: slide-up
---

# 虚假的帮助 vs. 真实的帮助

虚假的帮助: 面向结果, 解决当下问题优先

真实的帮助: 面向能力, 领悟学习方法优先

**本质区别: 如果将来不再提供帮助, 学生能否独立解决类似的问题?**

真实案例: 学生A询问某报错信息

* 分析: 根据提问内容, 学生A只进行了很少的尝试, 没有其他想法
* 虚假的帮助: 学生B指出可能是代码里面有些模块有bug, 提示学生A去看看
    * 学生A的收获是 “报错信息->something error”的表面因果关系, 难以深入理解和记忆, 并未学会真正思路和方法, 同时也错过一次锻炼机会
* 真实的帮助: 引导学生A学会对bug进行深入的分析和定位
    * **这比虚假的帮助困难得多, 大部分学生并不知道如何引导**

---
layout: full
transition: slide-up
---

# 任何直接获得答案的做法都是在放弃训练的机会

* 遇到一个总线的bug, 希望同学提供点思路
    * 正确做法: RTFM, 确认自己正确理解细节; RTFSC, 梳理这个bug是如何出现的

* 不知道算法应该放在哪里, 希望助教告知一个好的设计方案
    * 正确做法: 自己尝试不同的方案, 然后总结它们的优劣

* 希望助教/大佬能整理一本攻略手册
    * 正确做法: 自己整理(作为学习成果), 但不要分享出去
        * **这些攻略并不能真正帮助你学习, 而是在剥夺你接受训练的机会**

* 阅读开源项目或者别人的案例
    * 正确做法: 先尽力完成一个满意的设计, 再对比开源项目
        * **缺少试错, 你无法理解 “为什么好, 为什么不好”**

<b text-orange font-900> 躺平容易坚持难, 但如果你能坚持下来, 你就可以得到脱胎换骨的提升</b>

---
layout: full
transition: slide-up
---

# Prerequisistes

信息与计算科学专业学生必须具备的核心素质。

<v-clicks>

1. 是一个合格的计算机用户
    * 会STFW/RTFM自己动手解决问题
    * 不怕学习和使用任何可以提高效率的工具
        * Linux,VS Code,Python,git,...

2. 不怕写代码
    * 能管理一定规模(数千行)的代码
    * 能在出bug时默念“机器永远是对的、我肯定能调试出来的”
        * 然后开始用正确的工具/方法调试

</v-clicks>


---
layout: full
transition: slide-up
---

# 成为一名计算机的Power User

<br/>

感到 Linux/PowerShell/Python/git/...很难？

<v-clicks>

1. 没有建立信心、没有理解基本逻辑
    * [计算机科学自学指南](https://suepaper.github.io/math201/docs/notes/cs%E2%80%94roadmap)

<br/>

2. 没有找对材料/没有多问“**能不能再多做点什么**”
    * Baidu v.s. Google/Github/Stackoverflow v.s. ChatGPT

<br/>

3. 没有用对工具(该用VS Code就别用Vim/Emacs)
    * 过了入门阶段，都会好起来

</v-clicks>

---
layout: full
transition: slide-up
---

# 成为一名计算机的Power User

<br/>

<v-clicks>

* 如果一件事很困难，通常是因为没有找到正确的方法。

<br/>

* 这门课程中绝大部分的内容都可以在互联网上找到适当的学习资料。

<br/>

* 在互联网/搜索引擎普及的时代，只要掌握 “提出问题” 的能力，就能极快地提升自己。

<br/>

* 同时，这可能将在 AI 时代被颠覆——AI 可能会猜测你的目的，并且告诉你 “应该去做什么”。

</v-clicks>

---
layout: full
transition: slide-up
---

# 学会写代码

写代码 == 创造有趣的东西

* 命令行 + 编程语言就是全世界
    * 我们还有sympy, sage, z3, rich,...呢

<br/>
<br/>

<v-click>

* 不要讲语言特性、设计模式、......
    * 写代码就对了；你自然而然就会需要它们的，也就自然而然学会了。

</v-click>