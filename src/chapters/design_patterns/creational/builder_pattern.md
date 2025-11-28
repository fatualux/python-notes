# Builder Pattern

## Overview

The Builder Pattern is a creational design pattern that allows for the encapsulation of the reusable logic involved in constructing complex objects.

### What Constitutes a Complex Object?

Complex objects typically have the following characteristics:

1. **Composition of Distinct Parts**: These objects are composed of multiple, distinct components that contribute to their overall structure and functionality.
2. **Defined Relationships**: There exists a well-defined relationship between the various components, dictating how they interrelate and contribute to the whole object.

### Key Principles of the Builder Pattern

The Builder Pattern is grounded in several core principles:

1. **Separation of Construction and Representation**: This principle emphasizes the decoupling of the construction process of an object from the representation of that object, allowing developers to focus on each aspect independently.

2. **Flexibility in Construction Process**: The design should be structured such that the same construction process can yield different representations of the object. This is particularly useful for creating variations of the same type of object based on differing requirements or contexts.

### Additional Information

- **Use Cases**: The Builder Pattern is particularly useful in scenarios where a class needs to be instantiated with a large number of parameters. It helps manage the complexity by allowing step-by-step construction.
  
- **Implementations**: In practice, the Builder Pattern typically involves a `Builder` class which constructs the complex object and a `Director` class that governs the construction process. The client interacts with the Builder to create specific representations of the complex object.

- **Advantages**:
    - Enhances code readability and maintainability.
    - Reduces the likelihood of errors during object creation by enforcing a step-by-step approach.
    - Makes it easier to add new configurations without affecting existing code.

- **Example**: Consider the following scenario: Imagine that you are coding the process of building a house for a video game. A house can be a complex object with numerous attributes, which may include:

    1. Walls
    2. Windows
    3. Floors
    4. Garage
    5. Swimming Pool
    6. Doors
    7. Backyard
    8. Garden
    9. Basement
    10. Roof

This structure reflects a hierarchy of components that make up the house, each contributing to its overall functionality and appearance.

To design this object in a way that adheres to the Builder Pattern principles, you might create a `House` class along with a `HouseBuilder` to simplify the construction process. Instead of having a long and complex constructor for the `House` class, you could implement something like this:

```python
class House:
    def __init__(self, walls, windows, floors, garage, swimming_pool, doors, backyard, garden, basement, roof):
        self.walls = walls
        self.windows = windows
        self.floors = floors
        self.garage = garage
        self.swimming_pool = swimming_pool
        self.doors = doors
        self.backyard = backyard
        self.garden = garden
        self.basement = basement
        self.roof = roof

class HouseBuilder:
    def __init__(self):
        self.walls = 0
        self.windows = 0
        self.floors = 0
        self.garage = False
        self.swimming_pool = False
        self.doors = 0
        self.backyard = False
        self.garden = False
        self.basement = False
        self.roof = False

    def set_walls(self, walls):
        self.walls = walls
        return self

    def set_windows(self, windows):
        self.windows = windows
        return self

    def set_floors(self, floors):
        self.floors = floors
        return self

    def add_garage(self):
        self.garage = True
        return self

    def add_swimming_pool(self):
        self.swimming_pool = True
        return self

    def set_doors(self, doors):
        self.doors = doors
        return self

    def add_backyard(self):
        self.backyard = True
        return self

    def add_garden(self):
        self.garden = True
        return self

    def add_basement(self):
        self.basement = True
        return self

    def add_roof(self):
        self.roof = True
        return self

    def build(self):
        return House(self.walls, self.windows, self.floors, self.garage, self.swimming_pool, self.doors, self.backyard, self.garden, self.basement, self.roof)

# Example client code
builder = HouseBuilder()
my_house = (builder.set_walls(4)
               .set_windows(10)
               .set_floors(2)
               .add_garage()
               .add_swimming_pool()
               .set_doors(3)
               .add_backyard()
               .add_garden()
               .add_basement()
               .add_roof()
               .build())
```

### Conclusion

The Builder Pattern offers a robust solution for constructing complex objects in a flexible and organized manner, ensuring clarity and maintainability in your codebase.
