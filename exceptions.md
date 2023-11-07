### Exceptions

**1. Handling Exceptions Gracefully:**

In Python, when your code runs into an unexpected problem, it might cause your program to crash. To avoid this, you can use something called "exception handling." It's like having a backup plan for when things go wrong.

Imagine you're trying to divide a number by another number, but you don't want to divide by zero because that's not allowed. You can use `try` and `except` to handle this situation:

```python
try:
    result = 10 / 0  # This could cause a problem
except ZeroDivisionError as e:
    print(f"An error occurred: {e}")
```

In this code, we're trying to divide 10 by 0 (which is not allowed in math). If an error (an exception) happens, we catch it with `except`. This helps our program stay running and display an error message, like "An error occurred."

**2. Custom Exception Classes:**

Sometimes, you might have a specific problem that doesn't quite fit into the standard exceptions Python provides. In that case, you can create your own exception, like a custom error message that describes your problem.

Imagine you're checking someone's age, and you don't want negative ages. You can create a custom error for that:

```python
class CustomError(Exception):
    def __init__(self, message):
        self.message = message

def validate_age(age):
    if age < 0:
        raise CustomError("Age cannot be negative")

try:
    validate_age(-5)  # This might be a problem
except CustomError as e:
    print(f"Custom error: {e}")
```

In this example, we create a custom error called `CustomError` to handle negative ages. If the age is negative, we "raise" this custom error, and it gives us a specific error message.

**3. Finally and Else Clauses:**

Finally, there are two more things: `finally` and `else`. Think of `finally` like a "clean-up" step, and `else` like "what happens when everything is fine."

```python
try:
    result = 10 / 2
except ZeroDivisionError as e:
    print(f"Error: {e}")
else:
    print("No errors occurred")
finally:
    print("This block always runs")

try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Error: {e}")
else:
    print("No errors occurred")
finally:
    print("This block always runs")
```

In the first example, because there is no error, we see "No errors occurred" in the `else` block, and "This block always runs" in the `finally` block. In the second example, because there is an error, we see the error message and both "No errors occurred" and "This block always runs."

These are tools that help you handle problems and keep your programs running smoothly, even when things go wrong.
