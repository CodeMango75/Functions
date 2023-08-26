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
