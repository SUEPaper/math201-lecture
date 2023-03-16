---
layout: center
---

# 高阶函数

---
layout: full
---

# What are higher-order functions?

A function that either:

- Takes another function as an argument
- Returns a function as its result

All other functions are considered first-order functions.

---
layout: full
---

# Generalizing over computational processes

<br/>

$\sum_{k=1}^5 k = 1 + 2 + 3 + 4 + 5 = 15$

<br/>

$\sum_{k=1}^5 k^3 = 1^3 + 2^2 + 3^3 + 4^3 + 5^3 = 225$

<br/>

$\sum_{k=1}^5 \frac{8}{(4k -3 ) \times (4k - 1)}=\frac{8}{3} + \frac{8}{35} + \frac{8}{99} + \frac{8}{195} + \frac{8}{323}=3.04$

<br/>

The common structure among functions may be a computational process, not just a number.

---
layout: full
---

# Functions as arguments

```py
def cube(k):
    return k ** 3

def summation(n, term):
    """Sum the first N terms of a sequence.
    >>> summation(5, cube)
    225
    """
    total = 0
    k = 1
    while k <= n:
        total = total + term(k)
        k = k + 1
    return total
```

---
layout: full
---

# Functions as return values

Functions defined within other function bodies are bound to names in a local frame.

```py
def make_adder(n):
    """Return a function that takes one argument k
       and returns k + n.
    >>> add_three = make_adder(3)
    >>> add_three(4)
    7
    """
    def adder(k):
        return k + n
    return adder
```

---
layout: center
---

# Lambda 表达式

---
layout: full
---

# Lambda syntax

A lambda expression is a simple function definition that evaluates to a function.

The syntax:

```py
lambda <parameters>: <expression>
```

A function that takes in parameters and returns the result of expression.

A lambda version of the square function:

```py
square = lambda x: x * x
```

A function that takes in parameter x and returns the result of x * x.

---
layout: full
---

# Lambda syntax tips

A lambda expression does not contain return statements or any statements at all.

Incorrect:

```py
square = lambda x: return x * x
```

Correct:

```py
square = lambda x: x * x
```

---
layout: full
---

# Lambda as argument

It's convenient to use a lambda expression when you are passing in a simple function as an argument to another function.

Instead of...

```py
def cube(k):
    return k ** 3

summation(5, cube)
```

We can use a lambda:

```py
summation(5, lambda k: k ** 3)
```

---
layout: full
---

# Conditional expressions

A conditional expression has the form:

```py
<consequent> if <predicate> else <alternative>
```

Evaluation rule:

- Evaluate the \<predicate\> expression.
- If it's a true value, the value of the whole expression is the value of the \<consequent\>.
- Otherwise, the value of the whole expression is the value of the \<alternative\>.


---
layout: full
---

# Lambdas with conditionals

This is invalid syntax:

```py
lambda x: if x > 0: x else: 0
```

Conditional expressions to the rescue!

```py
lambda x: x if x > 0 else 0
```