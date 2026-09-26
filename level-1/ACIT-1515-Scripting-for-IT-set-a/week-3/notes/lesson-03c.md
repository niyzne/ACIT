# Week 3 Notes - Lesson 3C

## Instructor Notes

- [Lesson 3C](https://bcitcomputing.notion.site/Lesson-3-37d05e5107e480ad8121eaff28718f6e)

## Student Notes

### Lesson 3C

---

#### Sequences: Strings, Lists, and Tuples

- A **sequence** is an ordered collection of values.
- Strings are sequences of individual characters.

```python
language = "Python"
```

- The string `"Python"` is a sequence of:
    - `P`
    - `y`
    - `t`
    - `h`
    - `o`
    - `n`

##### Sequence Operations

- `in` checks whether a value exists in a sequence.
- `not in` checks whether a value does not exist in a sequence.

```python
language = "Python"

print("P" in language)      # True
print("x" in language)      # False
print("x" not in language)  # True
print("ython" in language)  # True
```

- `+` can concatenate (join) sequences.

```python
first = "ACIT"
second = "1515"

print(first + second) # ACIT1515
```

- `len()` returns the length of a sequence.

```python
language = "Python"

num_characters = len(language)
print(num_characters) # 6
```

- Square brackets can be used with a numeric index to access a value.

```python
language = "Python"

print(language[0]) # P
print(language[1]) # y
```

- Indexing starts at `0`.
- Negative indexes start from the end:
    - `-1` → last value
    - `-2` → second-last value

```python
print(language[-1]) # n
print(language[-2]) # o
```

##### Slicing

- Square brackets can also be used to access part of a sequence.
- `[start:end]`
- The `end` index is **not included**.

```python
language = "Python"

print(language[2:])   # thon
print(language[2:4])  # th
print(language[:3])   # Pyt
```

- `count()` counts how many times a value occurs in a sequence.

```python
state = "Mississippi"

print(state.count("s")) # 4
```

- `index()` finds the index of the **first occurrence** of a value.

```python
state = "Mississippi"

print(state.index("s")) # 2
```

---

#### Lists

- Lists are sequences that can contain different types of values.
- Lists can store multiple values in one variable.
- Lists are created using square brackets.

```python
number_list = [1, 2, 3, 4, 5]
string_list = ["a", "b", "c", "Python"]
boolean_list = [True, False, True, True]
mixed_list = [1, "1", True]
```

- Lists can contain other lists.

```python
letters = [
    "a",
    "b",
    ["c", "d", "e"],
    "f"
]
```

- Sequence operations can also be used with lists:
    - `in`
    - `not in`
    - `+`
    - `len()`
    - indexing
    - slicing
    - `count()`
    - `index()`

```python
my_list = ["BCIT", "SFU", "VCC", "UBC"]

print("BCIT" in my_list)
print(my_list + my_list)
print("Capilano" not in my_list)
print(len(my_list))
print(my_list[1:3])
```

output

```txt
True
['BCIT', 'SFU', 'VCC', 'UBC', 'BCIT', 'SFU', 'VCC', 'UBC']
True
4
['SFU', 'VCC']
```

- Values inside a list are counted as individual values.
- `"SFU"` is one value in the list, even though it is also a string sequence.

##### Nested Lists

- A list can contain another list.
- You can use multiple square brackets to access values inside nested lists.

```python
letters = [
    "a",
    "b",
    ["c", "d", "e"],
    "f"
]

print(letters[1])    # b
print(letters[2])    # ["c", "d", "e"]
print(letters[2][1]) # d
```

##### Mutable Lists

- Lists are **mutable**, meaning their values can be changed.
- `append()` adds a value to the end of a list.

```python
a_list = []

a_list.append("a")
a_list.append("b")
a_list.append("c")

print(a_list)
# ["a", "b", "c"]
```

- A value inside a list can also be changed using its index.

```python
a_letter_list = ["a", "b", "c", "d"]

a_letter_list[1] = "B"

print(a_letter_list)
# ["a", "B", "c", "d"]
```

---

#### Strings vs Lists

- Lists are **mutable**.
- Strings are **immutable**.
- Mutable means the values inside can be changed.
- Immutable means the values inside cannot be changed.

This works with a list:

```python
a_letter_list[1] = "B"
```

This does not work with a string:

```python
language = "python"

language[0] = "P"
# TypeError
```

- Strings cannot be changed directly.
- New strings can be created instead.

---

#### Tuples

- Tuples are another sequence type.
- Tuples work like lists, but they are **immutable**.
- Tuples are created using parentheses.

```python
first_tuple = ("BCIT", "SFU", "UBC")
```

- Tuples use square brackets for indexing and slicing, just like lists.

```python
first_tuple = ("BCIT", "SFU", "UBC")

print("SFU" in first_tuple)
print(first_tuple[0])  # BCIT
print(first_tuple[1:]) # ("SFU", "UBC")
```

- Values inside a tuple cannot be changed.

```python
second_tuple = ("a", "b", "c")

second_tuple[0] = "A"
# TypeError
```

- Use a tuple when the values **should not change**.

---

#### Sequence Conversion Methods

Python provides functions to convert between sequence types:

```python
str()
list()
tuple()
```

Examples of uses:

- Convert a string into a list of individual characters.
- Convert values in a list into a string.
- Convert a list into a tuple so its values cannot be modified.

```python
grades = [90, 95, 80, 76]

immutable_grades = tuple(grades)

print(immutable_grades)
```

---

#### Using Loops with Sequences

- Loops allow us to repeat one or more lines of code multiple times.
- They help make code:
    - less repetitive
    - shorter
    - able to handle sequences with unknown or changing lengths

Instead of writing:

```python
cities = ["Vancouver", "Richmond", "Surrey", "Burnaby"]

print(cities[0])
print(cities[1])
print(cities[2])
print(cities[3])
```

- A loop can automatically go through the sequence.
- This avoids hard-coding every value.

---

#### For Loops

- A `for` loop can:
    - run code a set number of times
    - step through a sequence
    - move forwards or backwards
    - use different step sizes

Basic syntax:

```python
for variable in sequence:
    # code
```

Example:

```python
letters = ["a", "b", "c", "d"]

for letter in letters:
    print(letter)
```

- The loop runs once for every value in the sequence.
- `letter` is automatically assigned each value in order.
- The variable name after `for` can be whatever you want.

For example:

```python
for letter in letters:
    print(letter)
```

- First loop → `letter` is `"a"`
- Second loop → `letter` is `"b"`
- Third loop → `letter` is `"c"`
- Fourth loop → `letter` is `"d"`
- Once the sequence has been completely processed, the rest of the script continues.

##### Indentation in For Loops

- Any statements indented underneath `for` are part of the loop.

```python
letters = ["a", "b", "c", "d"]

for letter in letters:
    print("Inside loop")
    print(letter)

print("After loop")
```

- Both indented statements run for every value.
- The loop ends when the next **unindented** line is encountered.

---

#### Ranges

- `range()` provides a sequence of numbers for a `for` loop.
- It can be used to:
    - loop a specific number of times
    - loop backwards
    - use increments greater than `1`

Basic example:

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

- When only one number is given:
    - `start` defaults to `0`
    - `step` defaults to `1`
    - the given number is the `end`
    - the `end` value is not included

Structure:

```python
range(start, end, step)
```

Example:

```python
for i in range(1, 5):
    print(i)
```

Output:

```text
1
2
3
4
```

Using a step:

```python
for i in range(2, 6, 2):
    print(i)
```

Output:

```text
2
4
```

Counting backwards:

```python
for i in range(100, 0, -10):
    print(i)
```

- A function such as `len()` can also be used with `range()`.

```python
cities = ["Vancouver", "Richmond", "Surrey", "Burnaby"]

for i in range(len(cities)):
    print(cities[i])
```

- Using `range(len(sequence))` gives access to the current **index**.

---

#### Enumeration

- `enumerate()` allows us to access both:
    - the numeric index
    - the value

Example:

```python
options = ["Add", "Update", "Delete"]

for index, value in enumerate(options):
    print(index, value)
```

Output:

```text
0 Add
1 Update
2 Delete
```

- `enumerate()` returns tuples containing:
    - the index
    - the value
- Two variables are used because each tuple contains two values.

---

#### `break` and `continue`

- `break` stops a loop early.
- `break` can be used with both `while` and `for` loops.

Example:

```python
password = ""

while True:
    password = input("Please enter your password: ")

    if len(password) >= 16:
        break
```

- The loop stops when the condition is met.

`break` can also stop a `for` loop:

```python
schools = ["UBC", "SFU", "BCIT", "VCC", "Capilano"]

for school in schools:
    if school == "BCIT":
        break
```

##### `continue`

- `continue` skips the current iteration and starts the next iteration of the loop.

```python
for i in range(10):
    if i % 2 == 1:
        continue

    print(i)
```

- Odd numbers are skipped.
- The output is:

```text
0
2
4
6
8
```

---

#### Combining Loops and Conditional Statements

- Conditional statements can be placed **inside loops**.
- Loops can also be placed **inside conditional statements**.
- Blocks can be placed inside other blocks.
- Indentation determines which statements belong to each block.

Example:

```python
print("Before loop")

for i in range(5):
    print("Inside loop")

print("After loop")
```

- `After loop` is not part of the loop because it is unindented.

Compare with:

```python
print("Before loop")

for i in range(5):
    print("Inside loop")

    print("After loop")
```

- `After loop` is now part of the loop because it is indented.

**Remember:**

> Indentation matters in Python.

- A block ends when Python encounters the next **unindented** line.
- Pay attention to how statements line up.
- Incorrect indentation can change the output or behavior of the program.

---
