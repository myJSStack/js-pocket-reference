# Statements
**Expressions are evaluated to produce a value**, but **statements are executed to make something happen**.
- Conditionals are statements
- Loops
- Jumps 

### Functions
- Function declaration statements differ from function definition expressions in that they include a function name. Both
forms create a new function object, but the function declaration statement also declares the function name as a variable and assigns the function object to it. Like variables declared with var, functions defined with function definition statements are implicitly “hoisted” to the top of the containing script or function, so that all functions in a script or all nested functions in a function are declared before any other code is run. This means that you can invoke a JavaScript function before you declare it.

### Loops
- JavaScript has four looping statements: while, do/while, for, and for/in.
- The for/in statement uses the for keyword, but it is a completely different kind of loop than the regular for loop. A for/in loop looks like this:
```
for (variable in object)
 statement
```
The for/in loop does not actually enumerate all properties of an object, only the enumerable properties. The various built-in methods defined by core JavaScript are not enumerable. All objects have a toString() method, for example, but the for/in loop does not enumerate this toString property. In addition to built-in methods, many other properties of the built-in objects are nonenumerable. All properties and methods defined by your code are enumerable, however. (But in ECMAScript 5, you can make them nonenumerable.

### return
A return statement may appear only within the body of a function. It is a syntax error for it to appear anywhere else. 
- With no return statement, a function invocation simply executes each of the statements in the function body in turn until it reaches the end of the function, and then returns to its caller. In this case, the invocation expression evaluates to undefined.
- The return statement can also be used without an expression to make the function return undefined before it reaches the end of its body.
```
function display_object(o) {
 // Return immediately if o is null or undefined.
 if (!o) return;
 // Rest of function goes here...
}
```

### throw expression;
- An exception is a signal that indicates that some sort of exceptional condition or error has occurred. 
- In JavaScript, exceptions are thrown whenever a **runtime error occurs** and whenever ***the program explicitly*** throws one using the throw statement.
-  Exceptions are caught with the try/catch/finally statement, which is described next.
- The Error class and its subclasses are used when the JavaScript interpreter itself throws an error, and **you can use them as well.**
-  An **Error object** has a **name property** that specifies the type of error and a **message property** that holds the string passed to the constructor function
- Exception handlers are written using the catch clause of the try/catch/finally statement.


### try/catch/finally
- The try/catch/finally statement is JavaScript’s exception handling mechanism. 
```
try {
 // Normally, this code runs from the top of the block
 // to the bottom without problems. But it can
 // sometimes throw an exception, either directly, with
 // a throw statement, or indirectly, by calling a
 // method that throws an exception.
}
catch (e) {
 // The statements in this block are executed if, and
 // only if, the try block throws an exception. These
 // statements can use the local variable e to refer
 // to the Error object or other value that was thrown.
 // This block may handle the exception somehow, may
 // ignore the exception by doing nothing, or may
 // rethrow the exception with throw.
}
finally {
 // This block contains statements that are always
 // executed, regardless of what happens in the try
 // block. They are executed when the try block
 // terminates:
 // 1) normally, after reaching the bottom
 // 2) because of a break, continue, or return
 // 3) with an exception handled by a catch above
 // 4) with an uncaught exception that is propagating
}
```

### Miscellaneous Statements
### with
- The with statement temporarily alters the way variables are looked up by specifying an object whose properties should be treated as if they were variables. It has the following syntax:
```
with (object)
 statement
```
***Never use it, it will be depricated.***

### debugger
- The debugger statement normally does nothing. If, however, a debugger program is available and is running, then an implementation
may (but is not required to) perform some kind of debugging action. In practice, this statement acts like a breakpoint: execution of JavaScript code stops and you can use the debugger to print variables’ values, examine the call stack, and so on. 

### “use strict”
- Introduced in JS5, and is ingonred by ECMAScrip3. (it is a directive not an expression)
- Used to tell that the codes are in `strict mode`
1. The with statement is not allowed in strict mode.
2. In strict mode, all variables must be declared: a ReferenceError is thrown if you assign a value to an identifier that
is not a declared variable, parameter, or property of the global object. (In nonstrict mode, this implicitly declares
a global variable by adding a new property to the global object.)
3. In strict mode, functions invoked as functions (rather than as methods) have a this value of undefined. (In nonstrict
mode, functions invoked as functions are always passed the global object as their this value.) This difference can be used to determine whether an implementation supports strict mode:
```
var hasStrictMode = (function() {
 "use strict";
 return this === undefined;
}());
```
4. In strict mode, assignments to nonwritable properties and attempts to create new properties on nonextensible objects throw a TypeError.
5. In strict mode, code passed to eval() cannot declare variables or define functions in the caller’s scope as it can in
nonstrict mode. Instead, variable and function definitions live in a new scope created for the eval(). This scope is discarded when the eval() returns.
6. In strict mode, octal integer literals (beginning with a 0 that is not followed by an x) are not allowed. (In nonstrict mode, some implementations allow octal literals.)
7. In strict mode, the identifiers eval and arguments are treated like keywords, and you are not allowed to change their value. 
