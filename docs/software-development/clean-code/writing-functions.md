---
slug: clean-code-writing-functions
title: Writing Functions
tags: [clean-code]
sidebar_position: 4
---


# Writing Functions

Functions are the building blocks of clean code. By following a set of simple yet powerful rules, you can write functions that are clear, concise, and maintainable. This guide provides detailed guidelines on how to write functions effectively, with Python examples to illustrate key points.

In addition, functions are the "verbs" of your code, forming the actions of the system's narrative. Write them cleanly by keeping them small, focused, and well-named. Avoid unnecessary arguments, side effects, and redundancy. Above all, let your functions tell a clear story, one step at a time.

## TL;DR
> - Function should be small and do one thing.
> - Use self-explanatory descriptive names.
> - Keep the number of function arguments manageable, ideally limiting to 2, with a maximum of 3 in exceptional cases.
> - Function return values should be manageable.
> - Prefer returning values from functions rather than modifying arguments directly.
> - Appropriately scope functions as local, class-level, module-level, or library functions.
> - Avoid using arguments that alter behavior of functions.

---

## **Key Guidelines**

### 1. Functions Should Be Small
- A function should ideally fit within 20-30 lines of code. The smaller the function, the easier it is to read, test, and maintain.

#### 
```python
# Bad
def process_data(data):
    # This function does too much

    # validate logic
    # cleaning logic
    # transformation logic

# Good
def validate(data):
    pass  # Validation logic

def clean(data):
    pass  # Cleaning logic

def transform(data):
    pass  # Transformation logic
```

### 2. Do One Thing and Do It Well
A function should have a single, well-defined purpose. If a function does more than one thing, break it down into smaller functions.
```python
# Bad
def calculate_and_save(data):
    result = sum(data)
    with open("output.txt", "w") as file:
        file.write(str(result))

# Good
def calculate(data):
    return sum(data)

def save_to_file(filename, content):
    with open(filename, "w") as file:
        file.write(content)
```

### 3. Use Descriptive Names
Function names should clearly describe what they do. Use long, descriptive names if necessary, rather than cryptic abbreviations.
```python
# Bad
def calc(x):
    pass

# Good
def calculate_total_price(prices):
    pass
```

### 4. Maintain a Single Level of Abstraction
Statements within a function should all operate at the same level of abstraction. Mixing high-level logic with low-level details makes code hard to follow.

```python
# Bad
def process_order(order):
    total = sum(order['items'])
    order['total'] = total
    print(f"Order processed: {order}")

# Good
def calculate_order_total(order):
    return sum(order['items'])

def print_order(order):
    print(f"Order processed: {order}")
```

### 5. Minimize the Number of Arguments
The ideal number of arguments for a function is zero. One or two arguments are acceptable; avoid three or more unless absolutely necessary. Instead create a class if needed.

```python
# Bad
def create_user(name, age, email, address):
    pass

# Good
class UserDetails:
    def __init__(self, name, age, email, address):
        self.name = name
        self.age = age
        self.email = email
        self.address = address

def create_user(user_details):
    pass
```

### 6. Avoid Output Arguments
Prefer returning values rather than modifying arguments passed into the function.

```python
# Bad
def append_message(messages, new_message):
    messages.append(new_message)

# Good
def get_updated_messages(messages, new_message):
    return messages + [new_message]
```

### 7. Avoid Boolean Arguments
Passing booleans to functions often indicates the function does more than one thing. Split the function instead.

```python
# Bad
def configure(mode):
    if mode:
        print("Mode A configured")
    else:
        print("Mode B configured")

# Good
def configure()
    if mode:
        configure_mode_a()
    else:
        configure_mode_b()

def configure_mode_a():
    print("Mode A configured")

def configure_mode_b():
    print("Mode B configured")
```

### 8. Handle Errors Separately
Error handling should be isolated in its own functions to avoid cluttering the main logic.

```python
# Bad
def read_file(file_path):
    try:
        with open(file_path, "r") as file:
            return file.read()
    except FileNotFoundError:
        print("File not found")

# Good
try:
    content = read_file("example.txt")
    print(content)
except FileNotFoundError:
    handle_file_not_found_error()


def read_file(file_path):
    with open(file_path, "r") as file:
        return file.read()

def handle_file_not_found_error():
    print("File not found")
```

### 9. No Side Effects
Functions should do what they claim to do and nothing else. Avoid modifying global variables or unexpected behaviors.


```python
# Bad
counter = 0

def increment():
    global counter
    counter += 1

# Good
def increment(counter):
    return counter + 1
```

### 10. Follow the Stepdown Rule
Organize functions in a way that higher-level functions appear first, followed by lower-level details. This creates a top-down narrative.


```python
# Good
def process_data(data):
    cleaned_data = clean(data)
    transformed_data = transform(cleaned_data)
    save(transformed_data)

def clean(data):
    pass

def transform(data):
    pass

def save(data):
    pass
```


### 11. Use Exceptions for Error Handling
Avoid using error codes unnecessarily. Exceptions simplify the addition of new error types without recompiling or redeploying code.


```python
# Bad
def divide(a, b):
    if b == 0:
        return -1  # Error code
    return a / b

# Good
def divide(a, b):
    if b == 0:
        raise ValueError("Division by zero is not allowed")
    return a / b
```

### 12. Avoid Duplicating Code
Reuse functions and extract common logic to avoid redundancy.

```python
# Bad
def calculate_discount_price(price):
    return price * 0.9

def calculate_premium_price(price):
    return price * 1.1

# Good
def calculate_price(price, factor):
    return price * factor
```
