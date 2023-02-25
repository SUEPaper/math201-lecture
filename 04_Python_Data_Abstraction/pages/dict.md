---
layout: center
---

# Dictionaries

---
layout: full
---

# Dictionaries

A dict is a mapping of key-value pairs

```py
states = {
	"CA": "California",
	"DE": "Delaware",
	"NY": "New York",
	"TX": "Texas",
	"WY": "Wyoming"
}
```

Dictionaries support similar operations as lists/strings:

```py
>>> len(states)
5
```

```py
>>> "CA" in states
True
```

```py
>>> "ZZ" in states
False
```

---
layout: full
---

# Dictionary access

```py
words = {
	"más": "more",
	"otro": "other",
	"agua": "water"
}
```

Ways to access a value by key:

```py
>>> words["otro"]
'other'
```

```py
>>> first_word = "agua"
>>> words[first_word]
'water'
```

```py
>>> words["pavo"]
KeyError: pavo
```

```py
>>> words.get("pavo", "🤔")
'🤔'
```

---
layout: full
---

# Dictionary rules

- All keys in a dictionary are distinct (there can only be one value per key)
- A key cannot be a list or dictionary (or any other mutable type)
- The values can be any type, however!

```py
spiders = {
  "smeringopus": {
	  "name": "Pale Daddy Long-leg",
	  "length": 7
  },
  "holocnemus pluchei": {
	  "name": "Marbled cellar spider",
	  "length": (5, 7)
  }
}
```

---
layout: full
---

# Dictionary iteration

```py
insects = {"spiders": 8, "centipedes": 100, "bees": 6}
for name in insects:
    print(insects[name])
```

What will be the order of items?

```py
8 100 6
```

Keys are iterated over in the order they are first added.

---
layout: full
---

# Dictionary comprehensions

General syntax:

```py
{key: value for <name> in <iter exp>}
```

Example:

```py
{x: x*x for x in range(3,6)}
```

---
layout: full
---

# Exercise: Prune

```py
def prune(d, keys):
    """Return a copy of D which only contains key/value pairs
    whose keys are also in KEYS.
    >>> prune({"a": 1, "b": 2, "c": 3, "d": 4}, ["a", "b", "c"])
    {'a': 1, 'b': 2, 'c': 3}
    """
```

<v-click>

答案：

```py
def prune(d, keys):
    """Return a copy of D which only contains key/value pairs
    whose keys are also in KEYS.
    >>> prune({"a": 1, "b": 2, "c": 3, "d": 4}, ["a", "b", "c"])
    {'a': 1, 'b': 2, 'c': 3}
    """
    return {k: d[k] for k in keys}
```

</v-click>


---
layout: full
---

# Exercise: Index

```py
def index(keys, values, match):
    """Return a dictionary from keys k to a list of values v for which 
    match(k, v) is a true value.
    
    >>> index([7, 9, 11], range(30, 50), lambda k, v: v % k == 0)
    {7: [35, 42, 49], 9: [36, 45], 11: [33, 44]}
    """
```

<v-click>

答案：

```py
def index(keys, values, match):
    """Return a dictionary from keys k to a list of values v for which 
    match(k, v) is a true value.
    
    >>> index([7, 9, 11], range(30, 50), lambda k, v: v % k == 0)
    {7: [35, 42, 49], 9: [36, 45], 11: [33, 44]}
    """
    return {k: [v for v in values if match(k, v)] for k in keys}
```

</v-click>


---
layout: full
---

# Nested data

Many useful way to combine lists and dicts:

|||
| ---- | ---- |
| Lists of lists | `[ [1, 2], [3, 4] ]` |
| Dicts of dicts | `{"name": "Brazilian Breads", "location": {"lat": 37.8, "lng": -122}}` |
| Dicts of lists | `{"heights": [89, 97], "ages": [6, 8]}` |
| Lists of dicts | `[{"title": "Ponyo", "year": 2009}, {"title": "Totoro", "year": 1993}]` |
