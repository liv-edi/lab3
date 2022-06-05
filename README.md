## Lab 3

In this lab we used a car object provided to do the rest of the lab. We created vin and year variables using object deconstructing assigned to the vin and year values from the car object. We created an arroe function expression getCarMakeModelImplicit, getCarMakeModelExplicit, getCarMakeModelDestructure that returns the same formatted car output as getCarMakeModel. We created a for..in loop to list all the properties of an object. We created a for..of loop to list all values of an array. we used module.exports.

Technologies used in this lab:
- VSCode
- Node.js

The purpose of this lab was to practice refactoring JS code destructuring an object, converting normal functions into arrow function expression, usinf for..in syntax with objects, using for..of syntax with arrays, creating a Node.js code module using modiule.exports, importing a Node.js compatible code module using require, and using the spread operator.

From doing this lab I learned how to extend the functionality of my code so that I can use it in multiple ways. I also learned about code modules and module.exports.

```
// TODO Part 11: Import reverseString() and concatenateString()
// functions from lab-03-module.js module using require()
const {reverseString, concatenateString} = require('./lab-03-module.js');

// Declare a specific car object
let car = {
    make: "Ford",
    model: "Mustang",
    vin: "4S3BMHB68B3286050",
    color: "Red",
    year: 2019,
    mileage: 1234,
    used: true,
    owners: [
        { last: "Last1", first: "First1" },
        { last: "Last2", first: "First2" }
    ]
}

// Assign car VIN number and year to constant variables
//const vin = car.vin;
//const year = car.year;
const {vin, year} = car;

// TODO Part 2: Create vin and year variables using object destructuring
// Comment out the original code using single line comments
/*
   Important: The instructions and the following code mix vin/year and
   make/model. You can replace car.make and car.model in the following code
   with either vin and year or make and model.
*/
//const {make, model} = car;

// Declare a normal function that returns formatted car info
function getCarMakeModel(car) {
    return car.make + " " + car.model;
    //return `${make} ${model}`;
}
console.log(0, getCarMakeModel(car));

// TODO Part 3: Create arrow function expression getCarMakeModelImplicit
// and template literal that returns the same formatted car info as
// getCarMakeModel(). The arrow function MUST NOT use a return 
// statement (use implicit return)
// Include a console.log statement similar to getCarMakeModel,
// but increment the number from 0 to 1.
const getCarMakeModelImplicit = (car) => (car.make + " " + car.model);
console.log(1, getCarMakeModelImplicit(car));

// TODO Part 4: Create arrow function expression getCarMakeModelExplicit
// and template literal that returns the same formatted car info as
// getCarMakeModel(). The arrow function MUST use a return 
// statement (use explicit return)
// Include a console.log statement similar to getCarMakeModel,
// but increment the number from 0 to 2.
const getCarMakeModelExplicit = (car) => {return (car.make + " " + car.model);};
console.log(2, getCarMakeModelExplicit(car));

// TODO Part 5: Create arrow function expression getCarMakeModelDestructure
// and template literal that returns the same formatted car info as
// getCarMakeModel(). The arrow function MUST destructure the 
// car properties, which will also require using an explicit return.
// Include a console.log statement similar to getCarMakeModel,
// but increment the number from 0 to 3.
const getCarMakeModelDestructure = (car) => {const {make, model} = car; 
return `${make} ${model}`;};
console.log(3, getCarMakeModelDestructure(car));

// TODO Part 6: Study the following code that will list all 
// properties of an object using for..in syntax. The
// listing will include inherited properties, so the
// hasOwnProperty() method is used to only list properties
// defined in the current object
for (let prop in car) {
    if (car.hasOwnProperty(prop)) {
        console.log(prop);
    }
}

// Display all values of an array
const primes = [2,3,5,7,11];
//for (let index = 0; index < primes.length; index++) {
//    console.log(primes[index]);
//}

// TODO Part 7: Display all array values using for..of syntax
// Comment out the original for loop code using single line comments
for (const number of primes) {
    console.log(number);
}

// TODO Part 12: Import and use reverseString() and concatenateString() in
// a single line of code to produce the following output to the console: cbacba
console.log(concatenateString(reverseString("cbacba")));
```

```
// TODO Part 9: Add the reverseString function to the module.exports object
// for import using require()

// TODO Part 10: Add an anonymous function concatenateString that takes a string
// as a parameter, and returns the original concatenated to itself
//const concatenateString = function(str) {return `${str + str}`};
module.exports = {
    reverseString,
    concatenateString: function(str) {return `${str + str}`}
};

// TODO Part 8: Reference the following website to use the spread operator
// to reverse the string for reverseString(str) function. Comment out the
// original return line of code.
// https://betterprogramming.pub/5-ways-to-reverse-a-string-in-javascript-466f62845827
function reverseString(str) {
//    return str.split("").reverse().join("");
    return [...str].reverse().join("");
};
```
