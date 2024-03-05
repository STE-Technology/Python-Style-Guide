# Python Style Guide
It's important to follow good variable naming conventions and style guidelines (outlined in a document called the [Python Enhancement Proposal 8](https://pep8.org/), or PEP8). This helps us write clean, readable, and maintainable code. 

Here is a summary of style guidelines expected of you in this class.

## Whitespace
- Use whitespace to improve code readability.
- Separate logical paragraphs of code with blank lines.
- Surround operators and commas with whitespace for clarity.
- Avoid whitespace immediately inside parentheses, bracks, or braces.

### Example: Separate logical paragraphs of code with blank lines
#### Good
```python
# Ask the user for input
group_size = input("How many people in your group? ")
aftertax_total = input("What was the total bill after tax? ")
tip_percentage = input("How much do you want to tip (standard is 15%)? ")

# Calculate pre-tax total by backing out HST from after-tax total
pretax_total = float(aftertax_total) / 1.13

# Calculate desired tip based on pre-tax total
tip_total = pretax_total * (float(tip_percentage) / 100)
```

#### Bad
```python
group_size = input("How many people in your group? ")
aftertax_total = input("What was the total bill after tax? ")
tip_percentage = input("How much do you want to tip (standard is 15%)? ")
pretax_total = float(aftertax_total) / 1.13
tip_total = pretax_total * (float(tip_percentage) / 100)
```

### Example: Surround operators and commas with whitespace for clarity
#### Good
```python
total_price = float((item1 + item2 + item3) * 1.13)
print("You Pay", total_price)
```
#### Bad
```python
total_price=float((item1+item2+item3)*1.13)
print("You Pay",total_price)
```

### Example: Avoid whitespace immediately inside parentheses, bracks, or braces
#### Good
```python
total_price = float((item1 + item2 + item3) * 1.13)
```

#### Bad
```python
total_price = float ( ( item1 + item2 + item3 ) * 1.13 )
```

## Indentation
- Indent using 4 spaces for each level of indentation.
- Be consisten with indentation throughout the codebase.


## Variables
- Choose variable names that are meaningful and describe their purpose or content.
- Use lowercase letters with underscores for multi-word names (i.e. snake_case).
- Avoid using reserved words.
- Maintain consistent naming conventions throughout your codebase.
- Use meaningful prefixes for variable names in specific contexts. For example, if there are multiple variables that store a student's grade, you can distinguish them with `num_grade` (e.g. 97) and `str_grade` (e.g. A, B, C, D)


### Example: Use descriptive names
Choose variable names that are meaningful and describe their purpose or content. Avoid single-letter variable names except for loop indices or other very short-lived variables.

#### Good
```python
name = "John"
num_students = 10
```

#### Bad
```python
n = "John"
x = 10
```

### Example: Use lowercase letters with underscores for multi-word names (i.e. snake_case)
Use underscores (_) to separate words in variable names for better readability.
#### Good
```python
max_speed = 100
user_name = "example"
```

#### Bad
```python
MaxSpeed = 100
userName = "example"
```

### Example: Avoid using reserved words
Do not use special or reserved words as variable names.

#### Bad: 'class' is a reserved word
```python
class = "example"
```

### Example: Be consistent
Maintain consistent naming conventions throughout your codebase.

#### Good
```python
max_speed = 100
min_speed = 50
```

#### Bad
```python
maxSpeed = 100
min_speed = 50
```

### Example: Use meaningful prefixes for variable names in specific contexts
Use prefixes such as "is_" for Boolean variables, "num_" for counts or number variables, and "str_" for string variables.

#### Good
```python
is_valid = True
str_grade = "A"
num_grade = "97
```

#### Bad
```
valid = True
grade = "A"
grade2 = "97
```

### Avoid magic numbers
Assign numbers to variables with descriptive names instead of using them directly in your code.

#### Good
```python
max_speed = 100
acceleration = 9.8
```

#### Bad
```
distance = time * 9.8
```

## Comments
- **Clarity Over Comments**: Strive to write clear and understandable code. Use comments only when necessary to explain complex logic or provide additional context.
- **Avoid Verbosity**: Ensure that you don't have *too many comments*. Code that is too verbose or wordy can take away from readability and clarity.
- **Consistency**: Follow consistent commenting conventions throughout your codebase to improve readability and maintainability.

### Single-Line Comments
- Use single-line comments to provide short explanations, notes, or context for specific lines of code.
- Use single-line comments to clarify complex or non-obvious code.
- Place comments *above* the line they describe for clarity.

#### Good
```python
# Convert Celsius to Fahrenheit
fahrenheit = (celsius * 9/5) + 32
```
#### Bad
Avoid simply replicating code in comments, which can lead to redundancy and confusion:

```python
num_a = 10  # num_a is 10
num_b = 20  # num_b is 20

# result is num_a + num_b
result = num_a + num_b

# print result
print("Result:", result)
```

### Multi-Line Comments
Use multi-line comments to provide detailed documentation about purpose, usage, inputs, outputs, and behavior of entire programs, functions, modules, etc. 

#### Good: Program Header
Begin each Python file with a multi-line comment acting as a program header to describe what the program does.

```python
"""
File: celsius.py
Author: Dave Cheng
Date: 2024-02-21
Description: Converts temperture from Celsius to Fahrenheit.
"""

# Get Celsius temperature from user
temp_celsius = float(input("Enter temperature in Celsius: "))

# Convert Celsius to Fahrenheit
temp_fahrenheit = (celsius * 9/5) + 32

# Output result
print("Temperature in Fahrenheit:", temp_fahrenheit)
```

## Long Lines of Code
In general, you do not want a line of code to exceed the width of an average screen — about 80 characters. \
Keep code to a screen width promotes readability. 

In cases you have to write a long line of code, or just to promopte readability in general, you can break a \
single line of code across multiple lines using **line continuation**. This can be done with code in \
parentheses (e.g. arithmetic operations) or with the `\` ("backslash") escape character in string \
literals. 

#### Good: Using parentheses for line continuation
```python
total = (value1 * factor1 + 
         value2 + factor2 + 
         value3 + factor3 + 
         value4 * factor4 + 
         value5 * factor5)
```

#### Bad: Long lines of code
```python
total = (value1 * factor1 + value2 + factor2 + value3 + factor3 + value4 * factor4 + value5 * factor5)
```

You can also use `\` in string literals, such as a `print()` statement:

#### Good
```python
print("What is the answer? \
      \n(a) Choice \
      \n(b) Choice \
      \n(C) Choice")
```

#### Bad
```python
print("What is the answer?\n(a) Choice\n(b) Choice\n(c) Choice")
```