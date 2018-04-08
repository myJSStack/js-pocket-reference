## Types, Values, and Variables
- Date types in JS: Primitives, Objects
- Primitive data type: `Number`, `Boolean`, `String`.
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
- Arithmetic in JavaScript does not raise errors in cases of overflow,
underflow, or division by zero.
- When the result of a numeric
operation is larger than the largest representable number
(overflow), the result is a special infinity value, which Java-
Script prints as Infinity. Similarly, when a negative value becomes
larger than the largest representable negative number,
the result is negative infinity, printed as -Infinity.
- Division by zero is not an error in JavaScript: it simply returns
infinity or negative infinity.
- NaN: zero divided by zero, Infinity divided by Infinity, sqrt(a negative number)
- `== Nan` doesn't work  => `isNaN()` is the ONE :) 
-  (global isNaN() function, converts the tested value to a Number, then tests it.)
- Number.isNaN() does not convert the values to a Number, and will not return true for any value that is not of the type Number.

### String
- 
