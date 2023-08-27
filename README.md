# Functions 
* Functions are set of instructions that tells interpreter what to do. That are called by the caller. 
* Functions are denoted by `def` keyword. (User Defined Function)

* *Syntax* of **User Defined Function** is as follows:
```
def custom_name(parameter1,parameter2,...parameterN): 
   Statement1
   Statement2
   ...
   ...
   ...
   StatementN
custom_name() #Function Call 
```


* Functions in Python are of two types:

1. **Pre Defined Functions**:

* These are the functions that are defined already and injected to python interpreter.
* The few examples of pre defined functions are: `print()` , `findall()` , `input()` , `id()` etc.
These functions are pre built in. 
* Predefined functions, also known as built-in functions, are functions that are already available in Python. These functions are provided by the Python language itself and can be used directly without having to create them.

```
text = "Hello, world!"
length = len(text)  # Using the built-in len() function to calculate the length of the string
print(length)  # Output: 13

```

2. **User Defined Functions**: 
* User defuned Functions are functions that are built separately by users. 
* User Defined Functions are denoted by `def()` keyword followed by *Function Name*
* User-defined functions are functions that you create yourself to perform specific tasks. You give these functions a name, define what they should do, and then you can use them in your code whenever needed.
```
def calculate_square(number):
    square = number * number
    return square

result = calculate_square(5)  # Calling our user-defined function with the argument 5
print(result)  # Output: 25

```


**Common Properties**:
The common properties of the above 2 functions are: 

* `return`
* non-return
* required Parameters
* optional parameters
* Default parameters
* Positional Arguments
* Key Value Parameters
* `pass` unlimited optional arguments
* `pass` unlimited **key=value**


## Return Function:
* Return function is a function that can be assigned to a variable. 
* A return function is a type of function that computes a value and sends it back as the result of the function call. 
* The `return` statement is used to specify the value that the function should return.

```
def add(a, b):
    result = a + b
    return result

sum_result = add(3, 5)  # The function returns 8, which is assigned to sum_result

```

## Non Return Function:
* Non Return Function is not assigned to a vairable. 
* A non-return function is a type of function that performs a certain task or set of tasks but doesn't produce a value that can be captured or used elsewhere in the program. 
* These functions are primarily used for their side effects, such as printing output or modifying data.

```
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # This function prints "Hello, Alice!"
```
The `greet` function doesn't return a value; it only prints a message to the console.

### Difference Between Return and Print

* The `return` statement is used within a function to specify the value that should be sent back to the caller. This value can be assigned to a variable or used in further computations.
* The `print` statement is used to display information to the console. It doesn't affect the flow of the program or provide a value that can be captured.

## Parameters vs Arguments

**Parameters**:

* Parameters are placeholders or variables listed in the function definition. 
* They act as local variables within the function and serve as receptacles for the values that are passed into the function when it's called. 
* In simpler words, parameters are like empty slots in the function that you expect to be filled with values when the function is used.

```
def greet(name):
    print(f"Hello, {name}!")

# 'name' is the parameter of the 'greet' function
```
Here, `name` is the parameter of the `greet` function. It's a placeholder for the actual name that will be passed to the function when it's called.

**Arguments**

* Arguments are the actual values that are passed to a function when it is called. 
* They are the real data that fills in the placeholders (parameters) defined in the function.
In simpler words, arguments are the values you provide to a function when you use it.

```
def add(a, b):
    result = a + b
    return result

# 3 and 5 are the arguments passed to the 'add' function
sum_result = add(3, 5)
```
Remember:

* You define parameters in the function definition.
* You provide arguments when you call the function.

### Optional vs Required Parameters

**Required Parameters**
* Required parameters are parameters that must be provided with a value when calling a function.
* These parameters are essential for the function to work correctly, and not providing a value will result in an error.
```
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")
```
In this example, the `name` parameter in the `greet` function is required. When you call the function with `greet("Alice")`, you provide a value for the required parameter name.

**Optional Parameters** 
* Optional parameters (also known as *default parameters*) are parameters for which a default value is specified in the function definition. 
* If you don't provide a value for an optional parameter when calling the function, it will use the default value. 
* However, you can still provide a value to override the default if needed.

```
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()          # Output: Hello, Guest! (Using the default value)
greet("Alice")   # Output: Hello, Alice! (Providing a value to override the default)
```
In this example, the `name` parameter in the `greet` function is optional because it has a default value of "Guest". If you don't provide a value, it will use the default. But if you do provide a value, it will use that value instead.

**Can their be cases where parameters are require but we dont pass arguments OR its necessary for arguments to be simultaneously be inline with parameters?**

Yes, there can be cases where parameters are required, but you don't pass arguments when calling a function. However, it's important to understand that in such cases, not providing arguments will result in an error.
```
def multiply(a, b):
    result = a * b
    return result

# Uncommenting the line below will result in an error
# product = multiply()
```
In this example, the `multiply` function requires two parameters `a` and `b` to be provided with values. If you try to call the function without providing arguments like `multiply()`, you will get a TypeError because the function expects two arguments but receives none.

If you intend to make certain parameters required and ensure that the function won't work without them, you should provide appropriate arguments when calling the function.

On the other hand, for optional parameters (parameters with default values), you can call the function without providing arguments, and it will use the default values:

```
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()  # Output: Hello, Guest!
```
In this case, the `name` parameter is optional, so if you don't provide     an argument, the default value `"Guest"` will be used. 

In summary:

* For required parameters, you must provide arguments with values when calling the function, otherwise, you'll encounter an error.
* For optional parameters, you can omit providing arguments, and the function will use the default values specified in the parameter list.

## Positional Arguments

* Positional arguments in Python refer to the arguments that are passed to a function in the order in which they are defined in the function's parameter list. 
* When you call a function and provide values for its parameters without explicitly specifying the parameter names, Python assigns these values based on their position.
```
def add(a, b):
    return a + b

result = add(3, 5)
print(result)  # Output: 8
```
In this example above, 3 is assigned to the parameter `a`, and 5 is assigned to the parameter `b` because of their respective positions.
* Positional arguments are straightforward and intuitive to use, but it's important to remember that their order matters.
* If you change the order of arguments in the function call, the values will be assigned to different parameters
```
result = add(5, 3)
print(result)  # Output: 8
```
However, using positional arguments only will lead to confusion and this is where Named Arguments come in to play.


## Arbitrary Arguments (*args)



## Keyword Arguments (key=value)
* In Python, "named arguments" and "keyword arguments" refer to the same concept. Both terms are often used interchangeably to describe a way of passing arguments to a function by explicitly mentioning the parameter names along with the values.
* When you use named or keyword arguments, you provide the parameter names followed by the values you want to assign to those parameters.
* This approach allows you to pass arguments in any order, making your code more readable and reducing the chances of confusion, especially when dealing with functions that have many parameters.
```
def greet(name, age):
    print(f"Hello, {name}! You are {age} years old.")

greet(name="Alice", age=30)
```
In this example, the function `greet` takes two parameters: `name` and `age`. When calling the function, you provide the values for these parameters using their names as keywords. This way, the order in which you provide the arguments doesn't matter.
* Named/keyword arguments are particularly useful when a function has many parameters, and you want to make your code more self-explanatory.

* When using named or keyword arguments, position does not matter at all:
```
def example_function(a, b, c):
    print(f"a: {a}, b: {b}, c: {c}")

example_function(b=2, a=1, c=3)
```
* However, both keyword and positional arguments have their place in Python programming, and the choice should be based on the specific needs of your code.

## Arbitrary Keywords Arguments (**kwargs)
* Arbitrary arguments, often referred to as "varargs" (variable number of arguments), allow you to pass a variable number of arguments to a function in Python.
* This can be useful when you're uncertain about the number of arguments you need to provide or when you want to create functions that can handle a dynamic number of inputs.
*  Python provides two ways to implement arbitrary arguments in function definitions: ***args** and ****kwargs**.

### *Arbitrary Positional Arguments(args)*:
* The *args syntax allows you to pass a variable number of **positional** arguments to a function. 
* These arguments are collected into a *tuple* within the function. You can use any name you   like for `*args`, but the asterisk () is required to unpack the arguments.
```
def print_args(*args):
    for arg in args:
        print(arg)

print_args(1, 2, 3)  # Output: 1 2 3
print_args('a', 'b')  # Output: a b
```

### *Arbitrary Keyword Arguments(kwargs)*:
* The `**kwargs` syntax allows you to pass a variable number of keyword arguments to a function.
* These arguments are collected into a dictionary within the function
* Similar to *args, the double asterisks () are required to unpack the arguments.
```
def print_kwargs(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_kwargs(name='Alice', age=30)  # Output: name: Alice, age: 30
print_kwargs(city='New York')       # Output: city: New York
```
You can also use both *args and **kwargs in the same function definition, but *args should appear before **kwargs:
```
def combined_example(arg1, *args, kwarg1=None, **kwargs):
    print(f"arg1: {arg1}")
    print(f"args: {args}")
    print(f"kwarg1: {kwarg1}")
    print(f"kwargs: {kwargs}")

combined_example(1, 2, 3, kwarg1='value', name='Alice', age=30)
```
In this example, `arg1` is a required positional argument, `*args` captures additional positional arguments, `kwarg1` is a keyword argument with a default value, and `**kwargs` captures additional keyword arguments.

* Arbitrary arguments provide flexibility, making it possible to create functions that can accept a varying number of inputs without needing to specify each argument explicitly.

**NOTE**
When you use the `**kwargs` syntax in a function definition, the arguments that are passed as keyword arguments are collected into a **dictionary** within the function.  
This dictionary is then accessible within the function, and it contains the keyword argument names as keys and their corresponding values.

```
def process_kwargs(**kwargs):
    print(kwargs)
    print(type(kwargs))

process_kwargs(name='Alice', age=30, city='New York')
```
```
# output
{'name': 'Alice', 'age': 30, 'city': 'New York'}
<class 'dict'>
```
You can then use this dictionary to perform various operations within the function, such as iterating over the keys and values, accessing specific values using their keys, and so on. This feature is particularly useful when you want to create functions that are highly customizable and can accept a variable number of named arguments.


# Lambda Functions
Lambda is: 
* One Line Function
* Without Name (Anonymous name)
* it didnt use before nor it'll be used afterwards
This is called *Lambda Functions*
* A lambda function can take any number of arguments, but can only have one expression.
* *Syntax* of Lambda Function is:

```lambda arguments : expression```
* `lambda` is the *keyword*
   * arguments may be any for example `x,y` 
   * then any *expression* for example `x+y` separated by *colon* `:`

```
a = lambda x,y,z : x+y+x
print(a(5,5,5))
```
* Lambda function is returned by default. No need to return it separately.
* Use `lambda` function when you require an anonymous function for a **Short Period of Time** 

### Why Use Lambda Function?

* Lambda functions are efficient whenever you want to create a function that will only contain simple expressions 
* that is, expressions that are usually a single line of a statement.
* They're also useful when you want to use the function once.

```
data = [[1,'X','E'],
        [3,'Y','G'],
        [2,'Z','F']]
print(sorted(data, key=lambda x:x[0]))
print(sorted(data, key=lambda x:x[1]))
print(sorted(data, key=lambda x:x[2]))
```
In the above example, `x` on the first instance is the matrix of data and other `x` is the column of the matrix and `[]`  passes the index of the **columns**. 

* Lambda functions are useful for creating functions on-the-fly and are often employed with functions like `map()`, `filter()`, and `sorted()` for efficient code.




