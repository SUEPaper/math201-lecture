---
layout: center
---

# Lists

---
layout: full
---

# Lists

A list is a container that holds a sequence of related pieces of information.

The shortest list is an empty list, just 2 square brackets:

```py
members = []
```

Lists can hold any Python values, separated by commas:

```py
members = ["Pamela", "Tinu", "Brenda", "Kaya"]

ages_of_kids = [1, 2, 7]

prices = [79.99, 49.99, 89.99]

digits = [2//2, 2+2+2+2, 2, 2*2*2]

remixed = ["Pamela", 7, 79.99, 2*2*2]
```

---
layout: full
---

# List length

Use the global `len()` function to find the length of a list.

```py
attendees = ["Tammy", "Shonda", "Tina"]

print(len(attendees))   #  3

num_of_attendees = len(attendees)
print(num_of_attendees)
```

---
layout: full
---

# Accessing list items (brackets)

Each list item has an index, starting from 0.

```py
letters = ['A', 'B', 'C']
# Index:   0     1     2
```

Access each item by putting the index in brackets:

```py
letters[0]  # 'A'
letters[1]  # 'B'
letters[2]  # 'C'
letters[3]  # 🚫 Error!
```

```py
curr_ind = 1
letters[curr_ind] # 'B'
```

Negative indices are also possible:

```py
letters[-1]  # 'C'
letters[-2]  # 'B'
letters[-4]  # 🚫 Error!
```

---
layout: full
---

# List concatenation

Add two lists together using the + operator:

```py
boba_prices = [5.50, 6.50, 7.50]
smoothie_prices = [7.00, 7.50]
all_prices = boba_prices + smoothie_prices
```

Or the `add` function:

```py
from operator import add

boba_prices = [5.50, 6.50, 7.50]
smoothie_prices = [7.00, 7.50]
all_prices = add(boba_prices, smoothie_prices)
```

---
layout: full
---

# List repetition

Concatenate the same list multiple times using the * operator:

```py
boba_prices = [5.50, 6.50, 7.50]

more_boba = boba_prices * 3
```

Or the `mul` function:

```py
from operator import mul

boba_prices = [5.50, 6.50, 7.50]
more_boba = mul(boba_prices, 3)
```

All together now:

```py
digits = [1, 9, 8, 4]
together = [6, 2, 4] + digits * 2 # [6, 2, 4, 1, 9, 8, 4, 1, 9, 8, 4]
together = add([2, 7], mul(digits, 2))
```

---
layout: full
---

# Nested Lists

Since Python lists can contain any values, an item can itself be a list.

```py
gymnasts = [ ["Brittany", 9.15, 9.4, 9.3, 9.2],
                ["Lea", 9, 8.8, 9.1, 9.5],
                ["Maya", 9.2, 8.7, 9.2, 8.8] ]
```

- What's the length of gymnasts? 

<v-click>

3

</v-click>

- What's the length of gymnasts[0]? 

<v-click>

5

</v-click>


---
layout: full
---

# Accessing nested list items

```py
gymnasts = [
                ["Brittany", 9.15, 9.4, 9.3, 9.2],
                ["Lea", 9, 8.8, 9.1, 9.5],
                ["Maya", 9.2, 8.7, 9.2, 8.8]
            ]
```

Access using bracket notation, with more brackets as needed:

```py
gymnasts[0]    # ["Brittany", 9.15, 9.4, 9.3, 9.2]
gymnasts[0][0] # "Brittany"
gymnasts[1][0] # "Lea"
gymnasts[1][4] # 9.5
gymnasts[1][5] # 🚫 IndexError!
gymnasts[3][0] # 🚫 IndexError!
```


---
layout: full
---

# Containment operator

Use the `in` operator to test if value is inside a container:

```py
digits = [2, 8, 3, 1, 8, 5, 3, 0, 7, 1]

1 in digits # True

3 in digits # True

4 in digits # False

not (4 in digits) # True
```

---
layout: center
---

# For statements

---
layout: full
---

# For loop

The for loop syntax:

```py
for <value> in <sequence>:
    <statement>
    <statement>
```

The for loop provides a cleaner way to write many `while` loops, as long as they are iterating over some sort of sequence.

```py
def count(s, value):
    total = 0
    for element in s:
        if element == value:
            total = total + 1
    return total
```

---
layout: full
---

# For statement execution procedure

```py
for <name> in <expression>:
    <suite>
```

- Evaluate the header \<expression\>, which must yield an iterable value (a sequence)
- For each element in that sequence, in order:
    1. Bind \<name\> to that element in the current frame
    2. Execute the \<suite\>

---
layout: full
---

# Looping through nested lists

```py
gymnasts = [
                ["Brittany", 9.15, 9.4, 9.3, 9.2],
                ["Lea", 9, 8.8, 9.1, 9.5],
                ["Maya", 9.2, 8.7, 9.2, 8.8]
            ]
```

Use a nested `for-in` loop:

```py
for gymnast in gymnasts:
    for data in gymnast:
        print(data, end="|")
```

Remember what type of data is being stored in the loop variable!


---
layout: full
---

# Sequence unpacking in for statements

```py
pairs = [[1, 2], [2, 2], [3, 2], [4, 4]]
same_count = 0

for x, y in pairs:
    if x == y:
        same_count = same_count + 1
```

Each name is bound to a value, like in multiple assignment.

---
layout: center
---

# Ranges

---
layout: full
---

# The range type

A range represents a sequence of integers.

```py
... -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5...
                range(-2, 3)
```

If just one argument, range starts at 0 and ends just before it:

```py
for num in range(6):
    print(num)       # 0, 1, 2, 3, 4, 5
```

If two arguments, range starts at first and ends just before second:

```py
for num in range(1, 6):
    print(num)       # 1, 2, 3, 4, 5
```

---
layout: center
---

# List comprehensions

---
layout: full
---

# List comprehension syntax

A way to create a new list by "mapping" an existing list.

Short version:

```py
[<map exp> for <name> in <iter exp>]
```

```py
odds = [1, 3, 5, 7, 9]
evens = [(num + 1) for num in odds]
```

Long version (with filter):

```py
[<map exp> for <name> in <iter exp> if <filter exp>]
```

```py
temps = [60, 65, 71, 67, 77, 89]
hot = [temp for temp in temps if temp > 70]
```

---
layout: full
---

# List comprehension execution procedure

```py
[<map exp> for <name> in <iter exp> if <filter exp>]
```

- Add a new frame with the current frame as its parent
- Create an empty result list that is the value of the expression
- For each element in the iterable value of \<iter exp\>:
    - Bind \<name\> to that element in the new frame from step 1
    - If \<filter exp\> evaluates to a true value, then add the value of \<map exp\> to the result list

```py
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'm', 'n', 'o', 'p']
word = [letters[i] for i in [3, 4, 6, 8]]
```

---
layout: full
---

# Exercise: Divisors

```py
def divisors(n):
    """Returns all the divisors of N.

    >>> divisors(12)
    [1, 2, 3, 4, 6]
    """
```

<br/>

<v-click>

答案: 

```py
def divisors(n):
    """Returns all the divisors of N.

    >>> divisors(12)
    [1, 2, 3, 4, 6]
    """
    return [x for x in range(1, n) if n % x == 0]
```

</v-click>


---
layout: full
---

# Exercise: Frontloaded

```py
def front(s, f):
    """Return S but with elements chosen by F at the front.

    >>> front(range(10), lambda x: x % 2 == 1)  # odds in front
    [1, 3, 5, 7, 9, 0, 2, 4, 6, 8]
    """
```

<br/>

<v-click>

答案: 

```py
def front(s, f):
    """Return S but with elements chosen by F at the front.

    >>> front(range(10), lambda x: x % 2 == 1)  # odds in front
    [1, 3, 5, 7, 9, 0, 2, 4, 6, 8]
    """
    return [e for e in s if f(e)] + [e for e in s if not f(e)]
```

</v-click>

---
layout: center
---

# Slicing

---
layout: full
---

# Slicing syntax

Slicing a list creates a new list with a subsequence of the original list.

```py
letters = ["A", "B", "C", "D", "E", "F"]
        #   0    1    2    3    4    5

sublist1 = letters[1:]    # ['B', 'C', 'D', 'E', 'F']
sublist2 = letters[1:4]   # ['B', 'C', 'D']
```

Slicing also works for strings.

```py
compound_word = "cortaúñas"

word1 = compound_word[:5]    # "corta"
word2 = compound_word[5:]   # "úñas"
```

Negatives indices and steps can also be specified.

---
layout: full
---

# Copying whole lists

Slicing a whole list copies a list:

```py
listA = [2, 3]
listB = listA

listC = listA[:]
listA[0] = 4
listB[1] = 5
```

`list()` creates a new list containing existing elements from any iterable:

```py
listA = [2, 3]
listB = listA

listC = list(listA)
listA[0] = 4
listB[1] = 5
```

Python3 provides more ways in the [copy module](https://docs.python.org/3/library/copy.html).


---
layout: full
---