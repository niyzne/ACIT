# Week 3 Notes - Lesson 3B

## Instructor Notes

- [Lesson 3B](https://bcitcomputing.notion.site/Lesson-3B-37d05e5107e4800b8060d40c7576e35d)

## Student Notes

### Lesson 3B

---

#### Review

- Conditional statements (`if` statements) run code **only when a condition is `True`**.

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

- Conditions can be:
    - A **comparison** that results in `True` or `False`
    - A **test** that results in `True` or `False`
    - A **boolean value** itself

Example:

```python
understands = True

if understands:
    print("Now you're getting it")
```

- If the condition is `True`, the indented code runs.
- If the condition is `False`, the indented code is skipped.

##### Rules of Conditional Statements

- Only **one block** in a group of conditional statements can run.
- Python runs the **first condition that is `True`**.
- If no condition is `True`, the `else` block runs if one exists.

Structure:

```txt
if       ← required, exactly one
elif     ← optional, can have multiple
else     ← optional, exactly one, must be last
```

---

#### While Loops

- A conditional statement runs a block of code **once** if its condition is `True`.
- A `while` loop runs a block of code **repeatedly** until its condition becomes `False`.

Basic syntax:

```python
while condition:
    # code runs repeatedly
```

- A `while` loop:

  1. Starts with `while`
  2. Has a condition
  3. Ends the condition with `:`
  4. Uses indentation for the code that should repeat

- The loop stops when its condition becomes `False`.
- Once the loop stops, the rest of the script continues.

Example:

```python
while True:
    assignment = input("Please enter the assignment number: ")

    if assignment.isnumeric():
        break
    else:
        print("Assignment number must be numeric")

print("Thank you for entering a valid assignment number")
```

- This repeatedly asks the user for an assignment number.
- If the input is not numeric, a message is printed and the user is asked again.
- `break` stops the loop when a numeric value is entered.

##### `break`

- `break` manually stops a `while` loop.
- This is useful when the condition itself cannot become `False`.

```python
while True:
    # repeated code

    if condition:
        break
```

- `while True:` creates a loop whose condition is always `True`.
- The loop must therefore be stopped manually with `break`.

##### Indentation

- Indentation determines where a block of code ends.
- A `while` loop continues until Python reaches the **first unindented line**.
- Multiple levels of indentation can be used for nested blocks.
-  Be consistent and exact with indentation.

---

#### While Loop Conditions

A `while` loop condition can be:

- A **boolean value**

```python
while True:
    # code
```

- A **comparison**

```python
counter = 10

while counter >= 0:
    print(counter)
    counter = counter - 1
```

- A **function that returns a boolean value**

```python
assignment = input("Please enter assignment number: ")

while not assignment.isnumeric():
    print("Assignment number must be numeric")
    assignment = input("Please enter assignment number: ")
```

- The condition must eventually become `False`, or the loop needs a `break`.

---

#### Nested While Loops

- A **nested loop** is a loop placed inside another loop.
- The inner loop runs as part of the outer loop.

Example:

```python
while keep_playing:
    number = random.randint(1, 10)

    while True:
        guess = input("Guess a number between 1 and 10")

        if guess.isnumeric() and int(guess) == number:
            print("You guessed correctly!")
            break
        else:
            print("Incorrect guess!")
```

- The **outer loop** controls whether the game continues.
- The **inner loop** repeatedly asks for guesses.
- `break` stops the **inner loop**.
- The outer loop can continue after the inner loop finishes.
- Setting the outer loop's condition to `False` stops the outer loop.

---

#### Infinite While Loops

- A `while` loop is **infinite** when its condition never becomes `False` and the loop is never stopped with `break`.
- An infinite loop never stops on its own.

Example:

```python
counter = 10

while counter >= 0:
    counter = counter + 1
    print(counter)
```

- `counter` starts at `10`.
- The condition is `counter >= 0`.
- `counter` keeps increasing.
- Therefore, `counter >= 0` always remains `True`.
- The loop never stops.

**Remember:**

> Always make sure a `while` loop has a way to stop.

A loop can stop by:

- Using `break`
- Making sure its boolean condition eventually becomes `False`

---
