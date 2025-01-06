---
slug: solid-principles
title: SOLID Principles
tags: [clean-code]
sidebar_position: 3
---

# SOLID Principles

The SOLID principles are a set of five design principles intended to make software designs more understandable, flexible, and maintainable. These principles are especially useful in object-oriented design and programming. Let's dive into each principle with explanations and examples.

## S - Single Responsibility Principle (SRP)

A class should have only one reason to change, meaning it should have only one job or responsibility. Ensure each class has only one responsibility.

**Refactoring Ideas**: Look for classes that handle more than one task, like managing data and handling UI. Break these classes into smaller classes, each with a single responsibility.

### Example:

```python
# Before applying SRP
class Invoice:
    def calculate_total(self):
        # calculate total
        pass
    
    def print_invoice(self):
        # print the invoice
        pass
    
    def save_to_database(self):
        # save the invoice to the database
        pass

# After applying SRP
class Invoice:
    def calculate_total(self):
        # calculate total
        pass

class InvoicePrinter:
    def print_invoice(self, invoice):
        # print the invoice
        pass

class InvoiceRepository:
    def save_to_database(self, invoice):
        # save the invoice to the database
        pass
```
## O - Open/Closed Principle (OCP)

Software entities should be open for extension but closed for modification.

**Refactoring Ideas:** Look for if-else chains or switch statements. Use inheritance or interfaces to allow new functionality to be added without changing existing code.

```python
# Before OCP
class Rectangle:
    def area(self):
        # calculate area
        pass

class AreaCalculator:
    def calculate_area(self, shapes):
        total_area = 0
        for shape in shapes:
            if isinstance(shape, Rectangle):
                total_area += shape.area()
            # More shape types would require modifying this method
        return total_area

# After applying OCP
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def area(self):
        # calculate rectangle area
        pass

class Circle(Shape):
    def area(self):
        # calculate circle area
        pass

class AreaCalculator:
    def calculate_area(self, shapes):
        total_area = 0
        for shape in shapes:
            total_area += shape.area()
        return total_area
```

## L - Liskov Substitution Principle (LSP)
Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.

**Refactoring Ideas:** Look for subclasses that override methods in a way that changes expected behavior. Redesign the class hierarchy or use interfaces to ensure correct substitutability.

```python
# Correct LSP
class Bird:
    def fly(self):
        pass

class Sparrow(Bird):
    def fly(self):
        # Sparrow flying logic
        pass

class Ostrich(Bird):
    def fly(self):
        raise NotImplementedError("Ostrich can't fly")

# Ostrich violates LSP because it cannot fully substitute Bird
# To fix this, consider changing the design
```

## I - Interface Segregation Principle (ISP)
Clients should not be forced to depend on interfaces they do not use.

**Refactoring Ideas:** Look for interfaces that have methods unused by some clients.
Refactor: Break these interfaces into smaller, more specific ones.

```python
# Before ISP
class Worker:
    def work(self):
        pass
    
    def eat(self):
        pass

# After applying ISP
class Workable:
    def work(self):
        pass

class Eatable:
    def eat(self):
        pass

class Worker(Workable, Eatable):
    def work(self):
        # working logic
        pass
    
    def eat(self):
        # eating logic
        pass

class Robot(Workable):
    def work(self):
        # working logic for robot
        pass
```

## D - Dependency Inversion Principle (DIP)
High-level modules should not depend on low-level modules. Both should depend on abstractions.

**Refactoring Ideas:** Look for classes that directly instantiate other classes.
Refactor: Use dependency injection or design patterns like Factory or Strategy to depend on abstractions.

```python
# Before DIP
class LightBulb:
    def turn_on(self):
        pass
    
    def turn_off(self):
        pass

class Switch:
    def __init__(self, bulb):
        self.bulb = bulb
    
    def operate(self):
        # operate logic
        pass

# After applying DIP
class Switchable:
    def turn_on(self):
        pass
    
    def turn_off(self):
        pass

class LightBulb(Switchable):
    def turn_on(self):
        pass
    
    def turn_off(self):
        pass

class Switch:
    def __init__(self, device: Switchable):
        self.device = device
    
    def operate(self):
        # operate logic
        pass
```
By adhering to these principles, you can create more robust, scalable, and maintainable software. Each principle contributes to reducing dependencies and improving the flexibility of your codebase.

| Principle                  | Common Pitfalls                                          | When It Can't Be Avoided                      | How Solving One Violates Another |
|----------------------------|----------------------------------------------------------|-----------------------------------------------|----------------------------------|
| Single Responsibility (SRP)| Over-segmentation leading to too many small classes      | In simple applications where over-segmentation adds complexity | Solving SRP might increase the number of classes, complicating OCP |
| Open/Closed (OCP)          | Overuse of inheritance and polymorphism                  | When performance is critical and polymorphism introduces overhead | Excessive use of interfaces for OCP can violate ISP |
| Liskov Substitution (LSP)  | Misuse of inheritance, leading to incorrect substitutability | When a subclass naturally cannot behave like its parent | Enforcing LSP might lead to complex class hierarchies, impacting SRP |
| Interface Segregation (ISP)| Creating too many interfaces, leading to management overhead | In very simple systems where a single interface suffices | Splitting interfaces for ISP may complicate implementations, affecting SRP and OCP |
| Dependency Inversion (DIP) | Overuse of abstract classes and interfaces               | In small, non-scalable projects where simplicity is key | Applying DIP can increase the complexity of class structures, potentially impacting SRP |


Navigating the SOLID principles requires a balance between maintaining design integrity and practical application. While each principle offers distinct advantages, understanding their interdependencies and potential conflicts is key to effective software design. Always consider the context and scale of your project to apply these principles judiciously.