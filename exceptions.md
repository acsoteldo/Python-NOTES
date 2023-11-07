### **Exception Handling:**

**1. Handling Exceptions:**
   - Exception handling in Python allows you to anticipate and deal with errors that may occur during program execution, preventing your program from crashing.

   - You can use `try` and `except` to handle exceptions gracefully by specifying code that may raise an exception inside the `try` block and defining how to handle that exception in the `except` block.

   - Example:

     ```python
     try:
         result = 10 / 0  # Division by zero raises a ZeroDivisionError
     except ZeroDivisionError as e:
         print(f"An error occurred: {e}")
     ```

   - In this example, a `ZeroDivisionError` is caught, and an error message is printed, preventing the program from crashing.

**2. Custom Exception Classes:**
   - Python allows you to create custom exception classes by defining your own exceptions. Custom exceptions help you communicate specific errors in your code.

   - Example:

     ```python
     class CustomError(Exception):
         def __init__(self, message):
             self.message = message

     def validate_age(age):
         if age < 0:
             raise CustomError("Age cannot be negative")

     try:
         validate_age(-5)
     except CustomError as e:
         print(f"Custom error: {e}")
     ```

   - In this example, a custom exception class `CustomError` is used to handle a specific error condition, such as a negative age value.

**3. Finally and Else Clauses:**
   - Python's `try` and `except` blocks can be extended with `finally` and `else` clauses.

   - The `finally` block is used to specify code that always executes, whether an exception occurs or not. This is often used for cleanup operations.

   - The `else` block is executed when no exceptions are raised in the `try` block, allowing you to perform actions when everything goes as expected.

   - Example:

     ```python
     try:
         result = 10 / 2
     except ZeroDivisionError as e:
         print(f"Error: {e}")
     else:
         print("No errors occurred")
     finally:
         print("This block always runs")
     ```

   - In this example, the `else` block is executed because there are no exceptions, and the `finally` block always runs, providing a mechanism for cleanup and ensuring that resources are properly released.
