# Factory Method Example

```python
from abc import ABC, abstractmethod
from enum import Enum


class ShipsEnum(Enum):
    MILLENIUMFALCON = "MilleniumFalcon"
    UNSCInfinity = "UNSCInfinity"
    USSENTERPRISE = "USSEnterprise"
    SERENITY = "Serenity"


class SpaceShip(ABC):
    def __init__(
        self,
        position: tuple[int, int],
        size: tuple[int, int],
        displayName: str,
        speed: int = 0,
    ):
        self.position = position
        self.size = size
        self.displayName = displayName
        self.speed = speed

    @abstractmethod
    def fly(self) -> str:
        pass

    @abstractmethod
    def shoot(self) -> str:
        pass


class MilleniumFalcon(SpaceShip):
    def __init__(
        self,
        position: tuple[int, int],
        size: tuple[int, int],
        displayName: str,
        speed: int = 0,
    ):
        super().__init__(position, size, displayName, speed)

    def fly(self):
        return "The Millenium Falcon is flying through hyperspace!"

    def shoot(self):
        return "The Millenium Falcon fires its blasters!"


class UNSCInfinity(SpaceShip):
    def __init__(
        self,
        position: tuple[int, int],
        size: tuple[int, int],
        displayName: str,
        speed: int = 0,
    ):
        super().__init__(position, size, displayName, speed)

    def fly(self):
        return "The UNSC Infinity is cruising through space!"

    def shoot(self):
        return "The UNSC Infinity launches its MAC rounds!"


class USSEnterprise(SpaceShip):
    def __init__(
        self,
        position: tuple[int, int],
        size: tuple[int, int],
        displayName: str,
        speed: int = 0,
    ):
        super().__init__(position, size, displayName, speed)

    def fly(self):
        return "The USS Enterprise is exploring the galaxy!"

    def shoot(self):
        return "The USS Enterprise fires its phasers!"


class Serenity(SpaceShip):
    def __init__(
        self,
        position: tuple[int, int],
        size: tuple[int, int],
        displayName: str,
        speed: int = 0,
    ):
        super().__init__(position, size, displayName, speed)

    def fly(self):
        return "The Serenity is gliding through the 'verse!"

    def shoot(self):
        return "The Serenity fires its pulse cannons!"


class SpaceShipFactory:
    @staticmethod
    def create_ship(
        ship_type: ShipsEnum,
        position: tuple[int, int],
        size: tuple[int, int],
        displayName: str,
        speed: int = 0,
    ) -> SpaceShip:
        if ship_type == ShipsEnum.MILLENIUMFALCON:
            return MilleniumFalcon(position, size, displayName, speed)
        elif ship_type == ShipsEnum.UNSCInfinity:
            return UNSCInfinity(position, size, displayName, speed)
        elif ship_type == ShipsEnum.USSENTERPRISE:
            return USSEnterprise(position, size, displayName, speed)
        elif ship_type == ShipsEnum.SERENITY:
            return Serenity(position, size, displayName, speed)
        else:
            raise ValueError("Unknown ship type")
```