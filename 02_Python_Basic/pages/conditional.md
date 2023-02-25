---
layout: center
---

# 条件语句

---
layout: full
---

# Conditional statements

A conditional statement gives your code a way to execute a different suite of code statements based on whether certain conditions are true or false.

```py
if <condition>:
    <statement>
    <statement>
    ...
```

A simple conditional:

```py
clothing = "shirt"

if temperature < 32:
    clothing = "jacket"
```

---
layout: full
---

# Compound conditionals

A conditional can include any number of elif statements to check other conditions.

```py
if <condition>:
    <statement>
    ...
elif <condition>:
    <statement>
    ...
elif <condition>:
    <statement>
    ...
```

Example:

```py
clothing = "shirt"

if temperature < 0:
    clothing = "snowsuit"
elif temperature < 32:
    clothing = "jacket"
```

---
layout: full
---

# The else statement

A conditional can include an else to specify code to execute if no previous conditions are true.

```py
if <condition>:
    <statement>
    ...
elif <condition>:
    <statement>
    ...
else <condition>:
    <statement>
    ...
```

Example:

```py
if temperature < 0:
    clothing = "snowsuit"
elif temperature < 32:
    clothing = "jacket"
else:
    clothing = "shirt"
```