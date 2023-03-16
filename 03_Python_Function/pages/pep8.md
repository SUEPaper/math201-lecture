---
layout: center
---

# PEP8

---
layout: full
---

# PEP8 简介

PEP8(Style Guide for Python Code)是一份关于Python编码规范指南, 遵循该规范能够帮助Python开发者编写出优雅的代码, 提高代码的可读性, 同时提高团队合作时的开发效率。

链接地址：https://peps.python.org/pep-0008/

请记住**代码是写给人看的，不是写给机器看的**, 只是顺便让计算机可以执行而已。

---
layout: full
---

# 空格

- 避免使用无关的空格，包括空格内、逗号分号前面等
- 避免在行末使用空格
- 二元运算符在两侧使用一个空格
- 当用于指示关键字参数或默认参数值时，不要在=符号周围使用空格

<br/>

```py
a = f(1, 2) + g(3, 4) # good
a = f( 1, 2 ) + g( 3, 4 ) # bad
```

---
layout: full
---

# 命名规范

- 命名应该反应其用途而非实现
- `snake_case` 用于变量名/函数名
- `CamelCase` 用于类名
- `CAPS_CASE` 用于常量名

---
layout: full
---

# 缩进

- 每一级缩进使用4个空格。
- 续行应该与其包裹元素对其。
- 每行最多79个字符

推荐： 
```py
# 与左括号对齐  
fo = dict(name='小数先生', age=18, 
          gender='男',city='hangzhou') 
          
# 用更多的缩进来与其他行区分  
def long_function_name( 
        var_noe, var_two, 
        var_three, var_four): 
    print(var_one)
```

不推荐：

```py
fo = dict(name='小数先生', age=18, 
    gender='男',city='hangzhou')

def long_function_name( 
    var_noe, var_two, 
    var_three, var_four): 
    print(var_one)
```

---
layout: full
---

# 注释

- 代码更改时，相应的注释也要随之高优更改
- 注释应该是完整的语句，第一个单词应该大写，除非它是特定标识符
- 块注释：缩进到与该代码相同的级别。块注释的每一行都以＃和一个空格开始
- 行注释：对某一语句行进行注释，注释应该与语句至少隔开两个空格，用＃和一个空格开始
- 注释应该是完整的语句，第一个单词应该大写，除非它是特定标识符