# Objects
- An object is an unordered collection of properties, each of which has a name and a value. Property names are strings, so we can say that objects map strings to values.
- This string-to-value mapping goes by various names: `hash`, `hashtable`, `dictionary`, `associative array`.
- In addition to maintaining its own set of properties, a JavaScript object also inherits the properties of another object, known as its “prototype.” 
- **Any value in JavaScript that is not a string, a number, true, false, null, or undefined is an object.**
- Objects are **mutable** and are manipulated **by reference** rather than by value

### Creating Objects
#### (I) Object Literals
```
var empty = {}; // An object with no properties
var point = { x:0, y:0 }; // Two properties
var point2 = { // Another object literal
 x:point.x, // With more complex properties
 y:point.y+1
};
var book = { // Nonidentifier property names are quoted
 "main title": "JavaScript", // space in property name
 'sub-title': "Pocket Ref", // punctuation in name
 "for": "all audiences", // reserved word name
};
```
#### (II) Creating Objects with new Object()
```
var o = new Object()
```

**PROTOTYPE: Every JavaScript object has a second JavaScript object (or null, but this is rare) associated with it. This second object is known as a prototype, and the first object inherits properties from the prototype**

#### (III) Object.create()
1.
```
// o1 inherits properties x and y.
var o1 = Object.create({x:1, y:2});
```
2.
```
// o2 inherits no properties or methods.
var o2 = Object.create(null);
```
3.
```
// o3 is like {} or new Object().
var o3 = Object.create(Object.prototype);
```

### Properties
#### Property Inheritance
- JavaScript objects have a set of “own properties,” and they also inherit a set of properties from their prototype object.
```
// o inherits object methods from Object.prototype
var o = {}
o.x = 1; // and has an own property x.
// p inherits properties from o and Object.prototype
var p = inherit(o);
p.y = 2; // and has an own property y.
```

#### Deleting Properties
- The delete operator removes a property from an object.
```
delete book.author; // book now has no author.
delete book["main title"]; // or a "main title", either.
```

#### Testing Properties
- `hasOwnProperty()`: method of an object tests whether that object has an own property with the given name. _It returns false for inherited properties._
- `propertyIsEnumerable()`: method refines the hasOwnProperty() test. It returns true only if the named property is an own
property and its enumerable attribute is true.
- `in operator`:r expects a property name (as a string) on its left side and an object on its right. It returns true if the object has
an own property or an inherited property by that name.
