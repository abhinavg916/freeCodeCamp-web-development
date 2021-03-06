# Basic JavaScript

## Declare JavaScript Variables

- JavaScript provides eight different data types which are undefined, null, boolean, string, symbol, bigint, number, and object

## Understanding Uninitialized Variables

- When JavaScript variables are declared, they have an initial value of undefined.
- If you do a mathematical operation on an undefined variable your result will be NaN which means "Not a Number"
- If you concatenate a string with an undefined variable, you will get a literal string of "undefined"

## Understanding Case Sensitivity in Variables

- Best Practice - The variable names in JavaScript in camelCase. In camelCase, multi-word variable names have the first word in lowercase and the first letter of each subsequent word is capitalized.

## Declare String Variables Passed

- String is a series of zero or more characters enclosed in single or double quotes

## Escaping Literal Quotes in Strings

- In JavaScript, you can escape a quote from considering it as an end of string quote by placing a backslash (`\`) in front of the quote
- Quoting Strings with Single Quotes - `conversation = 'Finn exclaims to Jake, "Algebraic!"';` => Acceptable
- However, this becomes a problem if you need to use the outermost quotes within it. Remember, a string has the same kind of quote at the beginning and end. But if you have that same quote somewhere in the middle, the string will stop early and throw an error

```
goodStr = 'Jake asks Finn, "Hey, let\'s go on an adventure?"';
badStr = 'Finn responds, "Let's go!"'; // Throws an error
```

## Escape Sequences in Strings

```
\'	single quote
\"	double quote
\\	backslash
\n	newline
\r	carriage return
\t	tab
\b	word boundary
\f	form feed
```

## Concatenating Strings with the Plus Equals Operator

- Js supports the use of `+=` operator to concatenate a string onto the end of an existing string variable.

## Appending Variables to StringsPassed

- Append variables to a string using the plus equals `+=` operator

```
var anAdjective = "awesome!";
var ourStr = "freeCodeCamp is ";
ourStr += anAdjective;
// ourStr is now "freeCodeCamp is awesome!"
```

## Use of Bracket Notation to Find the Character in a String

```
var firstName = "Charles";
var firstLetter = firstName[0]; // firstLetter is "C
```

## Find the Length of a String

- The length of a String value by writing `.length` after the string variable or string literal

## Understand String Immutability

- In JavaScript, String values are immutable, which means that they cannot be altered once created
- The individual characters of a string literal cannot be changed
- The only way to change myStr would be to assign it with a new string

```
var myStr = "Bob";
myStr[0] = "J"; // Error
```

```
var myStr = "Bob";
myStr = "Job"; // Correct
```

## Store Multiple Values in one Variable using JavaScript Arrays

- It can contain multiple data type into one arraly like both a string and a number

```
var sandwich = ["peanut butter", "jelly", "bread", 100];
```

## Nest one Array within Another Array

- You can also nest arrays within other arrays, like below:

```
[["Bulls", 23], ["White Sox", 45]]
```

## Access Multi-Dimensional Arrays With Indexes

- One way to think of a multi-dimensional array, is as an array of arrays
- When you use brackets to access your array, the first set of brackets refers to the entries in the outer-most (the first level) array, and each additional pair of brackets refers to the next level of entries inside

```
var arr = [
  [1,2,3],
  [4,5,6],
  [7,8,9],
  [[10,11,12], 13, 14]
];
arr[3]; // equals [[10,11,12], 13, 14]
arr[3][0]; // equals [10,11,12]
arr[3][0][1]; // equals 11
```

- Note - There shouldn't be any spaces between the array name and the square brackets, like array [0][0] and even this array [0] [0] is not allowed. Although JavaScript is able to process this correctly, this may confuse other programmers reading your code

## Manipulate Arrays With push()

- An easy way to append data to the end of an array is via the push() function
- `.push()` takes one or more parameters and "pushes" them onto the end of the array

```
var arr1 = [1,2,3];
arr1.push(4);
// arr1 is now [1,2,3,4]

var arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
// arr2 now equals ["Stimpson", "J", "cat", ["happy", "joy"]]
```

## Manipulate Arrays With pop()

- `.pop()` is used to "pop" a value off of the end of an array. We can store this "popped off" value by assigning it to a variable. In other words, .pop() removes the last element from an array and returns that element
- Any type of entry can be "popped" off of an array - numbers, strings, even nested arrays

```
var threeArr = [1, 4, 6];
var oneDown = threeArr.pop();
console.log(oneDown); // Returns 6
console.log(threeArr); // Returns [1, 4]
```

## Manipulate Arrays With shift()

- pop() always removes the last element of an array. What if you want to remove the first?
- That's where `.shift()` comes in. It works just like .pop(), except it removes the first element instead of the last

```
var ourArray = ["Stimpson", "J", ["cat"]];
var removedFromOurArray = ourArray.shift();
// removedFromOurArray now equals "Stimpson" and ourArray now equals ["J", ["cat"]].
```

## Manipulate Arrays With unshift()

- Not only can you shift elements off of the beginning of an array, you can also unshift elements to the beginning of an array i.e. add elements in front of the array
- `.unshift()` works exactly like .push(), but instead of adding the element at the end of the array, unshift() adds the element at the beginning of the array

```
var ourArray = ["Stimpson", "J", "cat"];
ourArray.shift(); // ourArray now equals ["J", "cat"]
ourArray.unshift("Happy");
// ourArray now equals ["Happy", "J", "cat"]
Add ["Paul",35] to the beginning of the myArray variable using unshift().
```

## Write Reusable JavaScript with Functions

- In JavaScript, we can divide up our code into reusable parts called functions

```
function functionName() {
  console.log("Hello World");
}
```

- You can call or invoke this function by using its name followed by parentheses, like this: functionName(); Each time the function is called it will print out the message "Hello World" on the dev console. All of the code between the curly braces will be executed every time the function is called

## Passing Values to Functions with Arguments

- Parameters are variables that act as placeholders for the values that are to be input to a function when it is called
- When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or "passed") into a function when it is called are known as arguments

```
function testFun(param1, param2) {
  console.log(param1, param2);
}
```

- Then we can call testFun: testFun("Hello", "World"); We have passed two arguments, "Hello" and "World". Inside the function, param1 will equal "Hello" and param2 will equal "World". Note that you could call testFun again with different arguments and the parameters would take on the value of the new arguments.

## Global Scope and Functions

- In JavaScript, scope refers to the visibility of variables. Variables which are defined outside of a function block have Global scope. This means, they can be seen everywhere in your JavaScript code.
- Variables which are used without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var.

## Local Scope and Functions

- Variables which are declared within a function, as well as the function parameters have local scope. That means, they are only visible within that function.
- Here is a function myTest with a local variable called loc.

```
function myTest() {
  var loc = "foo";
  console.log(loc);
}
myTest(); // logs "foo"
console.log(loc); // loc is not defined
loc is not defined outside of the function.
```

- The editor has two console.logs to help you see what is happening. Check the console as you code to see how it changes. Declare a local variable myVar inside myLocalScope and run the tests.
- Note: The console will still have 'ReferenceError: myVar is not defined', but this will not cause the tests to fail.

## Global vs. Local Scope in Functions

- It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

```
var someVar = "Hat";
function myFun() {
  var someVar = "Head";
  return someVar;
}
```

- The function myFun will return "Head" because the local version of the variable is present.

## Understanding Undefined Value returned from a Function

- A function can include the return statement but it does not have to. In the case that the function doesn't have a return statement, when you call it, the function processes the inner code but the returned value is undefined.

```
var sum = 0;
function addSum(num) {
  sum = sum + num;
}
addSum(3); // sum will be modified but returned value is undefined
```

- addSum is a function without a return statement. The function will change the global sum variable but the returned value of the function is undefined.

## Stand in Line

- In Computer Science a queue is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue.

```
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
  return arr.shift();
  // Only change code above this line
}

// Setup
var testArr = [1,2,3,4,5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

## Add === Operator

## Multiple Identical Options in Switch Statements

- If the break statement is omitted from a switch statement's case, the following case statement(s) are executed until a break is encountered. If you have multiple inputs with the same output, you can represent them in a switch statement like this:

```
switch(val) {
  case 1:
  case 2:
  case 3:
    result = "1, 2, or 3";
    break;
  case 4:
    result = "4 alone";
}
```

- Cases for 1, 2, and 3 will all produce the same result.

## Replacing If Else Chains with Switch

- Switch Cases comparision in JavaScript uses strictly `===` comparision operator
- If you have many options to choose from, a switch statement can be easier to write than many chained if/else if statements. The following:

```
if (val === 1) {
  answer = "a";
} else if (val === 2) {
  answer = "b";
} else {
  answer = "c";
}
can be replaced with:

switch(val) {
  case 1:
    answer = "a";
    break;
  case 2:
    answer = "b";
    break;
  default:
    answer = "c";
}
```

## Returning Boolean Values from Functions

- You may recall from Comparison with the Equality Operator that all comparison operators return a boolean true or false value.
- Sometimes people use an if/else statement to do a comparison, like this:

```
function isEqual(a,b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:

function isEqual(a,b) {
  return a === b;
}
```

## Build JavaScript ObjectsPassed

- You may have heard the term object before.
- Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.
- Objects are useful for storing data in a structured way, and can represent real world objects, like a cat.
- Here's a sample cat object:

```
var cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
```

## Accessing Object Properties with Dot Notation

- There are two ways to access the properties of an object: dot notation (.) and bracket notation ([]), similar to an array.
- Dot notation is what you use when you know the name of the property you're trying to access ahead of time.
- Here is a sample of using dot notation (.) to read an object's property:

```
var myObj = {
  prop1: "val1",
  prop2: "val2"
};
var prop1val = myObj.prop1; // val1
var prop2val = myObj.prop2; // val2
```

- The second way to access the properties of an object is bracket notation ([]). If the property of the object you are trying to access has a space in its name, you will need to use bracket notation.
- However, you can still use bracket notation on object properties without spaces.
- Here is a sample of using bracket notation to read an object's property:

```
var myObj = {
  "Space Name": "Kirk",
  "More Space": "Spock",
  "NoSpace": "USS Enterprise"
};
myObj["Space Name"]; // Kirk
myObj['More Space']; // Spock
myObj["NoSpace"];    // USS Enterprise
```

## Updating Object Properties

- After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.
- For example, let's look at ourDog:

```
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```

- Since he's a particularly happy dog, let's change his name to "Happy Camper". Here's how we update his object's name property: ourDog.name = "Happy Camper"; or ourDog["name"] = "Happy Camper"; Now when we evaluate ourDog.name, instead of getting "Camper", we'll get his new name, "Happy Camper".

## Add New Properties to a JavaScript Object

- You can add new properties to existing JavaScript objects the same way you would modify them.
- Here's how we would add a "bark" property to ourDog:

```
ourDog.bark = "bow-wow";

or

ourDog["bark"] = "bow-wow";
```

- Now when we evaluate ourDog.bark, we'll get his bark, "bow-wow".
- Example:

```
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
```

## Delete Properties from a JavaScript Object

- We can also delete properties from objects like this: `delete ourDog.bark;`
- Example:

```
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"],
  "bark": "bow-wow"
};

delete ourDog.bark;
```

## Using Objects for Lookups Passed

- Objects can be thought of as a key/value storage, like a dictionary. If you have tabular data, you can use an object to "lookup" values rather than a switch statement or an if/else chain. This is most useful when you know that your input data is limited to a certain range.
- Here is an example of a simple reverse alphabet lookup:

```
var alpha = {
  1:"Z",
  2:"Y",
  3:"X",
  4:"W",
  ...
  24:"C",
  25:"B",
  26:"A"
};
alpha[2]; // "Y"
alpha[24]; // "C"

var value = 2;
alpha[value]; // "Y"
```

## Testing Objects for Properties

- Sometimes it is useful to check if the property of a given object exists or not. We can use the .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty() returns true or false if the property is found or not.
- Example

```
var myObj = {
  top: "hat",
  bottom: "pants"
};
myObj.hasOwnProperty("top");    // true
myObj.hasOwnProperty("middle"); // false
```

## Manipulating Complex Objects

- Sometimes you may want to store data in a flexible Data Structure. A JavaScript object is one way to handle flexible data. They allow for arbitrary combinations of strings, numbers, booleans, arrays, functions, and objects.
- Here's an example of a complex data structure:

```
var ourMusic = [
  {
    "artist": "Daft Punk",
    "title": "Homework",
    "release_year": 1997,
    "formats": [
      "CD",
      "Cassette",
      "LP"
    ],
    "gold": true
  }
];
```

- This is an array which contains one object inside. The object has various pieces of metadata about an album. It also has a nested "formats" array. If you want to add more album records, you can do this by adding records to the top level array. Objects hold data in a property, which has a key-value format. In the example above, "artist": "Daft Punk" is a property that has a key of "artist" and a value of "Daft Punk". JavaScript Object Notation or JSON is a related data interchange format used to store data.

```
{
  "artist": "Daft Punk",
  "title": "Homework",
  "release_year": 1997,
  "formats": [
    "CD",
    "Cassette",
    "LP"
  ],
  "gold": true
}
```

- Note - You will need to place a comma after every object in the array, unless it is the last object in the array.

## Accessing Nested Objects

- The sub-properties of objects can be accessed by chaining together the dot or bracket notation.
- Here is a nested object:

```
var ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": {
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};
ourStorage.cabinet["top drawer"].folder2;  // "secrets"
ourStorage.desk.drawer; // "stapler"
```

## Accessing Nested Arrays

- As we have seen in earlier examples, objects can contain both nested objects and nested arrays. Similar to accessing nested objects, Array bracket notation can be chained to access nested arrays.
- Here is an example of how to access a nested array:

```
var ourPets = [
  {
    animalType: "cat",
    names: [
      "Meowzer",
      "Fluffy",
      "Kit-Cat"
    ]
  },
  {
    animalType: "dog",
    names: [
      "Spot",
      "Bowser",
      "Frankie"
    ]
  }
];
ourPets[0].names[1]; // "Fluffy"
ourPets[1].names[0]; // "Spot"
```

## Record Collection

- You are given a JSON object representing a part of your musical album collection. Each album has several properties and a unique id number as its key. Not all albums have complete information.
- Write a function which takes an album's id (like 2548), a property prop (like "artist" or "tracks"), and a value (like "Addicted to Love") to modify the data in this collection.

```
// Setup
var collection = {
  2548: {
    album: "Slippery When Wet",
    artist: "Bon Jovi",
    tracks: [
      "Let It Rock",
      "You Give Love a Bad Name"
    ]
  },
  2468: {
    album: "1999",
    artist: "Prince",
    tracks: [
      "1999",
      "Little Red Corvette"
    ]
  },
  1245: {
    artist: "Robert Palmer",
    tracks: [ ]
  },
  5439: {
    album: "ABBA Gold"
  }
};

// Only change code below this line
function updateRecords(id, prop, value) {


  return collection;
}

updateRecords(5439, "artist", "ABBA");
```

## Iterate with JavaScript While Loops

- Add Elements to array

```
// Setup
var myArray = [];
var i = 5;
while( i >= 0){
  myArray.push(i);
  i--;
}

// Only change code below this line
```

## Nesting For Loops

- If you have a multi-dimensional array, you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays. Here is an example:

```
var arr = [
  [1,2], [3,4], [5,6]
];
for (var i=0; i < arr.length; i++) {
  for (var j=0; j < arr[i].length; j++) {
    console.log(arr[i][j]);
  }
}
```

## Generate Random Fractions with JavaScript

- JavaScript has a Math.random() function that generates a random decimal number between 0 (inclusive) and not quite up to 1 (exclusive). Thus Math.random() can return a 0 but never quite return a 1

## Generate Random Whole Numbers within a Range

- To do this, we'll define a minimum number min and a maximum number max.
- Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing: `Math.floor(Math.random() * (max - min + 1)) + min`

## Use the parseInt Function

- The parseInt() function parses a string and returns an integer. Here's an example:

```
var a = parseInt("007");`// The above function converts the string "007" to an integer 7. If the first character in the string can't be converted into a number, then it returns NaN.
```

## Use the parseInt Function with a Radix

- The parseInt() function parses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.
- The function call looks like:

```
parseInt(string, radix);
```

- And here's an example:

```
var a = parseInt("11", 2);
```

- The radix variable says that "11" is in the binary system, or base 2. This example converts the string "11" to an integer 3.

## Use the Conditional (Ternary) Operator

- The conditional operator, also called the ternary operator, can be used as a one line if-else expression.
- The syntax is:

```
condition ? statement-if-true : statement-if-false;
```

## Use Multiple Conditional (Ternary) Operators

- The following function uses if, else if, and else statements to check multiple conditions:

```
function findGreaterOrEqual(a, b) {
  if (a === b) {
    return "a and b are equal";
  }
  else if (a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}
```

- The above function can be re-written using multiple conditional operators:

```
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal"
    : (a > b) ? "a is greater"
    : "b is greater";
}
```

- It is considered best practice to format multiple conditional operators such that each condition is on a separate line, as shown above. Using multiple conditional operators without proper indentation may make your code hard to read. For example:

```
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" : (a > b) ? "a is greater" : "b is greater";
}
```
