#autoreq.js
A node program that generate a single .js file requiring all files that matches a given file name

Checkout the [Typescript skeleton](https://github.com/RafaelSalguero/AngularTypescriptSkeleton) for a real world example of this library

This tool is intended for projects with *feature based* folders in which each feature is responsable for its own dependencies.


##Install me!
```
npm install autoreq 
```
**Run without arguments for help:**
```
node node_modules/autoreq/autoreq.js
```
**Or with arguments**
```
node node_modules/autoreq/autoreq.js [filename] [basePath] [outputFile] [inputFolders]
```

**Example:**

Suppose the following folder structure and that each feature contains a **view** (html) and a **controller** (.js / .ts)
```
app
  |--features
     |--login
        |--login.html
        |--main.ts
     |--home
        |--home.html
        |--main.ts
     |--products
        |--products.html
        |--main.ts
     |--clients
        ...
index.html
```

Running `node autoreq.js "." main.js deps.js "."` would generate the `deps.js` files requiring all files in `"."` (base path) that are named `main.js` with the following content:

```
require('features/login/main');
require('features/home/main');
require('features/products/main');
require('features/clients/main');

```

Allowing us requiring the `deps.js` file that contains all main dependencies to each feature, of course,
each one of these `main.js` file could have its own dependencies, controllers, services, or any other component that should be loaded when the application starts
