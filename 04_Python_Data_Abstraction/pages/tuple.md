---
layout: center
---

# Tuples

---
layout: full
---

# Tuples

A **tuple** is an immutable sequence. It's like a list, but no mutation allowed!

An empty tuple:

```py
empty = ()
# or
empty = tuple()
```

A tuple with multiple elements:

```py
conditions = ('rain', 'shine')
# or
conditions = 'rain', 'shine'
```

A tuple with a single element: 🙀

```py
oogly = (61,)
# or
oogly = 61,
```

---
layout: full
---

# Tuple operations

Many of list's read-only operations work on tuples.

Combining tuples into a new tuple:

```py
('come', '☂') + ('or', '☼')  # ('come', '☂', 'or', '☼')
```

Checking containment:

```py
'wally' in ('wall-e', 'wallace', 'waldo')  # True
```

Slicing:

```py
rainbow = ('red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet')
roy = rainbow[:3]  # ('red', 'orange', 'yellow')

```

---
layout: center
---

# Immutability vs. Mutability


---
layout: full
---

# Immutable vs. Mutable

An **immutable** value is unchanging once created.

Immutable types (that we've covered): int, float, string, tuple

```py
a_tuple = (1, 2)
a_tuple[0] = 3                  # 🚫 Error! Tuple items cannot be set.
a_string = "Hi y'all"
a_string[1] = "I"               # 🚫 Error! String elements cannot be set.
a_string += ", how you doing?"  # 🤔 How does this work?
an_int = 20
an_int += 2                     # 🤔 And this?
```


A **mutable** value can change in value throughout the course of computation. All names that refer to the same object are affected by a mutation.

Mutable types (that we've covered): list, dict

```py
grades = [90, 70, 85]
grades_copy = grades
grades[1] = 100
words = {"agua": "water"}
words["pavo"] = "turkey"
```

---
layout: full
---

# Tuples