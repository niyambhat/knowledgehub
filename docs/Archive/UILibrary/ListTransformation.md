---
sidebar_position: 4
---

# List Transformation 

To transform the list of desserts, three operations are applied in sequence: filtering to remove any desserts with more than 500 calories, sorting the resulting low-calorie desserts array in ascending order by calorie count, and mapping each dessert object to an HTML li element that displays its name and calorie count. The resulting array of li elements is assigned to the lowCaloriesDesserts variable.

```JSX
import React from 'react'
import DessertsList from './DessertsList'
const desserts = [
    {
        name: "Chocolate Cake",
        calories: 400,
        createdAt: "2022-09-01",
    },
    {
        name: "Ice Cream",
        calories: 200,
        createdAt: "2022-01-02",
    },
    {
        name: "Tiramisu",
        calories: 300,
        createdAt: "2021-10-03",
    },
    {
        name: "Cheesecake",
        calories: 600,
        createdAt: "2022-01-04",
    },
];


function TransFormingList() {
    return (
        <div>
            <h2>List of low calorie desserts:</h2>
            <DessertsList data={desserts} />
        </div>
    )
}

export default TransFormingList
```

Then the child element as belows. On thing to keep ion mind is always using a key , such that react remembers the values that are in hte list. 
If the data is voming from he server, the best way is to use the db key as a value. 


```JSX
import React from "react";

function DessertsList({ data }) {
  const lowCaloriesDesserts = data
    .filter((dessert) => {
      return dessert.calories < 500;
    })
    .sort((a, b) => {
      return a.calories - b.calories;
    })
    .map((dessert) => {
      return (
        <li key={dessert.id}>
          {dessert.name} - {dessert.calories} cal
        </li>
      );
    });

  return (
    <ul>
      {lowCaloriesDesserts}
    </ul>
  )
}

export default DessertsList;

```