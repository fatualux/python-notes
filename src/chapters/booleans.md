# Booleans

**Booleans** are used to represent true or false values (boolean algebra is the subset of algebra which variables are either true or false).

![booleans](../static/images/booleans.png)

Booleans are subclasses of integers, and are represented as **1** (*true*) and **0** (*false*); their type is `bool`. and they can be combined in Boolean expressions using the logical operators *and*, *or*, and *not*.

Example:

```python
int(False) # this outputs 0
int(True) # this outputs 1
bool(0) # this outputs False
bool(1) # this outputs True
bool(-9) # this outputs True, because -9 is non-zero
not False # this outputs True
True and False # this outputs False, because True and False are both non-zero
True and True # this outputs True, because True and True are both non-zero
True or False # this outputs True, because True or False is non-zero
3 + True # this outputs 4, because True is equal to 1
5 + False # this outputs 5, because False is equal to 0
```
