# Python Basics

#### Variables:
- In Python, you can create variables to store data. Example:
    ```python
    x = 5
    name = "Alice"
    is_true = True
    ```

#### Data Types:
- Python has various data types:

    - **Integers**: Whole numbers. Example:
    ```python
    age = 25
    ```

    - **Floats**: Numbers with decimal points. Example:
    ```python
    price = 19.99
    ```

    - **Strings**: Sequences of characters. Example:
    ```python
    greeting = "Hello, World"
    ```

    - **Booleans**: True or False values. Example:
    ```python
    is_raining = False
    ```

#### Lists (Array-like):
- Lists are ordered collections of items. You can access elements by their index, and they can contain various data types. Example:
    ```python
    my_list = [1, 2, 3, "apple", True]
    ```

#### Control Structures:
- **`if`, `elif`, and `else`**:
    - Used for conditional statements. Example:
    ```python
    if x > 10:
        print("x is greater than 10")
    elif x == 10:
        print("x is equal to 10")
    else:
        print("x is less than 10")
    ```

- **`for` Loop**:
    - Used for iterating over a sequence (e.g., a list) or a range of numbers. Example:
    ```python
    for item in my_list:
        print(item)

    for i in range(1, 6):
        print(i)
    ```

- **`while` Loop**:
    - Used for repeating a block of code while a condition is true. Example:
    ```python
    while count < 5:
        print(count)
        count += 1
    ```

- **`do-while` Equivalent**:
    - In Python, there's no direct "do-while" loop, but you can achieve similar behavior using a `while` loop with a `break` statement. Example:
    ```python
    while True:
        # Code to execute at least once
        user_input = input("Do you want to continue? (yes/no): ")
        if user_input == "no":
            break
    ```

- **`switch` Statement Equivalent**:
    - Python doesn't have a `switch` statement, but you can use `if` and `elif` for similar functionality. Example:
    ```python
    def switch_case(case):
        if case == "option1":
            print("Option 1 chosen")
        elif case == "option2":
            print("Option 2 chosen")
        else:
            print("Invalid option")

    switch_case("option1")
    ```


#### Functions:
- Functions are blocks of code that can be reused. You can pass arguments and return values. Example:
    ```python
    def greet(name):
        return f"Hello, {name}!"

    result = greet("Alice")
    print(result)
    ```

#### Input and Output:
- Use `input()` to get user input and `print()` to display output. Example:
    ```python
    user_input = input("Enter your name: ")
    print(f"Hello, {user_input}!")
    ```

#### Comments:
- Use `#` for single-line comments and `'''` or `"""` for multi-line comments. Example:
    ```python
    # This is a single-line comment

    '''
    This is a
    multi-line comment
    '''
    ```

#### Indentation:
- Python uses indentation (whitespace) to indicate blocks of code. Example:
    ```python
    if condition:
        # Indented block
        statement1
        statement2
    # Back to the outer block
    ```

#### Basic Operators:
- Arithmetic operators: `+`, `-`, `*`, `/`, `//`, `%`, `**`
- Comparison operators: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Logical operators: `and`, `or`, `not`

#### Built-in Functions:
- Python has many built-in functions. For example, `len()`, `str()`, `int()`, `float()`, `max()`, `min()`, `sum()`, etc. Example:
    ```python
    my_list = [3, 7, 1, 9, 4]
    length = len(my_list)
    maximum = max(my_list)
    ```

#### Libraries:
- You can import libraries/modules to extend Python's functionality. For example, to work with math functions, you can use the `math` library.
    ```python
    import math

    result = math.sqrt(25)
    ```
