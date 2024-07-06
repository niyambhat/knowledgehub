---
sidebar_position: 2
---

# React project from scratch

Reference: Creating a React App from scratch 

## What does React offer?
- Provides a straightforward and powerful way to render data in the user's browser.
- Efficiently updates the user interface in response to changes in the underlying data.
- Provides little guidance on how to load, store, and manipulate this data, allowing developers flexibility to choose the best approach for their applications.

As a result, data loading and management logic often becomes tightly integrated into the components themselves. Consequently, vanilla React applications frequently feature large, complex components that handle all aspects of data management internally. 

If we can find a way to effectively identify and organize the many different types of concerns in an application, this goes a long way toward making our code base more maintainable. This brings us to **SoC (Separation of Concerns)**.

**SoC is the main concept behind React.**

## React Ecosystem

- **React Redux**: Manage state in our app using FLUX architecture.
- **Redux Thunkx**: Side-effect management (network requests).
- **Reselect**: Selector abstracts away the state's structure.
- **Styled components**

## Building a React App from Scratch 

Great experience of what goes on behind the scenes.

### Starting Ingredients:

Create a folder structure as such
my-react-app/
  |- public/
  |  |- index.html
  |- src/
  |  |- index.js


### Initializing project:

1. Inside an empty folder 
```bash
npm init -y
```
2. Create folder structure:
C
### Inside `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>React App</title>
</head>
<body>
  <div id="root"></div>
  <noscript>Please enable javascript</noscript>
  <script src="../dist/bundle.js"></script> <!-- Loading our js file, we will create later -->
</body>
</html>
```


### Adding support for ES6 and JSX:

```bash
npm install --save-dev @babel/core @babel/cli @babel/preset-env @babel/preset-react
```

### Babel Presets 
Adding .babelrc in root:

```Json
{
  "presets": ["@babel/preset-env", "@babel/preset-react"]
}
```

Transpiling is the process of converting source code from one high-level programming language to another.

- **@babel/preset-env**:
  - Enables Babel to transpile modern JavaScript code (ES6+ syntax) to a version of JavaScript compatible with the browsers or environments you want to support.
  - Includes necessary polyfills and transformations based on the specified targets (browsers or Node.js versions).

- **@babel/preset-react**:
  - Enables Babel to transform JSX syntax and React-specific features into plain JavaScript code that browsers can understand.
  - Includes transformations like converting JSX to `React.createElement` calls and handling other React-specific syntax.


### Introducing Webpack 🛠️

We need to set up Webpack to actually build our app. What we're going to have Webpack do for us is take the code in our source directory and perform some operations on it, like converting the ES6 syntax and JSX to common JS, and then host our public directory so that we can view our app in a browser.

Webpack is an awesome open-source module bundler for JavaScript.

#### Life without Module Bundler 📦

Without module loaders and bundlers, you could always combine your files manually or load your HTML with countless ``<script>`` tags, but that has several disadvantages:

- You need to keep track of the proper order in which the files should load, including which files depend on which other files and making sure not to include any files you don’t need.
- Multiple `<script>` tags mean multiple calls to the server to load all of your code, which is worse for performance.
- Obviously, this entails a lot of manual work, instead of letting the computer do it for you.


Steps:
```bash 
npm i save-dev webpack webpack-cli webpack-dev-server style-loader scc-loader babel-loader 
```


- `style-loader` injects CSS into the DOM by adding a `<style>` tag.
- `css-loader` interprets `@import` and `url()` in CSS files and resolves them, meaning it translates these directives into import statements that Webpack can understand and process.


Recommended reading:
https://www.smashingmagazine.com/2017/02/a-detailed-introduction-to-webpack/


### `webpack.config.js`
On the root create a new file called webpack.config.js.

This webpack configuration file sets up a development environment with features for transforming ES6 to JavaScript, loading CSS, resolving file extensions, outputting bundled JS, defining a development server, and enabling Hot Module Replacement (HMR).


```Javascript
const path = require("path");
const webpack = require("webpack");

module.exports = {
  entry: "./src/index.js",
  mode: "development",

  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
          options: { presets: ["@babel/env"] },
        },
      },
      {
        test: /\.css$/,
        use: ["style-loader", "css-loader"],
      },
    ],
  },
  output: {
    path: path.resolve(__dirname, "dist"),
    publicPath: "/dist/", // Ensure this matches devServer publicPath
    filename: "bundle.js",
  },
  resolve: {
    extensions: ["*", ".js", ".jsx"],
  },
  devServer: {
    static: {
      directory: path.join(__dirname, "public"),
    },
    hot: "only",
    port: 3000,
  },
  plugins: [new webpack.HotModuleReplacementPlugin()],
};
```

### Add React-refresh to hotreload UI changes on browser

```bash
npm install --save-dev @pmmmwh/react-refresh-webpack-plugin react-refresh
```
Then in webpack.config.js,

```Javascript
const path = require("path");
..
const ReactRefreshWebpackPlugin = require("@pmmmwh/react-refresh-webpack-plugin");

module.exports = {
  entry: "./src/index.js",
  mode: "development",

  module: {
    rules: [
      ....
  },
  plugins: [
    new webpack.HotModuleReplacementPlugin(),
    new ReactRefreshWebpackPlugin(), // Add the React Refresh Webpack Plugin
  ],
};

```
### Checkpoint, the file structiore should look as such. 
my-react-app/
  |- public/
  |  |- index.html
  |- src/
  |  |- index.js
  |  |- App.js

Index.js is where we initialze or react component such that it attaches to the root in Index.html
```Jsx
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(<App />, document.getElementById("root"));
```


Then we start coding our app in App.js, building and adding new components as we go along
```jsx
import React from 'react';

const App = () => {
  return (
    <div>
      <h1>Welcome to My App</h1>
      <p>This is a simple React application.</p>
    </div>
  );
};

export default App;
```

### Finish voila





