# Scopes

A **scope** is the textual region of a Python program, where a namespace is directly accessible.

In other words, a scope is a block of code where a particular variable can be accessed or modified.

Understanding scope is crucial for managing variable visibility and avoiding conflicts.

## The LEGB Rule

Python uses the **LEGB** rule to define the scope of variables.
LEGB stands for Local, Enclosing, Global, and Built-in.

There are different types of scopes in Python:

1. Local Scope

Variables defined within a function are in the local scope.
They are accessible only within that function. Local variables are created when the function is called and are destroyed when the function terminates.

python

def my_function():
    local_var = 10  # Local scope
    print(local_var)

my_function()  # Outputs: 10
print(local_var)  # Raises NameError: name 'local_var' is not defined

2. Enclosing (or Nonlocal) Scope

This scope refers to variables in the enclosing function, which is the function that contains another function. If a nested function modifies a variable in the enclosing function, the nonlocal keyword is used.

python

def outer_function():
    enclosing_var = 20
    
    def inner_function():
        nonlocal enclosing_var
        enclosing_var = 30
        print(enclosing_var)  # Outputs: 30
    
    inner_function()
    print(enclosing_var)  # Outputs: 30

outer_function()

3. Global Scope

Variables defined at the top level of a script or module are in the global scope. They are accessible from any part of the code after they are defined. To modify a global variable within a function, the global keyword is used.

python

global_var = 40  # Global scope

def my_function():
    global global_var
    global_var = 50
    print(global_var)  # Outputs: 50

my_function()
print(global_var)  # Outputs: 50

4. Built-in Scope

This is the scope that contains names that are preassigned in Python. These names are always available and include functions like print(), len(), etc.

python

print(len("hello"))  # 'print' and 'len' are built-in functions

Scope Resolution: The LEGB Rule

When Python encounters a variable, it searches for it in the following order:

    Local: The innermost scope, which is the local scope.
    Enclosing: Any enclosing functions' scopes, from inner to outer.
    Global: The next-to-last scope, which is the module's global scope.
    Built-in: The outermost scope, which is the built-in names.

Example to Illustrate LEGB Rule

python

x = "global"

def outer():
    x = "enclosing"
    
    def inner():
        x = "local"
        print(x)  # Outputs: "local"
    
    inner()
    print(x)  # Outputs: "enclosing"

outer()
print(x)  # Outputs: "global"

Summary

    Local Scope: Variables defined within a function.
    Enclosing Scope: Variables in the local scope of enclosing functions.
    Global Scope: Variables defined at the top level of a script/module.
    Built-in Scope: Predefined names in Python.

Understanding and managing scopes effectively helps in writing clear and bug-free code, especially in larger projects.
