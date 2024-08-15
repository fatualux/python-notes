# Global vs. Local Variables

### Global Variables

Global variables are defined outside of any function or class and are accessible from any part of the code. They retain their value throughout the lifetime of the program.

#### Characteristics:
- Defined at the top level of a script or module.
- Accessible from any function or method within the module.
- Can be modified inside functions using the `global` keyword.

#### Example:

```python
x = 10  # Global variable

def print_global():
    print(x)  # Accessing global variable

def modify_global():
    global x
    x = 20  # Modifying global variable
```

### Local Variables

Local variables are defined within a function or method and are only accessible within that function or method. They are created when the function is called and destroyed when the function exits.

#### Characteristics:
- Defined inside a function or method.
- Accessible only within the function or method where they are declared.
- Cannot be accessed from outside the function or method.

#### Example:

```python
def example_function():
    y = 5  # Local variable
    print(y)  # Accessing local variable

example_function()
# print(y)  # This will raise an error because 'y' is not accessible outside the function
```

### Key Differences

- **Scope**: Global variables have global scope (accessible anywhere in the module), while local variables have local scope (accessible only within the function).
- **Lifetime**: Global variables exist for the duration of the program, whereas local variables exist only during the execution of the function.
- **Modification**: To modify a global variable within a function, use the `global` keyword; local variables can be freely modified within their own scope.

### Best Practices

- **Minimize Global Variables**: Overuse of global variables can make code harder to understand and maintain. Prefer using local variables when possible.
- **Use Descriptive Names**: Name variables clearly to indicate their purpose and scope, reducing confusion.
- **Encapsulation**: Use functions and classes to encapsulate and manage the scope of variables, keeping the global namespace clean and minimizing side effects.

