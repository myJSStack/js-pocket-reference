## Types, Values, and Variables
- Data types in JS: Primitives, Objects (`Boolean`, `Null`, `Undefined`, `Number`, `String`, `Symbol`, `Object`)
- Primitive data type (3+2): `Number`, `Boolean`, `String`. + `Symbol` (added in ES6).Boolean.
- Object data type(3): `Object`, `Array`, `function`.
- Also, we have `undefined` (type=undefined), and `null` (type=object) as _primitives_.
- JS Variables are `untyped`, meaning you can assign it to a number now, 10 mins later you can assign it to a String

### Numbers
- No difference between integers, and floating point numbers  :laughing:
- Numbers are _64 bits floating point precision_. However to _interger values it is performed on 32-bit digits_
- base-10 numbers are common.
- base-16 values are written in strings of `"0x"` or `"0X"`
- Exponential notation in JS is like `[digits][.digits][(E|e)[(+|-) digits]]`
- There is a huge `Math` methods
```
Math.pow(2,53) // => 9007199254740992: 2 to the power 53
Math.round(.6) // => 1.0: round to the nearest integer
Math.ceil(.6) // => 1.0: round up to an integer
Math.floor(.6) // => 0.0: round down to an integer
Math.abs(-5) // => 5: absolute value
Math.max(x,y,z) // Return the largest argument
Math.min(x,y,z) // Return the smallest argument
Math.random() // Pseudo-random number 0 <= x < 1.0
Math.PI // π
Math.E // e: The base of the natural logarithm
Math.sqrt(3) // The square root of 3
Math.pow(3,1/3) // The cube root of 3
Math.sin(0) // Trig: also Math.cos, Math.atan, etc.
Math.log(10) // Natural logarithm of 10
Math.log(100)/Math.LN10 // Base 10 logarithm of 100
Math.log(512)/Math.LN2 // Base 2 logarithm of 512
Math.exp(3) // Math.E cubed
```
- Arithmetic in JavaScript **does not raise errors in cases of overflow, underflow, or division by zero**.:sweat_smile:
- When the result of a numeric operation is larger than the largest representable number (overflow), the result is a special infinity value, which Java-Script prints as _Infinity_. Similarly, when a negative value becomes larger than the largest representable negative number, the result is negative infinity, printed as _-Infinity_.:fearful:
- Division by zero is not an error in JavaScript: it simply returns infinity or negative infinity.:fearful:
- NaN: zero divided by zero, Infinity divided by Infinity, sqrt(a negative number)
- `== Nan` doesn't work  => `isNaN()` is the ONE :) however, `NaN has the typeof number`
- Note1: global isNaN() function, converts the tested value to a Number, then tests it.
- Note2: Number.isNaN() does not convert the values to a Number, and will not return true for any value that is not of the type Number.

### String
- Single and double quote, and you know how to use them combined!
- `\` escape character 
- length is a property
- Perfect set of methods
- It is important that to remember, **strings are immutable** in JS
-  + is used to **concatenate**. and numbers are casted to the strings when combining with Strings 
```
var s = "hello, world" // Start with some text.
s.charAt(0) // => "h": the first character.
s.charAt(s.length-1) // => "d": the last character.
s.substring(1,4) // => "ell": chars 2, 3, and 4
s.slice(1,4) // => "ell": same thing
s.slice(-3) // => "rld": last 3 characters
s.indexOf("l") // => 2: position of first l.
s.lastIndexOf("l") // => 10: position of last l.
s.indexOf("l", 3) // => 3: position at or after 3
s.split(", ") // => ["hello", "world"]
s.replace("h", "H") // => "Hello, world": // replaces all instances
s.toUpperCase() // => "HELLO, WORLD"
```
- slice is shared with arrays, more powerful,accepts negative numbers.
- substring can swap two inputs when needed!

### Booleans
- ok: true/false
- All true (objects, and arrays are included) unless 6 falsy values :imp:
```
undefined
null
0
-0
NaN
"" // the empty string
```
- Null, and undefined both have no value in them, no property, no method.

### Global Object
- All global variable are property of the global object
- In client-side JavaScript, the Window object serves as the global object. 
```
var global = this; // /refer to the global object
```

### Type Conversion
- JS converts everything to something it is expected to see! (:sweat_smile: OMG!)
```
Some examples:
10 + " objects" // => "10 objects". 10 -> string
"7" * "4" // => 28: both strings -> numbers
var n = 1 - "x"; // => NaN: "x" can't convert to a number
n + " objects" // => "NaN objects": NaN -> "NaN"
```
- Conversion are automatic, but may want to push to make you code cleaner using `Boolean()`, `Number()`, `String()` or `Object()`
- Note that any value other than null or undefined has a `toString()` method and the result of this method is usually the same as that returned by the String() function.
- Check out following articles for casting.Most of the time the outputs are tricky.[1](https://medium.freecodecamp.org/js-type-coercion-explained-27ba3d9a2839), [2](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Logical_operators)
- Working with financial or scientific data  :heart_eyes:
```
var n = 123456.789;
n.toFixed(2); // "123456.79"
n.toExponential(3); // "1.235e+5"
n.toPrecision(7); // "123456.7"
```

### Variable Declaration
- Before you use a variable in a JavaScript program, you should declare it. Variables are declared with the var keyword.
- You can also declare multiple variables with the same var keyword
- You can combine variable declaration with variable initialization
- If you don’t specify an initial value for a variable with the var statement, the variable is declared, but its value is undefined until your code stores a value into it.
- It is legal and harmless to declare a variable more than once with the var statement. If the repeated declaration has an initializer,
it acts as if it were simply an assignment statement.:stuck_out_tongue: !
- _BUT ERRORS PART_ > If you attempt to read the value of an undeclared variable :fist:, 
***Historically, however, and in nonstrict mode, if you assign a value to an undeclared variable, JavaScript actually creates that variable as a property of the global object, and it works much like a properly declared global variable. This means that you can get away with leaving your global variables undeclared. This is a bad habit and a source of bugs, however, and you should always declare your variables with var.***

- **Scopes**:  globals, and function body-> {} <- inputs to the function
JavaScript **does not have block scope**, Instead, JavaScript **uses function scope: variables are visible within the
function in which they are defined and within any functions that are nested within that function.**
- Variables are even visible before they are declared. This feature of JavaScript is informally known as **hoisting**: JavaScript code behaves as if all variable declarations in a function (but not any associated assignments) are “hoisted” to the top of the function.
