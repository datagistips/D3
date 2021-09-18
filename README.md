# javascript

## A voir
- Blocks
- Promises
- DOM elements
- Dictionaries
- Iterators
- forEach
- =>

## 18 Septembre 2021
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
let myTag = (str, name, age) => `${str[0]}${name}${str[1]}${age}${str[2]}`;
let [name, age] = ['Mika', 28];
myTag`Participant "${ name }" is ${ age } years old.`;

var str = 'this string \
is broken \
across multiple \
lines.'

- block statements

var x = 1;
{
  var x = 2;
}
console.log(x); // outputs 2

if ((x = y)) {
  /* statements here */
}

- falsy : false, undefined, null, O, NaN, ""
- var b = new Boolean(false);

### DOM
${document.form1.threeChar.value}

- switch () { case xxx: statement; break
- use break to stop
- try..catch
- throw

### Objects
function UserException(message) {
  this.message = message;
  this.name = 'UserException';
}

Ne fonctionne pas

- try, catch, finally

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

- Error object

### Loops
- for(let x = 0; x<5;x++)
- for ([initialExpression]; [conditionExpression]; [incrementExpression])

let btn = document.getElementById('btn');
btn.addEventListener('click', function() {
  alert('Number of options selected: ' + howMany(document.selectForm.musicTypes));
});

document.selectForm.musicTypes

- do..while
- x += n

### Labeled statement
markLoop:
while (theMark === true) {
   doSomething();
}

break;
break [label];
- à voir : break labelCancelLoops;
- continue : un peu comme pass
- à voir : continue [label]
-   for (let i in obj) {
-   for..of

const arr = [3, 5, 7];
arr.foo = 'hello';

for (let i in arr) {
   console.log(i); // logs "0", "1", "2", "foo"
}

for (let i of arr) {
   console.log(i); // logs 3, 5, 7
}






