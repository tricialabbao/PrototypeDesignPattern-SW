# PrototypeDesignPattern-SW
A creational design pattern that creates new objects by cloning existing ones, avoiding the cost of creating objects from scratch.

## Overview

The pattern uses a registry (`AnimalRegistry`) to store and clone pre-configured prototype objects. Clients request copies through the registry rather than instantiating classes directly.

## Classes

### `Animal` (Interface)
Extends `Cloneable` and defines the contract for all animal types.
- `clone(): Animal` — returns a copy of the object
- `makeSound(): void` — animal-specific sound behavior
- `getType(): String` — returns the animal type name

### `AnimalRegistry`
Manages prototype instances and exposes factory methods.
- Stores prototypes: `sheepPrototype`, `cowPrototype`, `horsePrototype`
- `createSheep(String name): Animal`
- `createCow(): Animal`
- `createHorse(): Animal`

### Concrete Animals
| Class | Fields |
|-------|--------|
| `Sheep` | legs, sound, food, name |
| `Cow` | legs, sound, food |
| `Horse` | legs, sound, food, color |

### `TestAnimal`
Entry point. Uses `AnimalRegistry` to create animal instances via cloning.

## Benefits

- Avoids subclass proliferation for object creation
- Reduces initialization overhead for complex objects
- Clients remain decoupled from concrete implementations

# UML Class Diagram
![Image](https://github.com/tricialabbao/PrototypeDesignPattern-SW/blob/main/PrototypeDesignPattern.webp)
