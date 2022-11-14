# Project Start Guide

1. Make your repo on github and clone it
2. Run `npm init -y` on your project directory
3. Run following command to setup webpack

   ```
   npm install --save-dev webpack
   npm install --save-dev webpack-cli
   npm install --save-dev webpack-dev-server
   npm install --save-dev html-webpack-plugin
   ```

4. Add **_webpack.config.js_** to your project directory
5. Add following code to your **_webpack.config.js_**

   ```js
   const path = require("path");
   const HtmlWebpackPlugin = require("html-webpack-plugin");

   module.exports = {
     entry: "./src/index.js",
     output: {
       filename: "bundle.js",
       path: path.resolve(__dirname, "dist"),
     },
     plugins: [
       new HtmlWebpackPlugin({
         template: "./src/index.html",
       }),
     ],
     mode: process.env.NODE_ENV === "production" ? "production" : "development",
   };
   ```

6. Add following code to your **_"scripts"_** in **_package.json_**

   ```json
    "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "webpack serve",
    "build": "NODE_ENV='production' webpack"
    },
   ```

To deploy your webpack dev server, run following command :

```
npm start
```
