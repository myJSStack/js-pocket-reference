# Functions
- In JavaScript, functions are objects.
- JavaScript can assign functions to variables and pass them to other functions.
- (closures)JavaScript function definitions can be nested within other functions, and they have access to any variables that are in scope where they are defined.
- Developer can add properties, and new method to function object

### Defining Functions
- Note that parameters behave like local variables to a function
- function declaration statements are “hoisted” to the top of the enclosing script or the enclosing function, so that functions declared in this way may be invoked from code that appears before they are defined.
- The return statement causes the function to stop executing and to return the value of its expression (if any) to the caller.
- If a function does not contain a return statement, it simply executes each statement in the function body and returns the undefined value to the caller.

### Nested functions
- They can access the parameters and variables of the function (or functions) they are nested within

### Invoking Functions
- as functions,  as methods, as constructors, indirectly through their call() and apply() methods
#### three notes on ***this*** variable
1. Note that ***this*** is a keyword, not a variable or property name. JavaScript syntax does not allow you to assign a value to this.
2. Unlike variables, the this keyword does not have a scope. It is a common mistake to assume that a nested function invoked as a function can use this to obtain the invocation context of the
outer function. If you want to access the this value of the outer function, you need to store that value into a variable that is in scope for the inner function. It is common to use the variable self for this purpose
3. ***If a nested function is invoked as a method, its this value is the object it was invoked on. If a nested function is invoked as a function, its this value will be either the global object (nonstrict mode) or undefined (strict mode).***

- Constructor functions do not normally use the return keyword  If the constructor uses return with no value, or if it returns a primitive value, that return value is ignored and the new object is used as the value of the invocation.
- call() and apply(), invoke the function indirectly: 1st arg the lended object, 2nd arg is inputs for that function.
- The apply() method is like the call() method, except that the arguments to be passed to the function are specified as an array
- Perfect for ***monkey-patching*** !!

### Function Arguments and Parameters
- JS  does not any type checking on the argument values you pass, and number of arguments

#### The Arguments Object
- This is array but object like array; `(arguments[i])`
- function that use argument objects are so-called `varargs functions`

#### Funtions as Namespaces
- When you write a code, it is the best to isolate your code from outside world for many reasons simplest one is the conflict in the naming. With functions it is the possible make this isolation.
```
(function() { // mymodule as an unnamed expression
 // Module code goes here.
}()); 
```
#### Closures
- Nested funtons make closure, the our function returns innder one.  
- The innder one has access to the variables of outer ones one

