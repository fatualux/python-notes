# Methods

In Python, a **method** is a function that is associated with an object.

![Methods](../static/images/methods.png)

It defines the behavior of the objects of a class.

Methods are defined inside the class definition and are accessed via instances of the class (objects).

Methods can take parameters (like regular functions) and operate on the object's internal state.

Example (method `howl` from the `wolf` class):

```python
class Wolf:
    def howl(self):
        print("Wooooooo!")
        self.howl()
        # this will print "Wooooooo!"
```
