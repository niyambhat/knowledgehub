---
sidebar_position: 3
---

# Todo List APP, Keys Demystified

In React, keys are special attributes that are used to uniquely identify elements in an array. Keys help React keep track of which elements have changed, been added, or been removed. When you don't specify a key, React will use the default key which is the index of the element in the array.

It's better not to use the index as the key for several reasons:

If the order of the list changes, the keys will also change, which can lead to unexpected behavior or errors.

If you add or remove items in the middle of the list, React has to re-render all the items after the change, which can be slow and inefficient.

If you have duplicate keys, React will warn you with a console error.

Instead of using the index, it's better to use a unique identifier for each item in the list, such as a database ID or a UUID. This ensures that the keys will remain stable even if the order of the list changes or items are added or removed.


Additional resources:
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map  
https://react.dev/learn/rendering-lists#rendering-data-from-arrays
https://react.dev/learn/rendering-lists#where-to-get-your-key


# In this UI Component.
React can identify the component, track it , even when the order is reversed using the reverse button.


```JSX
import React, {useState} from 'react'
import ToDoList from './ToDoList';

const data = [
    {
      id: "todo1",
      createdAt: new Date(),
      text: "Buy milk",
      completed: false
    },
    {
      id: "todo2",
      createdAt: new Date(),
      text: "Call John",
      completed: true
    },
    {
      id: "todo3",
      createdAt: new Date(),
      text: "Pay rent",
      completed: false
    }
  ];
  
  

function ToDoApp() {
    const [todos, setTodos] = useState(data)
    const reverseOrder=()=>{
        setTodos([...todos].reverse())
    }
  return (
    <ToDoList data ={todos} reverseOrder={reverseOrder}/>
  )
}

export default ToDoApp

```

Then the child component

```JSX
import React from 'react'
import ToDoItem from './ToDoItem'

function ToDoList(props) {
    const {data} = props
  return (
    <div>
        <button onClick={props.reverseOrder}>Reverse</button>
        <table>
            <tbody>
                {
                    data.map((todo,index)=>(
                        <ToDoItem key={todo.id} title={todo.id}/>
                    ))
                }
            </tbody>
        </table>
    </div>
  )
}

export default ToDoList
```

To Do Item
```JSX

```