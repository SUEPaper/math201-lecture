---
layout: center
---

# 循环

---
layout: full
---

# while 循环

The while loop syntax:

```py
while <condition>:
    <statement>
    <statement>
```

As long as the condition is true, the statements below it are executed.

```py
multiplier = 1
while multiplier <= 5:
    print(9 * multiplier)
    multiplier += 1
```

The code is significantly shorter, and it can easily be extended to loop for more or less iterations.

---
layout: full
---

# Using a counter variable

It's common to use a counter variable whose job is keeping track of the number of iterations.

```py
total = 0
counter = 0
while counter < 5:
  total += pow(2, 1)
  counter += 1
```

The counter variable may also be involved in the loop computation:

```py
total = 0
counter = 0
while counter < 5:
  total += pow(2, counter)
  counter += 1
```

---
layout: full
---

# Beware infinite loops

Uh oh..

```py
counter = 1
while counter < 5:
    total += pow(2, counter)
```

What one line of code would fix this?

`counter += 1`

```py
counter = 6
while counter > 5:
  total += pow(2, counter)
  counter += 1
```

How do we save this code?

Intentions are unclear! Change the initial value and condition?


---
layout: full
---

# break

The break statement ends the current loop and jumps to the statement immediately following the loop


```py

while True:
    line = input('> ')
    if line == 'done' : 
       break
    print(line)
print('Done!')

```
---
layout: full
---

# continue

The continue statement ends the current iteration and jumps to the top of the loop and starts the next iteration


```py

while True:
    line = input('> ')
    if line[0] == '#' : 
        continue
    if line == 'done' :
        break
    print(line)
print('Done!')

```

---
layout: full
---

# for loop 循环

```py

for i in [5, 4, 3, 2, 1] :
    print(i)
print('Finished !!!')

```

