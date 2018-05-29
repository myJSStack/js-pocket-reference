# Arrays
- Ordered elements by index number, in JS, they are dynamic.
- Array elements in JS can be different type.
- Thre is no multidimentional array, but you can simulate it.
### Creating Arrays
1. Array literal(almost alway simpler): `a = [1, 2, 3]`, `b = [1,,2]`, `c=[,,]` note that missing elements are `undefined`, and `trailing ,` is optioal
2. Using array constructor: `new Array()`, `new Array(10)`, `new Array(2,3, 'a')`
### Array Elements and Length
1. access is possible with bracket []
2. ***length property is writable***
### Array methods
1. `Array.join()`: You can specify the separator, if there is noting, then the separator will be camma. (It always come versus with `String.split("")`)
2. `Array.reverse()`: in place, reserse the order of an array.
3. `Array.sort()`:in place, sorts alphabetically an array.
```
- To sort an array with something other than alphabet, you must pass a comparision function inside.
- Easy: Two `a,b` inputs, the `function desides` a should come first or b.
- return < 0 value when a is before b
- return > 0 value when a is after b
- return 0 value when a = b
```
4. `concate()`: create and concate the origin array with the one in argument
5. `slice()`: create and return slice of the array. Arg can be negative
6. `splice()`: (create and return, also original array isDirty) general-purpose method for adding and removing elements to an array
```
- first arg: starting position for add/remove
- second arg: number of delecting elements
- 3rd, 4th are the adding elements
```
7. `Push()`: in place adds to the end
8. `Pop()`: in place remove from the end
9. `unshift()`: in place add to the beginning
10. `shift()`: in place remove for the beginning.
11. `toString()`: convert array to string; comma separated. 

### Array methods introduced in ES5
12. `forEach()`: 2nd, and 3rd are optional
```
forEach(function(value, index, array){
....
})
```
13. `map()`: create new mapped array; structure is like forEach()
14. `filter()`: create newly filtered array, input args are like forEach() but if the returning value is boolean
15. `every()` equals to "FOR ALL": inside function returns boolean
16. `some()` equals to "THERE EXIST" : inside function returns boolean
*** every returns true, and some returns false on an empty array***
17. `reduce()`:  Output is a single value.  Reduce has two args; action function, initial value for the returning value.
action function is diffent from the above. function has two args; result so far, and the value
18. `reduceRight()`:  same as reduce but from right side of array
19. `indexOf()`: search an array for an element with a specified value, and return the index of the first such
element found, or –1 if none is found.
20. `lastIndexOf()`: searches from end to beginning

