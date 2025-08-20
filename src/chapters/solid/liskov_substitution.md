# Liskov Substitution Principle

"Functions that use pointers or references to a base class must be able to use objects of any derived class without knowing it."

The Liskov Substitution Principle (LSP) is a fundamental principle of object-oriented design within the S.O.L.I.D framework.

It states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.

This principle ensures that a derived class can stand in for its base class, promoting code reusability and robustness.

## Examples:

- Here is a simple example demonstrating LSP:

```python
class Bird:
    def fly(self):
        print("Flying")

class Sparrow(Bird):
    def chirp(self):
        print("Chirping")

def make_bird_fly(bird: Bird):
    bird.fly()  # This works for any object that is a Bird
    if isinstance(bird, Sparrow):
        bird.chirp()  # This works for Sparrows specifically

# Example usage:
sparrow = Sparrow()
make_bird_fly(sparrow)  # This will call fly() and chirp() for Sparrow
```

- And if we wanted to violate LSP:
```python
class Penguin(Bird):
    def fly(self):
        raise Exception("Penguins can't fly")  # Violates LSP

def make_bird_fly(bird: Bird):
    bird.fly()  # This will cause an exception if a Penguin is passed

# Example usage:
penguin = Penguin()
make_bird_fly(penguin)  # This will raise an exception
```