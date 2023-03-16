---
layout: center
---

# 函数

---
layout: full
---

# What is a function?

A function is a sequence of code that performs a particular task and can be easily reused. ♻️

We've already used functions:

```py
add(18, 69)
mul(60, sub(5, 4))
```

A function takes inputs (the arguments) and returns an output (the return value).

18, 69 → add → 87


---
layout: full
---

# Defining functions

The most common way to define functions is Python is the def statement.

```py
def <name>(<parameters>):
    return <return expression>
```

Example:

```py
def add(num1, num2):
    return num1 + num2
```

Once defined, we can call it:

```py
add(2, 2)
add(18, 69)
```

---
layout: full
---

# Anatomy of a function definition

The first line is called the function signature, all lines after are considered the function body.

```py
def <name>(<parameters>):        # ← Function signature
    return <return expression>   # ← Function body
```

```py
def add(num1, num2):             # ← Function signature
    return num1 + num2           # ← Function body
```

The function body can have multiple lines:

```py
def add(num1, num2):             # ← Function signature
    sum = num1 + num2            # ← Function body
    return sum                   # ← Function body
```

---
layout: full
---

# Function arguments

We can pass in any expressions as arguments.

```py
def add(num1, num2):
    return num1 + num2
```

```py
x = 1
y = 2
add(x, y)
```

```py
x = 3
add(x * x, x + x)
```

---
layout: full
---

# Return values

The return keyword returns a value to whoever calls the function (and exits the function).

```py
def add(num1, num2):
    return num1 + num2

sum = add(2, 4)
```

Reminder: You can use function calls in expressions:

```py
big_sum = add(200, 412) + add(312, 256)
```

...and nest function calls inside function calls:

```py
huge_sum = add(add(200, 412), add(312, 256))
```

---
layout: full
---

# Spot the bug #1

What's wrong with this code?

```py
def add(num1, num2):
    return sum
    sum = num1 + num2

sum = add(2, 4)
```

The code after the return statement will not be executed, that line belongs before the return.

---
layout: full
---

# Spot the bug #2

What's wrong with this code?

```py
def add():
    return num1 + num2

sum = add(2, 4)
```

The function body is referring to variables that don't seem to exist. Most likely, they should be parameters in the function signature.

---
layout: full
---

# Spot the bug #3

What's wrong with this code?

```py
def add(num1, num2):
    sum = num1 + num2

sum = add(2, 4)
```

The function body does not return any value. However, the code that calls it tries to use the result of the expression. It should have a return statement that returns the sum.

