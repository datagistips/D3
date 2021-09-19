# javascript

## A voir
- Blocks
- Promises
- DOM elements
- Dictionaries
- Iterators
- forEach
- =>
- bind function

## 19 Septembre
### Functions
Objects

```
function myFunc(theObject) {
  theObject.make = 'Toyota';
}

var mycar = {make: 'Honda', model: 'Accord', year: 1998};
```

```
const square = function(number) { return number * number }
```

Function expressions
```
function map(f, a) {
  let result = []; // Create a new Array
  let i; // Declare variable
  for (i = 0; i != a.length; i++)
    result[i] = f(a[i]);
  return result;
}
const f = function(x) {
   return x * x * x;
}
let numbers = [0, 1, 2, 5, 10];
let cube = map(f,numbers);
```

```
 < 2 ? 1 : n * fac(n - 1)
 ```
Function constructor & eval

hoisted
```
console.log(square(5));
/* ... */
function square(n) { return n * n }
```
works only with function declaration, not function expressions (const...)

```
var num1 = 20,
    num2 = 3,
    name = 'Chamakh';

// This function is defined in the global scope
function multiply() {
  return num1 * num2;
}
```

recursive function

```
function foo(i) {
  if (i < 0)
    return;
  console.log('begin: ' + i);
  foo(i - 1);
  console.log('end: ' + i);
}
foo(3);

// Output:

// begin: 3
// begin: 2
// begin: 1
// begin: 0
// end: 0
// end: 1
// end: 2
// end: 3
```

```
function outside(x) {
  function inside(y) {
    return x + y;
  }
  return inside;
}
fn_inside = outside(3); // Think of it like: give me a function that adds 3 to whatever you give
                        // it
result = fn_inside(5); // returns 8

result1 = outside(3)(5); // returns 8
```
Name conflicts : pas vu

Closures : pas vu

typeof, toLowerCase

arguments.length

Rest parameters

```
function multiply(multiplier, ...theArgs) {
  return theArgs.map(x => multiplier * x);
}

var arr = multiply(2, 1, 2, 3);
console.log(arr); // [2, 4, 6]
```

map, =>


```
var a = [
  'Hydrogen',
  'Helium',
  'Lithium',
  'Beryllium'
];

var a2 = a.map(function(s) { return s.length; });

console.log(a2); // logs [8, 6, 7, 9]

var a3 = a.map(s => s.length);

console.log(a3); // logs [8, 6, 7, 9]

```

**Arrow function**
=>
```
var a3 = a.map(s => s.length);
```

arrow and this
```
function Person() {
  this.age = 0;

  setInterval(() => {
    this.age++; // |this| properly refers to the person object
  }, 1000);
}

var p = new Person();
```

eval, uneval, isNan, isFinite, decodeURI

```
test
```
### Assignement and operators
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators

```
x += y, x *= y, x /= y, 	x **= y, x &= y	
```

right to left
```
const z = (x = y); // Or equivalently: const z = x = y;
```

Destructuring

```
var foo = ['one', 'two', 'three'];

// without destructuring
var one   = foo[0];
var two   = foo[1];
var three = foo[2];

// with destructuring
var [one, two, three] = foo;
```

Strict equal (===)	: Returns true if the operands are equal and of the same type. See also Object.is and sameness in JS.	

bitwise perators : bitwise XOR : ^, NOT : ~, ? >>, ? >>>

binary representation : pas vu

bitwise logical operators : &&, ||, NOT : !

?? nullish coalescing operator. Only returns the second expression, when the first one is "nullish", i.e. null or undefined. 

conditional ternary op. : condition ? val1 : val2

```
var status = (age >= 18) ? 'adult' : 'minor';
```

comma operator : allow multiple variables to be updated each time through the loop.
```
var x = [0,1,2,3,4,5,6,7,8,9]
var a = [x, x, x, x, x];

for (var i = 0, j = 9; i <= j; i++, j--)
//                                ^
  console.log('a[' + i + '][' + j + ']= ' + a[i][j]);
```

```
delete object.property;
delete object[propertyKey];
delete objectName[index];
```

typeof

void and undefined

```
void function test() {
  console.log('boo!');
  // expected output: "boo!"
}();
```

in
```
// built-in objects
'PI' in Math;          // returns true
var myString = new String('coral');
'length' in myString;  // returns true
```

objectName instanceof objectType : Date Array

precedence : pas vu

Functions that assign a value, functions that resolve ta a value

```
this['propertyName']
this.propertyName
```

```
function validate(obj, lowval, hival) {
  if ((obj.value < lowval) || (obj.value > hival))
    console.log('Invalid Value!');
}
```

```
<p>Enter a number between 18 and 99:</p>
<input type="text" name="age" size=3 onChange="validate(this, 18, 99);">
```

new, super
? super : quand l'utiliser

### Numbers and dates
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Numbers_and_dates

0888 // 888 parsed as decimal
Pas vus

Number : à voir

Math, Math.sin

var dateObjectName = new Date([parameters]);

today = new Date();.

A set of integer values for year, month, and day. For example, var Xmas95 = new Date(1995, 11, 25).

set, get, to

getMonth(), getTime(), setTime(), getFullYear(), setFullYEar()

var IPOdate = new Date();
IPOdate.setTime(Date.parse('Aug 9, 1995'));

```
function JSClock() {
  var time = new Date();
  var hour = time.getHours();
  var minute = time.getMinutes();
  var second = time.getSeconds();
  var temp = '' + ((hour > 12) ? hour - 12 : hour);
  if (hour == 0)
    temp = '12';
  temp += ((minute < 10) ? ':0' : ':') + minute;
  temp += ((second < 10) ? ':0' : ':') + second;
  temp += (hour >= 12) ? ' P.M.' : ' A.M.';
  return temp;
}
```

### Text formating
```
const firstString = '2 + 2'; // Creates a string literal value
const secondString = new String('2 + 2'); // Creates a String object
eval(firstString); // Returns the number 4
eval(secondString); // Returns a String object containing "2 + 2"
```
charAt, idexOf, startsWith, split, slice, substr, match, toLowerCase, 

Multi line
```
console.log('string text line 1\n\
string text line 2');
// "string text line 1
// string text line 2"

console.log(`string text line 1
string text line 2`);
// "string text line 1
// string text line 2"
```

Template literals
```
const five = 5;
const ten = 10;
console.log(`Fifteen is ${five + ten} and not ${2 * five + ten}.`);
// "Fifteen is 15 and not 20."
```

internationalization : pas vu

Intl.NumberFormat, Intl.DateTimeFormat, Intl.Collator

### Regular expressions
```
let re = /ab+c/;
let re = new RegExp('ab+c');
```

Assertions
```
const text = 'A quick fox';

const regexpLastWord = /\w+$/;
console.log(text.match(regexpLastWord));
// expected output: Array ["fox"]

const regexpWords = /\b\w+\b/g;
console.log(text.match(regexpWords));
// expected output: Array ["A", "quick", "fox"]

const regexpFoxQuality = /\w+(?= fox)/;
console.log(text.match(regexpFoxQuality));
// expected output: Array ["quick"]
```

\w : word character

A voir : assertions

Escaping : /a\*b/ 

exec, test, match, matchAll, search, replace, replaceAll, split

test or search

exec or match

```
var myRe = new RegExp('d(b+)d', 'g');
var myArray = myRe.exec('cdbbdbsbz');
```

pas vu : flags. m flag : multi line

phone number : voir page4.html

```
var re = /(?:\d{3}|\(\d{3}\))([-\/\.])\d{3}\1\d{4}/;
document.querySelector('#phone')
`${phoneInput.value}
var out = document.querySelector('#out');
out.textContent
```

## 18 Septembre
- alert, console.log
- semicolon
- var : local and global, let : in block, const global : in block, read only
- variable scope
- accents ok
- var a; undefined
- a == undefined
- in a function : local variable
- hoisting :you can refer to a variable declared later, without getting an exception.
- in web pages, global object = window
- const MY_OBJECT = {'key': 'value'};  MY_OBJECT.key = 'otherValue'; ok
- properties and content not protected
- array.push
- null, undefined, Object
- var answer = 42; answer = 'Thanks for all the fish...';
- parseInt, parseFloat
- Literals
- exponent e or E followed by integer
- Objects var car = { myCar: 'Saturn', getCar: carTypes('Honda'), special: sales };
- name === 'Honda'
- regexp : var re = /ab+c/;
- `In JavaScript, template strings can run
 over multiple lines, but double and single
 quoted strings cannot.`
 - string interpolation : var name = 'Bob', time = 'today';
 - `Hello ${name}`

### Tagged templates
```
let myTag = (str, name, age) => `${str[0]}${name}${str[1]}${age}${str[2]}`;
let [name, age] = ['Mika', 28];
myTag`Participant "${ name }" is ${ age } years old.`;
```

```
var str = 'this string \
is broken \
across multiple \
lines.'
```

- block statements

```
var x = 1;
{
  var x = 2;
}
console.log(x); // outputs 2

if ((x = y)) {
  /* statements here */
}
```

- falsy : false, undefined, null, O, NaN, ""
- var b = new Boolean(false);

### DOM
```
${document.form1.threeChar.value}
```

switch
```
switch () { case xxx: statement; break
```

use break to stop

try..catch

throw

### Objects
```
function UserException(message) {
  this.message = message;
  this.name = 'UserException';
}
```
Ne fonctionne pas

try, catch, finally

```
function f() {
  try {
    console.log(0);
    throw 'bogus';
  } catch(e) {
    console.log(1);
    return true;    // this return statement is suspended
                    // until finally block has completed
    console.log(2); // not reachable
  } finally {
    console.log(3);
    return false;   // overwrites the previous "return"
    console.log(4); // not reachable
  }
  // "return false" is executed now
  console.log(5);   // not reachable
}
```

Error object

### Loops
```
for(let x = 0; x<5;x++)
for ([initialExpression]; [conditionExpression]; [incrementExpression])
```

```
let btn = document.getElementById('btn');
btn.addEventListener('click', function() {
  alert('Number of options selected: ' + howMany(document.selectForm.musicTypes));
});

document.selectForm.musicTypes
```

do..while

x += n

### Labeled statement
```
markLoop:
while (theMark === true) {
   doSomething();
}

break;
break [label];
```

à voir : break labelCancelLoops;
continue : un peu comme pass

à voir : continue [label]

for..in
```
for (let i in obj) {
```

for..of

```
const arr = [3, 5, 7];
arr.foo = 'hello';

for (let i in arr) {
   console.log(i); // logs "0", "1", "2", "foo"
}

for (let i of arr) {
   console.log(i); // logs 3, 5, 7
}
```
