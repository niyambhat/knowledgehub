---
sidebar_position: 1
---

# Data flow in React

Unidirectional data flow is an architectural pattern used in software development where data only flows in one direction through a hierarchy of components. This means that the data is passed down from parent components to child components as props.

A react app consists of many components, organised as component tree. . The data flows from the root component to all the  components in the tree structure that require this data, using props.

## Parent Component
```JSX
function Coffee() {
    return (
        <Cup name="Cappuccino" foamStatus="full" glassShape="round" />
    );
};
```

## Child Component
```JSX
function Cup(props) {
    return (
        <div>
            {props.name} with <Foam status={props.foamStatus} /> served in a {props.glassShape}-shaped glass.
        </div>
    );
}
```

## Grand-Child Component
```JSX
function Foam(props) {
    return (
        <span>
            Foam is {props.status}
        </span>
    );
}
```

When data flows through props in a single direction, it becomes easier to comprehend the interactions between different components. If data were to move in all directions, it would be more difficult to understand its logical flow. Moreover, any attempts at optimization would likely be less efficient, particularly in modern React.

