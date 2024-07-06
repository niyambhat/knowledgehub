---
sidebar_position: 1
---

### Foundation Puthon

```Python
def greet(name):
    """This function greets the given name."""
    print(f"Hello, {name}!")

Calling the function
greet("Alice")
```

## Variable Scope
```Python
def func():
    x = 10  # Local variable within the function
    print("Inside the function:", x)

x = 5  # Global variable

func()
print("Outside the function:", x)
```

## Data Structure - List:
```Python
fruits = ["apple", "banana", "cherry", "date"]
print(fruits)
```

## Data Structure - Tuples:

```Python
student = ("Alice", 21, "Computer Science")
print(student)
```

## Data Structure - Set:

This example creates a set called colors with four elements. Sets are unordered collections of unique elements. In this case, the duplicate entry "red" is automatically removed when printing the set.

```Python
colors = {"red", "blue", "green", "red"}
print(colors)
```

## Data Structure - Dictionary:
It is using key, value pair. 

```Python
student = {
    "name": "Alice",
    "age": 21,
    "major": "Computer Science"
}
print(student)
print(student["name"])
```