---
layout: center
---

# *Args

---
layout: full
---

# The *args syntax

What if you want a function to accept any number of arguments?

The built-in max function allows that:

```py
max(1, 2) # 2
max(10, 30, 20) # 30
max(-2, 33, -40, 400, 321) # 400
```

That's possible by using the *args syntax in the function definition.

```py
def max(*args):
    # Do something with *args
```

---
layout: full
---

# Forwarding the *args

One way to use *args is to send those arguments into another function.

```py
def min_and_max(*args):
    return min(*args), max(*args)

min_and_max(-2, 33, -40, 400, 321) # -40, 400
```

---
layout: full
---

# Forwarding HOF example

A HOF can return a function that can be called with any number of arguments, and then forward those arguments inside the returned function.

```py
def printed(f):
    def print_and_return(*args):
        result = f(*args)
        print('Result:', result)
        return result
    return print_and_return

printed_max = printed(max)
printed_max(-2, 33, -40, 400, 321)   
```
