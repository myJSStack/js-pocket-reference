# Statements
Expressions are evaluated to produce a value, but statements are executed to make something happen.
- Conditionals are statements
- Loops
- Jumps 

#### Functions
- Function declaration statements differ from function definition expressions in that they include a function name. Both
forms create a new function object, but the function declaration statement also declares the function name as a variable and assigns the function object to it. Like variables declared with var, functions defined with function definition statements are implicitly “hoisted” to the top of the containing script or function, so that all functions in a script or all nested functions in a function are declared before any other code is run. This means that you can invoke a JavaScript function before you declare it.

#### Loops
- JavaScript has four looping statements: while, do/while, for, and for/in.
- The for/in statement uses the for keyword, but it is a completely different kind of loop than the regular for loop. A for/in loop looks like this:
```
for (variable in object)
 statement
```
The for/in loop does not actually enumerate all properties of an object, only the enumerable properties. The various built-in methods defined by core JavaScript are not enumerable. All objects have a toString() method, for example, but the for/in loop does not enumerate this toString property. In addition to built-in methods, many other properties of the built-in objects are nonenumerable. All properties and methods defined by your code are enumerable, however. (But in ECMAScript 5, you can make them nonenumerable.
