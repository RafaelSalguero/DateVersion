#dateversion
A node program that generate a single .js that sets a global variable with the current date and time.

Usefull for generating cache busting parameters

Run the program:
```
node node_modules/dateversion/dateversion "version.js" "app.version"
```

And the "version.js" file will be generated with: 

```
var app = app || { };
app.version = '20160402T175655';
```

##Install me!
```
npm install dateversion 
```
**Run without arguments for help:**
```
node node_modules/dateversion/dateversion.js
```
**Or with arguments**
```
node node_modules/dateversion/dateversion.js [filename] [variableName]
```
