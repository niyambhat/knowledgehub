---
sidebar_position: 2
---

# State Management in React using Context API

Context API allows to manage state between parent and child components. It is a built in feature. 
This allows us to skip having to pass the props down the entire component tree. This proeblem is also known as prop drilling. Which could lead to unnecssary rerenders as well as complex coding as the app scales up. 

In summary, the Context API in React is a useful tool for managing shared data and functionality in your application, and can help to simplify your code and improve performance.

## Overview of the Context API in React and its Key Components

**createContext**: This is a method provided by the Context API in React that creates a new context object. It takes an optional initial value as a parameter, which is the value that the context will hold until it is overridden by a Provider component.

**useContext**: This is a hook provided by the Context API that allows you to consume the value of a context object. It takes a context object as a parameter and returns the current value of that context.

**ContextProvider**: This is a custom component that you can create to provide the value of a context to its child components. It takes the context object as a prop and wraps its children with the context value.

**children**: This is a special prop that is used in React to pass child components to a parent component. It is often used with the Context API to provide a way for the child components to access the value of a context object.

**ContextConsumer**: This is a component that you can use to consume the value of a context object in a class component. It takes a context object as a prop and a function as a child, which receives the current value of the context as an argument.