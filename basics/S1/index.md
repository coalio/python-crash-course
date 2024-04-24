# Session 1: Introduction to Python

## Topics

- **Variables, data types and operators**
  - Int, float, complex, str, booleans (variable scope)
  - List, tuple, range, dict (basic operations)
  - Operators (+, -, *, /, %, *, //, )
  - Logical operators (and, or, not)
- **Flow control**
  - Conditions
  - Loops
- **Functions**
  - Definitions and usage
- **Expressions**
- **Comprehensions**

### Variables, data types and operators

In Python, variables are created when they are assigned a value. The type of the variable is determined by the value assigned to it. The basic data types in Python are:

- **Integers**: Whole numbers, e.g. 1, 2, 3, 4, 5, etc.
- **Floats**: Decimal numbers, e.g. 1.0, 2.5, 3.14, etc.
- **Complex numbers**: Numbers with a real and imaginary part, e.g. 1 + 2j, 3 + 4j, etc.
- **Strings**: Text, e.g. 'Hello, World!', 'Python', etc.
- **Booleans**: True or False.
- **Lists**: Ordered collection of items, e.g. [1, 2, 3], ['a', 'b', 'c'], etc.
- **Tuples**: Ordered collection of items, e.g. (1, 2, 3), ('a', 'b', 'c'), etc.
- **Dictionaries**: Collection of key-value pairs, e.g. {'a': 1, 'b': 2, 'c': 3}, etc.
- **Sets**: Unordered collection of unique items, e.g. {1, 2, 3}, etc.

```python
a = 1
b = 2.5
c = 3 + 4j
d = 'Hello, World!'
e = True
f = [1, 2, 3]
g = (1, 2, 3)
i = {'a': 1, 'b': 2, 'c': 3}
```

Operators are used to perform operations on variables. The basic operators in Python are:

- **Arithmetic operators**: +, -, *, /, %, **, //.
- **Comparison operators**: ==, !=, >, <, >=, <=.
- **Logical operators**: and, or, not.
- **Assignment operators**: =, +=, -=, *=, /=, %=, //=.
- **Identity operators**: is, is not.
- **Membership operators**: in, not in.
- **Bitwise operators**: &, |, ^, ~, <<, >>.

### Flow control

Flow control is used to determine the order in which statements are executed in a program. The basic flow control statements in Python are:

- **Conditions**: if, elif, else.
- **Loops**: while, for.

```python
a = 1
b = 2

if a > b:
    print('a is greater than b')
elif a < b:
    print('a is less than b')
else:
    print('a is equal to b')

while a < 10:
    print(a)
    a += 1

# range is a built-in class that generates a sequence of numbers
for i in range(10):
    print(i)
```

### Functions

Functions are used to group code that performs a specific task. Functions can take input arguments and return output values. The basic syntax for defining a function in Python is:

```python
def my_function(a, b):
    return a + b

result = my_function(1, 2)
print(result)
```

Functions in Python are first-class objects, which means they can be passed as arguments to other functions, returned from other functions, and assigned to variables. This makes functions very flexible and powerful.

### Expressions

In programming languages (most of them) what's not a statement (i.e. a raw line of code that does something) is an expression. Expressions are the building blocks of statements. They are the smallest unit of computation in a program. Expressions can be combined to form more complex expressions, which can then be used to build statements.

The simplest expressions are the ones I showed you before: literals and variables. But expressions can also be more complex, like the ones you see in the following examples:

```python
a = lambda x: x + 1
b = a(1)
print(b)
```

In this example, `a` is a lambda function that takes an argument `x` and returns `x + 1`. We then call `a` with the argument `1` and assign the result to `b`. Finally, we print `b`, which is `2`.

Lambda functions are a way to define small, anonymous functions in Python. They are useful when you need a simple function for a short period of time. Their allocation is dynamic, so they are not stored in memory after they are used.

### Comprehensions

There's also a concept called "comprehensions" in Python. Comprehensions are a way to create sequences (lists, sets, dictionaries) in a concise way. They are a powerful feature of Python that allows you to write complex expressions in a single line of code. Comprehensions can be used in place of a list, set, or dictionary literal.

Here's an example of a list comprehension:

```python
squares = [x ** 2 for x in range(10)]
print(squares)
```

In this example, we create a list of squares of numbers from 0 to 9 using a list comprehension. The expression `x ** 2` is evaluated for each value of `x` in the range `0` to `9`, and the result is stored in the list `squares`.

Comprehensions can also be used with sets and dictionaries. Here's an example of a set comprehension:

```python
squares_set = {x ** 2 for x in range(10)}
print(squares_set)
```

And an example of a dictionary comprehension:

```python
names = ['Alice', 'Bob', 'Charlie']
last_names = ['Smith', 'Jones', 'Brown']
last_name_dict = {name: last_name for name, last_name in zip(names, last_names)}
print(squares_dict)
```

In the above example, we create a dictionary `last_name_dict` where the keys are the names from the `names` list and the values are the last names from the `last_names` list.

Note: if you're not familiar with the `zip` function, it's a built-in function that takes two or more sequences and "zips" them together into a single sequence of tuples, that is, it returns pairs of elements from the input sequences.

### Generators

Generators are a special kind of iterator in Python. They are used to create iterators in a more concise and readable way. Generators are similar to functions, but instead of using the `return` keyword to return a value, they use the `yield` keyword.

Here's an example of a generator that generates the Fibonacci sequence:

```python
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b
```

The `fibonacci` function is a generator that generates the Fibonacci sequence up to `n` numbers. It uses the `yield` keyword to return each number in the sequence. When the generator is called, it returns an iterator that can be used to iterate over the sequence.

It can be used like this:

```python
for i in fibonacci(10):
    print(i)
```

This will print the first 10 numbers in the Fibonacci sequence.