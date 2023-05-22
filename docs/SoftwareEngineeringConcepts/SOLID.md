---
sidebar_position: 4
---

# SOILD Design principles

The SOLID principles are a set of five design principles that promote good software architecture and modular design. They were introduced by Robert C. Martin (Uncle Bob) and are widely regarded as best practices in object-oriented programming. Here is a brief explanation of each principle:

1. Single Responsibility Principle (SRP): This principle states that a class or module should have only one reason to change. It means that a class should have a single responsibility or purpose. By adhering to this principle, we keep our code focused, modular, and easier to understand, test, and maintain.Here's a simple Python example that demonstrates the Single Responsibility Principle (SRP):

```Python
class Calculator:
    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def multiply(self, a, b):
        return a * b

    def divide(self, a, b):
        if b == 0:
            raise ValueError("Cannot divide by zero")
        return a / b

class Logger:
    def log(self, message):
        print(message)

calculator = Calculator()
logger = Logger()

result = calculator.add(5, 3)
logger.log(f"The result is: {result}")
```
In this example, we have two separate classes, Calculator and Logger, each with a single responsibility:


2. Open-Closed Principle (OCP): The OCP states that software entities (classes, modules, functions) should be open for extension but closed for modification. It means that we should design our code in a way that allows us to add new functionality without modifying existing code. This promotes code reuse, modularity, and easier maintenance.
Here's a Python example that illustrates the Open-Closed Principle (OCP):

```JSX
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

def calculate_total_area(shapes):
    total_area = 0
    for shape in shapes:
        total_area += shape.area()
    return total_area

rectangle = Rectangle(4, 5)
circle = Circle(3)

shapes = [rectangle, circle]
total_area = calculate_total_area(shapes)
print(f"Total area: {total_area}")
```
In this example, we have a base Shape class with an abstract area method. This class serves as the foundation for different shapes. Two specific shapes, Rectangle and Circle, are derived from the Shape class.

By adhering to the Open-Closed Principle, the Shape class is open for extension but closed for modification. We can add new shapes by creating new classes that inherit from Shape without modifying the existing code. In this example, we added a Rectangle and Circle class, each with its own implementation of the area method.

The calculate_total_area function demonstrates code that is open for extension. It takes a list of shapes as input and calculates the total area by iterating through the shapes and calling their area methods. We can add new shapes to the list without modifying the calculate_total_area function.

By designing our code in this way, we achieve code reusability, modularity, and easier maintenance. We can add new functionality by creating new classes without modifying the existing code, promoting a more flexible and scalable architecture.

3. Liskov Substitution Principle (LSP): The LSP states that objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program. In simpler terms, it means that derived classes should be able to substitute their base classes without breaking the code's behavior. This principle ensures that inheritance hierarchies are well-designed and adhere to the "is-a" relationship.
A Python example that illustrates the Liskov Substitution Principle (LSP):
```JSX
class Bird:
    def fly(self):
        pass

class Duck(Bird):
    def fly(self):
        print("Duck is flying...")

class Ostrich(Bird):
    def fly(self):
        raise NotImplementedError("Ostrich cannot fly.")

def perform_fly(bird):
    bird.fly()

duck = Duck()
ostrich = Ostrich()

perform_fly(duck)
perform_fly(ostrich)
```
In this example, we have a base Bird class with a fly method that is expected to be overridden by its subclasses. Two specific bird species, Duck and Ostrich, inherit from the Bird class.

The Liskov Substitution Principle states that objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program. In this case, both Duck and Ostrich can be used in place of Bird because they inherit the fly method from the base class.

By adhering to the Liskov Substitution Principle, we ensure that the behavior of derived classes does not violate or change the expected behavior defined by the base class. Subclasses can extend the functionality of the base class while preserving the overall behavior and allowing for seamless substitution.

4. Interface Segregation Principle (ISP): The ISP emphasizes that clients should not be forced to depend on interfaces they do not use. It encourages the design of fine-grained interfaces specific to the needs of the clients. By adhering to this principle, we avoid bloated interfaces and minimize dependencies between components.

```JSX
from abc import ABC, abstractmethod

class Printer(ABC):
    @abstractmethod
    def print_document(self, document):
        pass

class Scanner(ABC):
    @abstractmethod
    def scan_document(self):
        pass

class Photocopier(Printer, Scanner):
    def print_document(self, document):
        print("Printing document:", document)

    def scan_document(self):
        print("Scanning document...")

class Client:
    def __init__(self, printer):
        self.printer = printer

    def do_print(self, document):
        self.printer.print_document(document)

printer = Photocopier()
client = Client(printer)
client.do_print("Sample Document")

```
In this example, we have two interfaces, Printer and Scanner, each representing a distinct responsibility. The Photocopier class implements both interfaces, providing the necessary methods.

The Client class depends only on the Printer interface since it needs printing functionality. It doesn't need to know about the scanning capability. By relying on a specific interface, the client is shielded from unnecessary dependencies and is not forced to implement methods it doesn't use.

5. Dependency Inversion Principle (DIP): The DIP states that high-level modules should not depend on low-level modules. Both should depend on abstractions. This principle promotes loose coupling and decoupling of modules by relying on abstractions, such as interfaces or abstract classes, instead of concrete implementations. It allows for flexibility, modularity, and easier testing.

By following these SOLID principles, developers can achieve code that is modular, maintainable, and resilient to changes. These principles provide guidelines for creating software systems that are flexible, scalable, and easier to understand and modify over time.

```JSX
from abc import ABC, abstractmethod

class MessageSender(ABC):
    @abstractmethod
    def send_message(self, message):
        pass

class EmailSender(MessageSender):
    def send_message(self, message):
        print("Sending email:", message)

class SMSMessenger(MessageSender):
    def send_message(self, message):
        print("Sending SMS:", message)

class NotificationService:
    def __init__(self, sender: MessageSender):
        self.sender = sender

    def send_notification(self, message):
        self.sender.send_message(message)

email_sender = EmailSender()
notification_service = NotificationService(email_sender)
notification_service.send_notification("Hello, World!")

sms_messenger = SMSMessenger()
notification_service = NotificationService(sms_messenger)
notification_service.send_notification("Hello, OpenAI!")

```
In this example, we have a MessageSender abstract base class that defines the contract for sending messages. Two concrete classes, EmailSender and SMSMessenger, implement the send_message method.

The NotificationService class depends on the MessageSender abstraction rather than specific implementations. It receives an instance of a MessageSender through its constructor, allowing for easy substitution of different senders.

By following the Dependency Inversion Principle, we achieve decoupling between the NotificationService and the concrete message sender implementations. The high-level module (NotificationService) depends on the abstraction (MessageSender), and the low-level modules (EmailSender and SMSMessenger) depend on the same abstraction. This promotes flexibility, modularity, and easy replacement or addition of different message senders without impacting the NotificationService class.
