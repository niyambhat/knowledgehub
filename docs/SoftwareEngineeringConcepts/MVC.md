---
sidebar_position: 4
---

# Model View Controller 

MVC Pattern stands for Model-View-Controller Pattern. This pattern is used to separate application's concerns.
Model–view–controller (MVC) is a software design pattern commonly used for developing user interfaces that divides the related program logic into three interconnected elements

Model - Model represents an object carrying data. It can also have logic to update controller if its data changes.

View - View represents the visualization of the data that model contains.

Controller - Controller acts on both model and view. It controls the data flow into model object and updates the view whenever data changes. It keeps view and model separate.

### How does MVC help?
The MVC (Model-View-Controller) pattern promotes the separation of concerns in software development. It emphasizes the division of an application into three components: the model, the view, and the controller.

1. Separation of Concerns: The MVC pattern helps in organizing code by separating different responsibilities. The model represents the data and business logic, the view handles the presentation of the data to the user, and the controller manages user input and coordinates the interaction between the model and the view.

2. Dependency Direction: It is recommended that dependencies in an MVC architecture flow in the direction of stability. The model, being the core of the application, should be stable, with the view and controller depending on it. This allows for easier maintenance and updates to the user interface without affecting the underlying business logic.

3. Thin Controllers, Fat Models: In MVC, it is considered good practice to keep the controllers lightweight, focusing on handling user input, delegating tasks to the model, and updating the view accordingly. The models, on the other hand, should encapsulate the business rules and contain the majority of the application's logic.

4. User Interface Frameworks: It is important to choose user interface frameworks that align with the principles of MVC. Decoupling the business logic from the user interface framework ensures flexibility and portability.

By adhering to the MVC pattern, developers can achieve better separation of concerns, code organization, and maintainability in their applications.


Case Study one:

### Implementing MVC in a Todolist App in C#
Model:
```csharp
public class TodoItem
{
    public int Id { get; set; }
    public string Title { get; set; }
    public bool IsCompleted { get; set; }
}

Controller:
```csharp
public class TodoController : Controller
{
    public IActionResult Index()
    {
        List<TodoItem> todoList = GetTodoItemsFromDatabase(); // Assume this retrieves the list of todo items from the database
        return View(todoList);
    }
}

```

View(React Component):
```jsx
import React from 'react';

const TodoList = ({ todoList }) => {
  return (
    <div>
      <h1>Todo List</h1>
      <ul>
        {todoList.map((item) => (
          <li key={item.Id}>
            {item.Title}
            {item.IsCompleted ? <span>(Completed)</span> : <span>(Pending)</span>}
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoList;

```


### Implementing MVC in a Todolist App in Scala Lang
Here's an example of how the MVC pattern can be implemented in a Scala application with React as the view component for a simple Todo List:

Model:
```scala
case class TodoItem(id: Int, title: String, isCompleted: Boolean)

```

Controller:
```scala
import play.api.mvc._
import play.api.libs.json.Json

class TodoController extends Controller {
  def index = Action {
    val todoList = getTodoItemsFromDatabase() // Assume this retrieves the list of todo items from the database
    Ok(Json.toJson(todoList))
  }
  
  private def getTodoItemsFromDatabase(): List[TodoItem] = {
    // Retrieve the list of todo items from the database
    // Return a sample list for demonstration
    List(
      TodoItem(1, "Task 1", false),
      TodoItem(2, "Task 2", true),
      TodoItem(3, "Task 3", false)
    )
  }
}

```


View:
```scala
import React from 'react';

const TodoList = ({ todoList }) => {
  return (
    <div>
      <h1>Todo List</h1>
      <ul>
        {todoList.map((item) => (
          <li key={item.id}>
            {item.title}
            {item.isCompleted ? <span>(Completed)</span> : <span>(Pending)</span>}
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoList;

```