# Javascript

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



