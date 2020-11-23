# Javascript

Important links:
[Conditional Rendering](https://www.robinwieruch.de/conditional-rendering-react)
[Object Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

Variable declaration

`var`, `const`, and `let`

Variables with `const` - Read-Only (once initialized using `const`, cannot be reassigned)

Additional keywords allow programmer to decide scope options for defined variables.

1) var - function in which the varaible is declared
2) let - Block in which the varaible is declared
3) const - Block in which the varaible is declared

> Block scopes are what you get when you use if statements, for statements, or write code inside curly brackets

```
function foo(){
  for (var i=0; i<5 ; i++){
    console.log(i);
  }
  console.log(i); // This variable i is only accessible within the curly brackets if you use the 'let' keyword instead of 'var'
}

foo();
```

# Rules of Thumb

1) Don't use `var` - because `let` and `const` are more specific
2) Default to `const`, because it cannot be re-assigned or re-declared
3) Use `let` when you want to re-assign the variable in the future
4) Always prefer using `let` over `var`, and `const` over `let`

Typically `let` is used in a `for loop` for incrementing the interator.

`const` is normally used for keeying JS variables unchanged. Even though it is possible to change the inner properties of objects and arrays when using `const`.

The variable declaration shows the INTENT of keeping the variable unchanged!

# Operators and Expressions

1) Unary - takes only one operand (arguments)
2) Binary - takes two operands (arguments)

Example Binary Operators:

Arthimetic Operators
- `+, - , *, /`

Assignment Operators
- `=, +=, -=, *=`

Logical Operators
- `|| , && , ! `

Comma Operator - evalutes each operand from LEFT TO RIGHT, and returns the value of the RIGHT MOST OPERAND
- ` , `
```
console.log("\n Comma Operator")
var a = 4;
a = (a++, a);
console.log("The value for expression with comma operator is: " + a) //returns 5
//returns 5
```

Comparison Operators
- `< , > , == , !=`

Bitwise Operators
- `& , | , ^ `

String Operators
- ` + `

Conditional Operators
- `? : ` (teriary operator)

```
//Conditional Operator
console.log("\n ****Conditional Operator****")
var num_of_months = 13
var ans = (num_of_months > 12) ? "Invalid" : "Valid"
console.log(ans) //Returns Invalid
```

> A comma operator `,` is used when you awant to evaluate an expression from left to right.

# Unary Operators

Some of the most common unary operators in JS are:
- `typeof` -- Returns the type of the given operand
- `delete` -- Deletes an object, object's attribute or an instance in an array
- `void` -- specifics that an expression does not return anything
- Increment operators `++, --`

# Deep Equals vs. Double Equals in JS

` ===` is the **deep equals** operator. This performs TYPE COMPARISON.
` == ` is a more shallow equals operator. Converts the type of one of the operands to make their types the same.

```
// Shallow Equals
console.log(1 == 1); //returns true
console.log('1' == 1); //returns true

// Deep Equals
console.log(1 === 1); //returns true
console.log('1' === 1); //returns false
```

# Expressions

Anything that evaluates to a **value** in JS is called an expression.

Some of the basic expressions and keywords used in JS are:

1) `this` - points to the current object
2) `super` - calls methods on an object's parent, for example, call parent's constructor
3) `function` - used to defined a function
4) `function*` - used to defined a GENERATOR function
5) `async function` - used to define an async function

# Ternary Operator in React - Aka. Conditional Operator (? :)

Takes three operands, and returns a value based on some condition.

It's an alternative for the `if statement`. This could be used for multiple purposes and comes in very handy in React as well!

Displaying JS strings, objects, and arrays in React is NOT enough. 

If-else statement for `conditional rendering`. You cannot use an if-else statement directly in JSX (ES 6), but you can return early from the rendering function.

Return `null` is valid in ReAct when displaying nothing. Just like we did in the example given below.

> Conditional rendering in React uses JS operators like `if` or the conditional operators to create elements representing the current state, and let React show or hide a certain UI element based on a condition.

```
import React from 'react';

export default class App extends React.Component {
  render() {
    const users = [
      { name: 'Robin' },
      { name: 'Markus' },
    ];

    const showUsers = true;
    if (!showUsers) {
      return null;
    }

    return (
      <ul>
        {users.map(user => <li>{user.name}</li>)}
      </ul>
    );
  }
}
```

```
import React from 'react';

export default class App extends React.Component {
  render() {
       const users = [
      { name: 'Robin' },
      { name: 'Markus' },
    ];
    const showUsers = true;
    return (
      <div>
        {
          showUsers ? (
            <ul>
              {users.map(user => <li>{user.name}</li>)}
            </ul>
          ) : (
            null
          )
        }
      </div>
    );
  }
}
```

Once again, most of React is actually JavaScript, and not anything React specific.

# Object Destructuring & Spread Operators

-  Rather than assigning them to avaraible one by one, you can use *destructing* assignment in JS.

```
const student = {
  ID: '21',
  name: 'Jhon',
  GPA: '3.0',
};

const id = student.ID;
const name = student.name;
const GPA = student.GPA;

console.log(id);
console.log(name);
console.log(GPA);
```

A simplier version of this is:

```
const student = {
    ID: '21',
    name: "Jhon",
    GPA: '3.0',
};
const {ID, name, GPA} = student;
```

List the properties you want inside the curly brackets and even rename them using aliases:

```
const student = {
    ID: '21',
    name: 'John',
    GPA: '3.0',
};
const {name:n} = student; //Aliases
console.log(n)
```

Another example of destructing:

```
//no destructing
const users = this.state.users;
const counter = this.state.counter;

// destructing
const {users, counter} = this.state
```



