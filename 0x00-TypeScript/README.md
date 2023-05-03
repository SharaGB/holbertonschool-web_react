# 0x00. Typescript

<div class="panel panel-default" id="project-description">
  <div class="panel-body">
    <p><img src="https://s3.eu-west-3.amazonaws.com/hbtn.intranet/uploads/medias/2019/12/baea85b5e9a9fb5c36ec.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&amp;X-Amz-Credential=AKIA4MYA5JM5DUTZGMZG%2F20230503%2Feu-west-3%2Fs3%2Faws4_request&amp;X-Amz-Date=20230503T133353Z&amp;X-Amz-Expires=86400&amp;X-Amz-SignedHeaders=host&amp;X-Amz-Signature=6680caa3170ee85b964d0e58dce0cb6790c547d70b50d2387f7bc9f754a551b0" alt="" loading="lazy" style=""></p>

<h2>Configuration Files</h2>

<p>Please use these files for the following tasks</p>

<h3><code>package.json</code></h3>

<details open="">
<summary>Click to show/hide file contents</summary>
<pre><code>
{
  "name": "typescript_dependencies",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start-dev": "webpack-dev-server --open",
    "build": "webpack",
    "test": "jest"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@babel/plugin-proposal-export-default-from": "^7.5.2",
    "@babel/preset-typescript": "^7.7.2",
    "@types/jest": "^24.0.23",
    "@typescript-eslint/eslint-plugin": "^2.4.0",
    "@typescript-eslint/parser": "^2.4.0",
    "clean-webpack-plugin": "^3.0.0",
    "fork-ts-checker-webpack-plugin": "^1.5.1",
    "html-webpack-plugin": "^3.2.0",
    "jest": "^24.9.0",
    "source-map": "^0.7.3",
    "ts-jest": "^24.1.0",
    "ts-loader": "^6.2.0",
    "typescript": "^3.6.4",
    "webpack": "^4.41.2",
    "webpack-cli": "^3.3.9",
    "webpack-dev-server": "^3.8.2"
  }
}
</code>
</pre>
</details>

<h3><code>.eslintrc.js</code></h3>

<details>
<summary>Click to show/hide file contents</summary>
<pre><code>
module.exports =  {
  parser:  '@typescript-eslint/parser',
  extends:  [
    'plugin:@typescript-eslint/recommended',  // Uses the recommended rules from @typescript-eslint/eslint-plugin
  ],
  parserOptions:  {
    ecmaVersion:  2018,
    sourceType:  'module',
  },
  rules:  {
  },
};
</code>
</pre>
</details>

<h3><code>tsconfig.json</code></h3>

<details>
<summary>Click to show/hide file contents</summary>
<pre><code>
{
  "compilerOptions": {
    "outDir": "./dist/",
    "sourceMap": true,
    "noImplicitAny": true,
    "module": "es6",
    "target": "es5",
    "allowJs": true,
    "moduleResolution": "node"
  }
}
</code>
</pre>
</details>

<h3><code>webpack.config.js</code></h3>

<details>
<summary>Click to show/hide file contents</summary>
<pre><code>
const path = require("path");
const HtmlWebpackPlugin = require('html-webpack-plugin');
const { CleanWebpackPlugin } = require('clean-webpack-plugin');
const ForkTsCheckerWebpackPlugin = require('fork-ts-checker-webpack-plugin');

module.exports = {
  entry: "./js/main.ts",
  devtool: "inline-source-map",
  module: {
    rules: [
      {
        test: /\.tsx?$/,
        loader: 'ts-loader',
        options: {
          transpileOnly: true
        }
      }
    ]
  },
  resolve: {
    extensions: [".tsx", ".ts", ".js"]
  },
  devServer: {
    contentBase: "./dist"
  },
  plugins: [
    new ForkTsCheckerWebpackPlugin(),
    new CleanWebpackPlugin(),
    new HtmlWebpackPlugin({
      title: "Development"
    })
  ],
  output: {
    filename: "bundle.js",
    path: path.resolve(__dirname, "dist")
  }
};
</code>
</pre>
</details>

  </div>
</div>

## Description

What you should learn from this project:

---

### [0. Creating an interface for a student](./task_0/js/main.ts)

* Copy the following configuration files (provided above) into the task_0 directory: package.json, .eslintrc.js, tsconfig.json, webpack.config.js

### [1. Let's build a Teacher interface](./task_1/js/main.ts)

* Create a directory task_1 and copy these configuration files into this folder: package.json, tsconfig.json, webpack.config.js

### [2. Extending the Teacher class](./task_1/js/main.ts)

* Write an interface named Directors that extends Teacher. It requires an attribute named numberOfReports(number)

### [3. Printing teachers](./task_1/js/main.ts)

* Write a function printTeacher:

### [4. Writing a class](./task_1/js/main.ts)

* Write a Class named StudentClass:

### [5. Advanced types Part 1](./task_2/js/main.ts)

* Create the DirectorInterface interface with the 3 expected methods:

### [6. Creating functions specific to employees](./task_2/js/main.ts)

* Write a function isDirector:

### [7. String literal types](./task_2/js/main.ts)

* Write a String literal type named Subjects allowing a variable to have the value Math or History only.
Write a function named teachClass:

### [8. Ambient Namespaces](./task_3/js/main.ts)

* Create a directory called task_3 and copy these configuration files into it: package.json, webpack.config.js, tsconfig.json.

### [9. Namespace & Declaration merging](./task_4/package.json)

* Create a new directory task_4 and copy the above tsconfig.json and put this package.json in there

### [10. Update task_4/js/main.ts](./task_4/js/main.ts)

* create and export a constant cpp for Cpp Subjects
* create and export a constant java for Java Subjects
* create and export a constant react for React Subjects
* create and export one Teacher object cTeacher with experienceTeachingC = 10
* for Cpp subject, log to the console C++, set cTeacher as the teacher, call the two methods getRequirements and getAvailableTeacher and print the strings they return
* for Java subject, log to the console Java, set cTeacher as the teacher, call the two methods getRequirements and getAvailableTeacher, and print the strings they return
* for React subject, log to the console React, set cTeacher as the teacher, call the two methods getRequirements and getAvailableTeacher, and print the strings they return

### [11. Brand convention & Nominal typing](./task_5/js/main.ts)

* Create a directory task_5 and copy these configuration files into the root of task_5: package.json, tsconfig.json, webpack.config.js
