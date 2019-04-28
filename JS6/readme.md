### Here is what are new in JS6

Readme material is coming from Udemy [JS6 tutorial](https://www.udemy.com/javascript-es6-tutorial)

- Array helper functions
    - `forEach`: used to look through the array. 
    - `map`: Generate a new mapped array. Arrays are immutable, but by using this helper function, we will have one good final mapped array. Highly useful in FE web development.
    - `filter`: if internal function gives `true`, we will see it in the filtered array.
    - `find`
    - `every`: all elements in array follow the same rule.
    - `some`: some of the elements in array follow the same rule.
    - `reduce`: internal function takes initial value and element.
- const/let: we are no longer using damn `var`(mother fucker trouble maker)
- Template strings: back ticks with `${}` where js variables go into this `${}`: just look how it makes it easy to make string of JSON!
- Arrow function (Lamda function in Java,C#, etc): 
    - (a,b) => {x,Y,z, return ali;}
    - Implicit return (because a single expression): a => a + b 
        - For compact syntax "single argument is needed for the part one. and sinlge expression is needed for the part two.
        - Compact syntax may make it confusing, do not sit on it.
- Enhanced literal:
    - if the key and value have the same exact name
    - key is a function, k: function(){}, then we can put k()
- Default function argument: function(a, b = 'value'); in JS5 we have to check each individual parameters for its existance.
    - Important note: put null is in parameter list if you want to push it as null, if you put undenifed, it will be the default value in it. function(a, null) is correct, and function(a, undefined) will be function(a, value)
    

    
[Personal] left over practices in the training
- Implementing `Pluck`
- Implementing `Reject`
- Implementing `findWhere`
- Implementing `Unique`
- Review the `when to use arrow functions continue`: very valuable materials
