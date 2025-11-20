# Factory Method Example

```python
from abc import ABC, abstractmethod
from enum import Enum
from typing import Type


class ShipsEnum(Enum):
    MILLENIUM_FALCON = "MilleniumFalcon"
    UNSC_INFINITY = "UNSCInfinity"
    USS_ENTERPRISE = "USSEnterprise"
    SERENITY = "Serenity"


class SpaceShipFactory:
    _registry: dict[ShipsEnum, Type["SpaceShip"]] = {}

    @classmethod
    def register(cls, ship_type: ShipsEnum, ship_class: Type["SpaceShip"]):
        cls._registry[ship_type] = ship_class

    @classmethod
    def create_ship(
        cls,
        ship_type: ShipsEnum,
        position: tuple[int, int],
        size: tuple[int, int],
        display_name: str,
        speed: int = 0,
    ) -> "SpaceShip":
        try:
            ship_class = cls._registry[ship_type]
            return ship_class(position, size, display_name, speed)
        except KeyError:
            raise ValueError(f"Unknown ship type: {ship_type}")


class SpaceShip(ABC):
    def __init__(
        self,
        position: tuple[int, int],
        size: tuple[int, int],
        display_name: str,
        speed: int = 0,
    ):
        self.position = position
        self.size = size
        self.display_name = display_name
        self.speed = speed

    @abstractmethod
    def fly(self) -> str:
        pass

    @abstractmethod
    def shoot(self) -> str:
        pass


class MilleniumFalcon(SpaceShip):
    def fly(self):
        return "The Millenium Falcon is flying through hyperspace!"

    def shoot(self):
        return "The Millenium Falcon fires its blasters!"


SpaceShipFactory.register(ShipsEnum.MILLENIUM_FALCON, MilleniumFalcon)


class UNSCInfinity(SpaceShip):
    def fly(self):
        return "The UNSC Infinity is cruising through space!"

    def shoot(self):
        return "The UNSC Infinity launches its MAC rounds!"


SpaceShipFactory.register(ShipsEnum.UNSC_INFINITY, UNSCInfinity)


class USSEnterprise(SpaceShip):
    def fly(self):
        return "The USS Enterprise is exploring the galaxy!"

    def shoot(self):
        return "The USS Enterprise fires its phasers!"


SpaceShipFactory.register(ShipsEnum.USS_ENTERPRISE, USSEnterprise)


class Serenity(SpaceShip):
    def fly(self):
        return "The Serenity is gliding through the 'verse!"

    def shoot(self):
        return "The Serenity fires its pulse cannons!"


SpaceShipFactory.register(ShipsEnum.SERENITY, Serenity)
```

## Brief explaination

### Why Using a Registry Is Better Than Using Many if/elif Conditions

A conditional factory looks like this:

```python
if ship_type == ShipsEnum.MILLENIUM_FALCON:
return MilleniumFalcon(...)
elif ship_type == ShipsEnum.UNSC_INFINITY:
return UNSCInfinity(...)
elif ship_type == ShipsEnum.USS_ENTERPRISE:
return USSEnterprise(...)
...
```

This works, but it has a big problem: every time you add a new ship, you must edit the factory and add a new elif.

This makes the factory grow endlessly and violates the Open/Closed Principle (your code should be open for extension, but closed for modification).

Infact, the conditional factory must be modified every time you add a ship.

The Registry Pattern Fixes the Problem: instead of writing conditionals, we store ship classes inside a dictionary:

```python
_registry = {
ShipsEnum.MILLENIUM_FALCON: MilleniumFalcon,
ShipsEnum.UNSC_INFINITY: UNSCInfinity,
ShipsEnum.USS_ENTERPRISE: USSEnterprise,
ShipsEnum.SERENITY: Serenity,
}
```

Now the factory becomes much simpler:

```python
ship_class = cls._registry[ship_type]
return ship_class(position, size, display_name, speed)
```

Why is this better?

Because you no longer modify the factory logic: you only update the registry, not the function that creates objects.

This keeps the factory small, clean, and scalable.

#### The Core Idea

The factory no longer needs to know anything about the ships.

It just:

- Looks up the class

- Instantiates the object

The creation logic never changes.

#### Adding a New Ship Using a Registry

With the old method, you needed to modify 3 places.

With a registry, you only add this:

```PYTHON
SpaceShipFactory._registry[ShipsEnum.NEW_SHIP] = NewShipClass
```

No conditions. No modifications to the factory logic.

#### Auto-Registration

You can let ships register themselves:

```python
class SpaceShipFactory:
registry = {}

@classmethod
def register(cls, enum, ship_class):
    cls.registry[enum] = ship_class
```

Then each ship registers itself:

```
class MilleniumFalcon(SpaceShip):
...

SpaceShipFactory.register(ShipsEnum.MILLENIUM_FALCON, MilleniumFalcon)
```
