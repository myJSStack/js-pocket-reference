## Types, Values, and Variables
- Date types in JS: Primitives, Objects
- Primitive data type: `Number`, `Boolean`, `String`.
- Object data type: `Object`, `Array`, `function`.
- Also, we have undefined (type=undefined), and null (type=object)
- JS Variables are `untyped`, meaning you can assign it to a number now, 10 mins later you can assign it to a String

### Numbers
- No diffrence between intergers, and floating point numbers
- Numbers are 64 bits floating point precison. However to interger values it is performed on 32-bit digits
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
- Arithmetic in JavaScript does not raise errors in cases of overflow, underflow, or division by zero.
- When the result of a numeric operation is larger than the largest representable number (overflow), the result is a special infinity value, which Java-Script prints as Infinity. Similarly, when a negative value becomes larger than the largest representable negative number, the result is negative infinity, printed as -Infinity.
- Division by zero is not an error in JavaScript: it simply returns infinity or negative infinity.
- NaN: zero divided by zero, Infinity divided by Infinity, sqrt(a negative number)
- `== Nan` doesn't work  => `isNaN()` is the ONE :) 
- Note1: global isNaN() function, converts the tested value to a Number, then tests it.
- Note2: Number.isNaN() does not convert the values to a Number, and will not return true for any value that is not of the type Number.

### String
- Single and double quote, and you know how to use them combined!
- `\` escape character 
- length is a property
- Perfect set of methods
- It is important that to remember, strings are immutable in JS
-  + is used to concatenate.
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

### Booleans
- ok: true/false
- All true (objects, and arrays are included) unless 6 falsy values
```
undefined
null
0
-0
NaN
"" // the empty string
```
- Null, and undefined both have no value in them, no property, no method

### Global Object
- All global variable are property of the global object,

### Type Conversion
- JS converts everything to something it is expected to see!
```
Some examples:
10 + " objects" // => "10 objects". 10 -> string
"7" * "4" // => 28: both strings -> numbers
var n = 1 - "x"; // => NaN: "x" can't convert to a number
n + " objects" // => "NaN objects": NaN -> "NaN"
```
- Conversion are automatic, but may want to push to make you code cleaner using `Boolean()`, `Number()`, `String()` or `Object()`
- Note that any value other than null or undefined has a `toString()` method and the result of this method is usually the same as that returned by the String() function.
- working with financial or scientific data
`var n = 123456.789;
n.toFixed(2); // "123456.79"
n.toExponential(3); // "1.235e+5"
n.toPrecision(7); // "123456.8"``

```
