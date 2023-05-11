---
sidebar_position: 3
---

# Context API - Meals List App

The Context API is a feature in React that allows you to manage state at a global level, making it accessible to any component in your application. In this case, you will be using the Context API to create a data flow for your app.

To start, you will create a context using the **createContext()** method. This context will act as a global store for your data, and will be wrapped around the components that need access to it using the MealsProvider.

Next, you will implement a custom hook called **useMealsList**. This hook will allow you to access the value from anywhere in your app that is wrapped by the MealsContext provider. The useMealsList hook will use the useContext() method to get the current value of the MealsContext and return it to the component that called the hook.

Overall, by using the **MealsProvider** and useMealsList hook, you will be able to easily manage the state of your app's data and make it available to any component that needs it.

## Meals App
Let me tell you about the awesome Meals App! It's a React app that uses the MealsProvider to manage meal data state across the entire application.

The cool thing is that by using the MealsProvider, we can avoid the need to drill props down to child components or lift state, making our code simpler and more fun to work with.

In this app, we have a Meals component that renders a list of meals by accessing the meal data state from the MealsProvider using the useMealsList hook.

And we also have a Counter component that keeps track of the total number of meals by accessing the meal data state from the MealsProvider using the same useMealsList hook.

Overall, the Meals App is a great example of how the Context API in React can make our code simpler, more readable, and more fun to work with.

```JSX
import React from 'react'
import MealsProvider from './MealsProvider';
import Meals from './Meals';
import Counter from './Counter';

function MealsApp() {
  return (
    <MealsProvider>
        <Meals/>
        <Counter/>
    </MealsProvider>
  )
}

export default MealsApp
```


## API Context
```JSX
import { createContext, useContext } from "react";

const MealsContext = createContext();
const todaysMeals = ["Baked beans", "Lamb Chops", "Pizza"]

const MealsProvider =({children})=>{
    return(
        <MealsContext.Provider value={{todaysMeals}}>
            {children}
        </MealsContext.Provider>
    )
}

export const useMealsList = ()=>useContext(MealsContext)
export default MealsProvider
```

## Meals
```JSX
import React from 'react'
import { useMealsList } from './MealsProvider'

function Meals() {
    const { meals } = useMealsList();
    return (
        <>
            <h1>Meals using the Context API</h1>
            {meals.map((item, index) => (
                <h2 key={index}>{item}</h2>
            ))}
        </>
    )
}

export default Meals
```

## Counter
```JSX
import React from 'react'
import { useMealsList } from './MealsProvider'

function Counter() {
  const {meals} = useMealsList()
  return (
    <div>
      <h1>
      Number of meals today: {meals.length}
      </h1>
    </div>
  )
}

export default Counter
```


