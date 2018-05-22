## Expressions and Operators
You express yourself, and this express is result of your thoughts! ok same in JS. ` expression is a phrase of JavaScript that a JavaScript interpreter
can evaluate to produce a value`.  For simplicity, we sometimes say that an operator returns a value rather than “evaluates to” a value
- Primary expression: `constant &literal values`, `Reserved words ` & ` bare variable reference`
- Initializers (for arrays, and objects are called literals)

### Property Access
1. Dot access `expression . identifier` 
2. Bracket access `expression [ expression ]`

#### Well which one to use? :confused:
- Dot is simpler and easier to use, bracket is harder! 
- If the property name is a reserved word or includes spaces or punctuation characters, or when it is a number (for arrays), you must use the square bracket notation. 
- Square brackets are also used when the property name is not static but is itself the result of a computation.

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

#### Invocation
- Output of a function invocation is expected from return. ***If there is no return the it is undefined***.

### Object Creation
```
new Object()
new Point(2,3)
new Object
new Date
```
Functions written for use as constructors do not return a value, and the value of the object creation expression is the newly created and initialized object. If a constructor does return an object value, that value becomes the value of the object creation expression and
the newly created object is discarded.
### Operators
- Operators with higher precedence are performed before those with lower precedence.(check the book table)
- Operator precedence can be overridden with the explicit use of parentheses.

#### Arithmetic Operators
- In JavaScript, however, all numbers are floating-point, so all division operations have floatingpoint results: 5/2 evaluates to 2.5, not 2. Division by zero yields positive or negative infinity, and 0/0 evaluates to NaN: neither of these cases raises an error :sweat_smile:.
- Modulo (%):  The sign of the result is the same as the sign of the first operand. For example, 5 % 2 evaluates to 1 and -5 % 2 evaluates to -1. :sweat_smile: This operator is typically used with integer operands, but it also works for floating-point values. For example, 6.5 % 2.1 evaluates to 0.2 :sweat_smile:.
- Addition (+) The binary + operator adds numeric operands or concatenates string operands :sweat_smile:  The conversion rules for + give priority to string concatenation.
- Unary plus (+): converts its operand to a number
(or to NaN) and returns that converted value. When used with an operand that is already a number, it doesn’t do anything.
- Increment (++): It s operand must be a `lvalue`
- bitwise operators: `Bitwise AND (&)`, `Bitwise OR (|)`, `Bitwise XOR (^)`, `Bitwise NOT (~)`, `Shift left (<<)`, `Shift right with sign (>>)`, `Shift right with zero fill (>>>)`

#### comparison expressions
- Relational expressions always evaluate to a boolean value, and that value is often used to control the flow of program execution in if, while, and for statements. `==`, `===`, `!==`, `<=`, `>=`, Property existence `(in)`
- `Loose equality ` vs `strict equality`:second one check for type and value, first one only check for the value(there is also casting involved.)
```
1 == "1"
true == 1
"1" == true
false == 0
[] == 0
```

#### logical expressions
- perform Boolean algebra and are often used in conjunction with the relational operators to combine two relational expressions into one more complex expression. These guys are alos tricky. Becareful!
```
// If max_width is defined, use that. Otherwise look
// for a value in the preferences object. If that is
// not defined use a hard-coded constant.
var max = max_width || preferences.max_width || 500;
```

#### assignment expressions
- JavaScript uses the = operator to assign a value to a variable, object property, or array element
- Besides the normal = assignment operator, JavaScript supports a number of other assignment operators that provide shortcuts by combining assignment with some other operation.`=+`,`+-`, `=*`, `=/`, `=%`



#### The delete Operator
- delete is a unary operator that attempts to delete the object property or array element specified as its operand. 
```
var o = {x:1, y:2}, a = [1,2,3];
delete o.x; // Delete a property of o
"x" in o // => false: the property does not exist
delete a[2]; // Delete the last element of the array
2 in a // => false: array element 2 doesn't exist
```
#### The Comma Operator (,)
- The comma operator is a binary operator whose operands may be of any type. It evaluates its left operand, evaluates its right
operand, and then returns the value of the right operand. The left-hand expression is always evaluated, but its value is discarded,
which means that it only makes sense to use the comma operator when the left-hand expression has side effects. The only situation in which the comma operator is commonly used is with a for loop that has multiple loop variables:
```
// The first comma below is part of the syntax of the
// var statement. The second comma is the comma operator:
// it lets us squeeze 2 expressions (i++ and j--) into a
// statement (the for loop) that expects 1.
for(var i=0,j=10; i < j; i++,j--)
 console.log(i+j);
```
