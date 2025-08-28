# Liskov Substitution Principle

”What is wanted here is something like the following substitution 
property: If for each object o1 of type S there is an object o2 of type T 
such that for all programs P defined in terms of T, the behavior of P is 
unchanged when o1 is substituted for o2 then S is a subtype of T.”
(Barbara Liskov, Data Abstraction and Hierarchy)

Or in simplified form: 
”Subtypes must be substitutable for their base types.”

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

CONCLUSION:

Make sure that inheritance is about behavior, not about data.
Make sure that the contract of base types is adhered to.
Make sure to adhere to the required concepts.