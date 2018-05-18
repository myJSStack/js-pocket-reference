## Expressions and Operators
You express yourself, and this express is result of your thoughts! ok same in JS. ` expression is a phrase of JavaScript that a JavaScript interpreter
can evaluate to produce a value`
- Primary expression
- Initializers (for arrays, and objects are called literals)

### Property Access
`expression . identifier` `expression [ expression ]`
- Well which one? :confused:
dot is simplere and easier, [] is harder! BUT If the property name is a reserved word or includes spaces or punctuation characters, or when it is a number (for arrays), you
must use the square bracket notation. Square brackets are also used when the property name is not static but is itself the result of a computation.

### Function expresion vs. function declaration
What is a Function Declaration?

A Function Declaration defines a named function variable without requiring variable assignment. Function Declarations occur as standalone constructs and cannot be nested within non-function blocks. It’s helpful to think of them as siblings of Variable Declarations. Just as Variable Declarations must start with “var”, Function Declarations must begin with “function”.
```
function bar() {
    return 3;
}
```

What is a Function Expression?

A Function Expression defines a function as a part of a larger expression syntax (typically a variable assignment ). Functions defined via Functions Expressions can be named or anonymous. Function Expressions must not start with “function” (hence the parentheses around the self invoking example below)
```
//anonymous function expression
var a = function() {
    return 3;
}
 
//named function expression
var a = function bar() {
    return 3;
}
 
//self invoking function expression
(function sayHello() {
    alert("hello!");
})();
```
