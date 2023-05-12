---
sidebar_position: 2
---


## React Router Dom  

### Simple Implementation of React Router
A simple implementation of the React navigation. the anchor tag is redundant in react for navigation. 


Little Lemons Project Example
```JSX
import "./App.css";
import Homepage from "./Homepage";
import AboutLittleLemon from "./AboutLittleLemon";
import Contact from "./Contact";
import { Routes, Route, Link } from "react-router-dom";

function App() {
  return (
    <div>
	  <nav>
      <Link to="/" className="nav-item">Homepage</Link>
      <Link to="/about" className="nav-item">About Little Lemon</Link>
      <Link to="/contact" className="nav-item">Contact</Link>

	  </nav>
      <Routes> 
        <Route path="/" element={<Homepage />}></Route>
        <Route path="/about" element={<AboutLittleLemon />}></Route>
        <Route path="/contact" element={<Contact />}></Route>
      </Routes>
    </div>
  );
};

export default App;


```

Other examples 
```JSX
import React from 'react';
import { Routes, Route, NavLink, BrowserRouter } from 'react-router-dom';
import MealsApp from './Components/ContextApiOne/MealsApp';
import SearchApp from './Components/StateManagement/SearchApp';
import Testpage from './Components/Pages/Testpage';

function App() {
  return (
    <BrowserRouter>
    <div className="App">
      <nav>
        <NavLink to="/meals" activeClassName="active-link">
          Meals App
        </NavLink>
        <NavLink to="/search" activeClassName="active-link">
          Search App
        </NavLink>
        <NavLink to="/err" activeClassName="active-link">
          Error Page
        </NavLink>
      </nav>
      <Routes>
        <Route path="/meals" element={<MealsApp />} />
        <Route path="/search" element={<SearchApp />} />
      </Routes>
    </div>
    </BrowserRouter>  
  );
}

export default App;
```


## A more optimised version

```JSX
import React from 'react';
import { BrowserRouter as Router, Switch, Route,Routes, NavLink } from 'react-router-dom';
import MealsApp from './Components/ContextApiOne/MealsApp';
import SearchApp from './Components/StateManagement/SearchApp';
import Testpage from './Components/Pages/Testpage';

const routes = [
  {
    path: '/',
    Component: MealsApp,
    exact: true,
  },
  {
    path: '/search',
    Component: SearchApp,
  },
  {
    path: '/err',
    Component: Testpage,
  },
];

const Navigation = () => {
  return (
    <nav>
      <NavLink to="/" exact activeClassName="active-link">
        Meals App
      </NavLink>
      <NavLink to="/search" activeClassName="active-link">
        Search App
      </NavLink>
      <NavLink to="/err" activeClassName="active-link">
        Error Page
      </NavLink>
    </nav>
  );
};

const App = () => {
  return (
    <div className="App">
      <Router>
        <Navigation />
        <Routes>
        {routes.map((route, index) => (
            <Route key={index} path={route.path} exact={route.exact} element={<route.Component />} />
          ))}
        </Routes>     
      </Router>
    </div>
  );
};

export default App;


```
