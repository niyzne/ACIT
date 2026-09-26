# Week 3 Notes - Lesson 3

## Instructor Notes

- [Lesson 3](https://bcitcomputing.notion.site/Lesson-3-37d05e5107e480ad8121eaff28718f6e)

## Student Notes

### Lesson 3

---
#### Review

- `input()`
    - always returns a `str`
    - If you want to do math with the input, you need to convert it to a number:
        - `int()` → integer
        - `float()` → decimal number
    - Converting invalid input can cause an error:
        - good
            - `"123"` → `int()`
        - bad
            - `"hello"` → `int()`
            - `""` → `int()`

- When user input can be invalid, use a **conditional statement** to check the value before doing something with it.

---

#### Conditional Statements

- Conditional statements let your program run code **only when a condition is true**.

Basic syntax:

```python
if condition:
    # code runs if condition is True
```

- A conditional statement:

  1. Starts with `if`
  2. Has a condition
  3. Ends the condition with `:`
  4. Uses indentation for the code that should run

Example:

```python
x = 10
y = 5

if x > y:
    print("X is greater than y")
```

- Conditions evaluate to either `True` or `False`.

---

#### Truthy and Falsy Values

- Python treats some values as inherently `True` or `False` when used as conditions.

- **Falsy values:**
    - `None`
    - `0`
    - `""` (empty string)
    - Empty sequences, sets, and dictionaries
- **Truthy values:**
    - Any non-zero number
    - Any non-empty string
    - Any non-empty sequence, set, or dictionary

This means you can do:

```python
test_string = "testing 123"

if test_string:
    print("The string is not empty")
```

To check if it is empty:

```python
if not test_string:
    print("The string is empty")
```

---

#### Comparison Operators

Think of it as 
> "A is `<Comparison Operator>` B"

| Operator | Meaning |
| --- | --- |
| `>` | greater than |
| `>=` | greater than or equal to |
| `<` | less than |
| `<=` | less than or equal to |
| `==` | equal to |
| `!=` | not equal to |

**Remember:** 
> `=` assigns a value, while `==` compares two values.

---

#### Containment Operators

* `in` → checks whether a value exists inside another value
* `not in` → checks whether a value does **not** exist inside another value

```python
if "CIT" in "BCIT":
    print("CIT was found")
```

```python
if "OOP" not in "ACIT1515":
    print("OOP was not found")
```

---

#### `not`

- `not` reverses a boolean condition.

```python
if not test_string:
    print("The string is empty")
```

* `not` can also be used with `in`:

```python
if "OOP" not in course:
    print("OOP is not in the course")
```

---

#### Practical Example

- Strings have an `.isnumeric()` method that checks whether they contain numeric characters.
- `.isnumeric()` returns a boolean:
    - numeric string → `True`
    - non-numeric string → `False`

```python
birth_year = input("Please enter your birth year: ")
current_year = 2026

if birth_year.isnumeric():
    birth_year = int(birth_year)
    print(f"You are {current_year - birth_year} years old")
```

- This allows us to check the input **before** converting it with `int()`.

---

#### `else`

- provides a fallback when the `if` condition is `False`.
- `else` must come after an `if`.
- `else` does not have its own condition.

```python
if birth_year.isnumeric():
    birth_year = int(birth_year)
    print(f"You are {current_year - birth_year} years old")
else:
    print("I'm sorry, you did not enter a number")
```

---

#### `elif`

* `elif` means **"else if"**.
* Use `elif` when there are multiple possible conditions.

```python
if hasCar:
    print("You can drive to school")
elif hasBusPass:
    print("You can take the bus")
elif hasBike:
    print("You can bike to school")
else:
    print("You cannot get to school")
```

* Only **one block** in an `if`/`elif`/`else` chain runs.
* Python checks conditions from **top to bottom**.
* The **first condition that is `True`** runs, and the remaining conditions are skipped.
* If every condition is `False`, the `else` block runs (if one exists).

Structure:

```txt
if       ← required, exactly one
elif     ← optional, can have multiple
else     ← optional, exactly one, must be last
```

---

#### Logical Operators

Use logical operators to combine multiple conditions.

| Operator | Meaning |
| --- | --- |
| `and` | Both conditions must be `True` |
| `or` | At least one condition must be `True` |
| `not` | Reverses the condition |

Example:

```python
if hasCar or hasBusPass or hasBike:
    print("You can get to school")
else:
    print("You cannot get to school")
```

Using `and` and `not`:

```python
if not hasCar and not hasBusPass and not hasBike:
    print("You cannot get to school")
else:
    print("You can get to school")
```

---
