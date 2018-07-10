---
layout: post
title:      "JavaScript Refresher: ES6 Concepts"
date:       2018-07-10 14:20:10 +0000
permalink:  javascript_refresher_es6_concepts
---


In this post, I'll refresh some of the key concepts introduced in ES6, particularly as they relate to scope and hoisting.

**Variable Declarations**

Prior to 2015 variable declarations were generally handled by the *var* keyword. With the arrival of ES6, JavaScript developers now have the option to declare variables with either *const* or *let*. These have rendered *var* mostly undesirable. 

Both *const* and *let* differ from var in that they can each only allow a variable to be declared once within a given scope. Beyond that, declaring a variable with *const* ensures that that its value can never be reassigned. On the contrary, *let* allows for variable reassignment. It's best practice to always declare variables with *const* unless that variable's value must change during execution.

**Scope**

Let's briefly recall how the location of a variable's declaration determines the execution context in which it will be available. In the following example, I declare *name* in the global scope, then call it within the *writesName* function. The code executes without error.

```
const name = "Brendan"

function writesName () {
	console.log(name)
}

writesName()   // outputs "Brendan" to the console
```

Let's consider another example. Below, I declare *name* within the scope of function *definesName*, then attempt to reference it in the global scope. This causes a ReferenceError because *name* is only available within *defineName*'s execution context.

```
function definesName () {
	const name = "Brendan"
}

console.log(name) // ReferenceError: name is not defined
```

It's important to remember how execution context depends on the variable declaration keyword. Considering the second example in this section: if I had declared *name* without a keyword, then *name* would have globally scoped. Because I declared it in with *const*, however, it was scoped to the function *definesName*.  Declaring with *var* or *let* would have had the same result. 

Finally, ES6 introduced block scoping - variables declared in a block with *const* or *let* are only available within that block. The same does not apply for *var*:

```
if (true) {
  var foo = "bar" // defined in block, but will be available in the global scope
}

console.log(foo) // outputs "bar" to the console
```


**Variable Hoisting**

Another reason to use *const* and *let* relates to the concept of hoisting. Consider the following code:

```
console.log(foo) // outputs undefined
var foo = "bar"
```

In this example, the JS compiler initializes the variable *foo* before execution, but does not store its value. Thus when the code is actually executed, *foo* exists in memory and the console.log statement does not throw a reference error. But because *foo* has yet to be assigned a value, the statement outputs 'undefined'.

If *foo* had been declared with *const* or *let*, console.log(foo) would have thrown a ReferenceError. *const* and *let* do not allow variables to be evaluated if they have been declared but not assigned a value.

**Function Hoisting**

A function declaration is hoisted, which allows it to be defined below its actual invocation:
```
sayGoodbye() // Outputs "Goodbye"

function sayGoodbye () {
  console.log("Goodbye")
}
```
The same does not apply when a function expression is assigned to a variable. In the below example, a function expression is assigned to the variable *sayGoodbye*. Because *sayGoodbye* is declare with *const*, it is not hoisted and the code fails to execute.

```
sayGoodbye() // ReferenceError: sayGoodbye is not defined

const sayGoodbye = function () {
  console.log("Goodbye")
}
```

To keep things simple, it's a good idea to declare functions before they are invoked.

**Arrow Functions**

Arrow functions are another important new feature in ES6. Compared to regular named functions, they can offer a more elegant and efficient syntax for several reasons.

1. They eschew the *function* keyword in favor of a *() => {}* declaration.

2. A single line arrow function does not require the use of the *return* keyword if it is declared without brackets.
```
1	const subtractOne = (number) => (number - 1)  // define arrow function without brackets
2	
3	console.log(subtractOne(10)) // outputs "9"
```
3. Arrow functions preserve the context of the outer scope in which they are declared. This feature can obviate the need for a .bind(this) statement that a regular function would require. Let's take a look at an example.
  ```
1	const tomatoes = {
2	  plum: 2,
3	  heirloom: 1,
4	  roma: 4,
5	  displayTotal: function () {
6	    return () => {
7	    console.log(this) // Output: { plum: 2, heirloom: 1, roma: 4, displayTotal: [Function] }
8	    return `There are ${this.plum + this.heirloom + this.roma} total tomatoes`
9	  }
10	  }
11	}
12	
13	console.log(tomatoes.displayTotal()()) // Output: There are 7 total tomatoes
```
On line 6, I return an arrow function expression nested within the function assigned to *displayTotal*. As the output from line 7 demonstrates, the arrow function's  *this* value is bound to the object *tomatoes*. If on line 6 I had instead returned a regular function, *this* would have been bound to the function expression which begins on line 5. 


