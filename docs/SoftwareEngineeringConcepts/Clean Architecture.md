---
sidebar_position: 3
---

# Clean Architecture

This article has been derived from the worshops done by Uncle Bob (Robert C. Martin), a renowned software engineer .
Only some parts have been discussed in this article which i tend to use during coding. According to the author, clean code refers to code that is easy to read, understand, and maintain. He has written extensively on the topic in his book "Clean Code: A Handbook of Agile Software Craftsmanship." Here are some key principles and characteristics of clean code as advocated by Uncle Bob:

What is clean coding? 
Clean clode is characterized by following:

Readability: Clean code should be easy to read and understand. It should convey its intent clearly and allow other developers to comprehend its purpose without much effort. This is achieved through the use of descriptive names, consistent formatting, and minimalism.

Simplicity: Clean code is simple and straightforward. It follows the principle of "Do One Thing and Do It Well" (DOTADIW), where each component or function should have a clear and single responsibility. Complex logic should be broken down into smaller, manageable pieces.

Expressiveness: Clean code is expressive and self-explanatory. It uses meaningful names for variables, functions, and classes, making the code more understandable and reducing the need for comments. It also employs idiomatic language constructs and avoids unnecessary abstractions.

Minimal duplication: Clean code minimizes duplication by following the DRY (Don't Repeat Yourself) principle. Duplication leads to maintenance issues and increases the chances of introducing bugs. Repeated code should be refactored into reusable functions or extracted into shared modules.

Testing and maintainability: Clean code is designed to be easily testable and maintainable. It is modular and loosely coupled, allowing changes to be made to specific components without affecting the entire system. It should have well-defined interfaces, well-encapsulated functionality, and thorough automated test coverage.

Consistent formatting: Clean code follows a consistent and agreed-upon formatting style. This includes indentation, spacing, line length, and naming conventions. Consistent formatting enhances readability and helps developers quickly understand the structure and flow of the code.

Small, focused functions and classes: Clean code promotes the use of small functions and classes that focus on specific tasks. Functions should be short and do one thing, while classes should have a single responsibility.

## How to adapt to Clean Architecture while coding?

1. Refactor for concise code: Long code is generally not desirable. Functions should be refactored to serve a specific purpose, focusing on doing one thing well. This improves readability and maintainability.

2. Self-descriptive functions: Functions should have meaningful names that accurately describe their purpose and functionality. When functions are named appropriately, comments become unnecessary as the code itself becomes self-explanatory.

3. Reasons to avoid "switch" statements: Switch statements can have drawbacks such as poor scalability, maintainability, and testability. They violate the Open-Closed Principle, which emphasizes the importance of being able to extend functionality without modifying existing code. Alternative design patterns, like polymorphism, provide more flexibility and maintainability.

4. Limit side effects: It is important to minimize excessive side effects in code. Excessive side effects can introduce unpredictability, making code harder to debug and maintain. By controlling side effects, code becomes more predictable, easier to test, and less prone to bugs.

5. DRY (Don't Repeat Yourself): Avoid code duplication by following the DRY principle. Duplicating code leads to maintenance challenges and increases the likelihood of introducing bugs. Instead, extract common functionality into reusable functions or modules.

6. Consistent naming conventions: Adopt a consistent naming convention for variables to improve code clarity and readability. Meaningful and descriptive variable names make it easier for others to understand the code and reduce the need for comments.


TBC . . . .

