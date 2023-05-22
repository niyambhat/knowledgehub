---
sidebar_position: 2
---

## Object Oriented Programming

Let's explain the principles of Object-Oriented Programming (OOP) using examples in Python:

### Encapsulation: 
Encapsulation is the principle of bundling data and the methods that operate on that data together as a single unit, called a class. It allows us to hide the internal details of an object and provide a public interface for interacting with it. Here's an example:

```python
class Circle:
    def __init__(self, radius):
        self.radius = radius

    def calculate_area(self):
        return 3.14 * self.radius * self.radius

circle = Circle(5)
area = circle.calculate_area()
print(area)

```