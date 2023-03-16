---
layout: full
---

# Expressions (with operators)

An expression describes a computation and evaluates to a value.

Some expressions use operators:

```py
18 + 69
```

```py
6/23
```

```py
2 * 100
```

```py
2 ** 100
```

---
layout: full
---

# Call Expressions

Many expressions use function calls:

```py
pow(2, 100)
```

```py
max(50, 300)
```

```py
min(-1, -300)
```

---
layout: full
---

# Expressions (both ways)

Expressions with operators can also be expressed with function call notation:

```py
2 ** 100
pow(2, 100)
```

```py
from operator import add

18 + 69
add(18, 69)
```

The `pow()` function is a built-in; it's provided in every Python environment. Other functions (`add()`, `div()`, etc) must be imported from the `operator` module in the Python standard library.

---
layout: full
---

# Names

A name can be bound to a value.

One way to bind a name is with an assignment statement:

```py
x	=	7
```

The value can be any expression:

```py
x	=	1 + 2 * 3 - 4 // 5
```

---
layout: full
---

# Using names

A name can be referenced multiple times:

```py
x = 10
y = 3

result1 = x * y
result2 = x + y
```

A name that's bound to a data value is also known as a variable.

---
layout: full
---

# Name rebinding

A name can only be bound to a single value.

```py
my_name = 'Pamela'

my_name = my_name + 'ela'
```

💬 Will that code error? If not, what will my_name store?

<v-click>

It will not error (similar code in other languages might, however). The name my_name is now bound to the value 'Pamelaela'.

</v-click>

---
layout: full
---

# Exercise

What will be the value of the final expression in this sequence?

```py
f = min
f = max
g = min
h = max
max = g
max(f(2, g(h(1, 5), 3)), 4)
```