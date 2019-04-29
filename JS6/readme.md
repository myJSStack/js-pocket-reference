### Here is what are new in JS6

Readme material is coming from Udemy [JS6 tutorial](https://www.udemy.com/javascript-es6-tutorial)

## Every body knows:
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
## New to me: 

### Enhanced literal:
    - if the key and value have the same exact name
    - key is a function, k: function(){}, then we can put k()
### Default function argument: 
function(a, b = 'value'); in JS5 we have to check each individual parameters for its existance.
    - Important note: put null is in parameter list if you want to push it as null, if you put undenifed, it will be the default value in it. function(a, null) is correct, and function(a, undefined) will be function(a, value)

### Rest, Spreed operators: 
    - Rest operator (gather inputs): ...numbers, we capture all of unkown number of inputs and put them in one array called number
    - Spreed operator(split inputs): lets say you have two arrays of a,b and you want to contacs them together in a way that you contact their content.  [...a, ...b]
   
### Destructing
This is about accessing to value of keys in objects or arrays. 
- first scenario [objects]
``` 
const { keyName1, KeyName2 } = objectName; 
```

- 2nd scenario [array] 
``` 
const companies = ['Google', 'FaceBook', 'Uber'];
const [name, name2, ...rest] = companies;
```

- 3rd scenario: The above to can be combined:[array of objects]
```
const companies = [{name:'Google', location:`Mountain View`}, {name:'FaceBook', location:`Menlo Park` }, {name: 'Uber', location: `San Francisco`}];

const [{ location}] = companies; //es5 eaquivalent is companies[0].location

```
- 4th scenario: object of arrays **most complex so far**: challenging to digest.
```
const Google = {
    locations: ['Mountain View', 'New York', 'London']
}

const { locations: [location] } = Google; // es5 equivalent: Google.locations[0]
```
#### How it can improve the code
- We pass an object of arguament instead of long list of arguments which is prone to mistake of order.

### Classes
lets make a class example in ES5
```
// CREATING
// Note that we start with the function keyword
function Car(options) {
   this.title = options.title
   // Note that we do not return a value
}

// ADDING A METHOD IN IT
Car.prototype.drive = function(){
    return 'vroom';
}

// USING IT
const car 1 = new Car({title: Prius});
car1.drive();


// INHERITANCE : look how BAD/FUCKED UP it is 
function Toyota(options) {
    this.color = option.color;
    
    // inheriting a car
    Car.call(this, options);
}

// GOSH!!!
Toyota.prototype = Object.create(Car.prototype);
Toyota.prototype.constructor = Toyota;

```
ok, now lets make a class example in ES6
```
class Car {
    constructor({ title }){
        this.title = title;
    }
    
    //methods
    drive() {
        return 'vroom';
    }
}

//
class Toyota extends Car {
    constructor(options) {
        super(options); // car.constructor
        this.color = options.color;
    }

    hunnk() {
        return 'beep';
    }
}
```

### Generator
Let's see a quick example. Note to the star sign, and the yield keyword
```
function *colors() {
    yeild 'red';
    yield 'blue';
    yield 'green';
}

const myColor = [];
for (let color of colors()) {
    myColors.push(color);
}
```
#### Iteration with generators
Now, let's look into the second example, that we are moving through an object property selectively
```
const engineeringTeam = {
    size : 3,
    department : `engineering`,
    lead : 'Jill',
    manager: 'Alex',
    engineer: 'Dave'
}

function* teamIterator(team) {
    yield team.lead;
    yield team.manager;
    yield team.engineer;
}

const names = [];
for (let name of teamIterator()) {
    names.push(name);
}
```
#### Generator delegation
let say you have QA team too. Note to * beside yield keyword
```
const testingTeam = {
    lead: 'Amanda',
    tester: 'Bill'
}

const engineeringTeam = {
    testingTeam,
    size : 3,
    department : `engineering`,
    lead : 'Jill',
    manager: 'Alex',
    engineer: 'Dave'
}

function* TeamIterator(team) {
    yield team.lead;
    yield team.manager;
    yield team.engineer;
    
    // note to this part
    const testingTeamGenerator = TestingTeamGenerator(team.testingTeam);
    yeild* testingTeamGenerator;
}

function* TestingTeamGenerator(team){
    yeild team.lead;
    yield team.tester;
}

const names = [];
for (let name of teamIterator()) {
    names.push(name);
}
```
#### Generators with symbol iterator
This part helps to clean up above codes. The **[Symbol.iterator] is a ES6 new feature.** Its job is to to tell the iterator how to move over an object.
```
const testingTeam = {
    lead: 'Amanda',
    tester: 'Bill',
    [Symbol.iterator]: function*() {
        yield this.lead;
        yield this.tester;
    }
}

const engineeringTeam = {
    testingTeam,
    size : 3,
    department : `engineering`,
    lead : 'Jill',
    manager: 'Alex',
    engineer: 'Dave',
    [System.iterator]: function*() {
        yield this.lead;
        yield this.manager;
        yield this.engineer;
        yield* this.testingTeam;
    }
}
```


 
[Personal] left over practices in the training
- Implementing `Pluck`
- Implementing `Reject`
- Implementing `findWhere`
- Implementing `Unique`
- Review the `when to use arrow functions continue`: very valuable materials
