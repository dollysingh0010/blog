Q-What is closures?
Def:-closures are just a normal functions with preserved value.When we are creating any closure,JavaScript will maintain state of that variable inside closure function after a call.
Example--

 function increament() {  --->outer function
  var x=0;
  return function add() {  --->inner function
    x++;
    return x;
  }

}

As you can see on the above example,there are two functions one inside other.increamnet() is the outer function and() add is the inner function.
As per javaScript functionality inner function add() can use varible x of outer function increament().

var test=increament();

test()
output = 1
test()
output = 2
test()
output = 3

Here value of x is bind with add function.after the first call value of x become 1 .But when we are calling it again its not taking value of x as 0 
but its preserve old state of variable.The variable x is private because external functions cannot access this variable.

Q- What is Hoisting?
At the time of execution all the declared part(function, class and variable) hoisted  on the top of program.JavaScript only hoist declarations, not initializations (assignments).
For var it will hoist with undefined value but let and const declarations remain uninitialized.

How internally its worked -
At the compile time it will check all the declaration for function and variable and add it to to the memory inside a JavaScript data structure called
Lexical Environment(place in memory where all the function and variable remain throught program excution). 

Example -

a= 10;
console.log(a);
var a;
output-10

During compile time it will store declaration part for variable a in Lexical Env .
So,at the time of execution it will return 10 without giving any error.

console.log(a);
var a=10;
output-undefined
Output is undefined because at the compile time a is store in Lexical Env with initializaed with undefined.


console.log(a);
let a=10;
output-a is not defined
On the above example Output is a is not defined because at the compile time a is store in Lexical Env with uninitializaed value.

Let and var are also get hoisted but here the issue is They will only get initialized once assignment is evaluated during runtime.
It means to access this variable an’t access the variable before the engine evaluates its value at the place it was declared in the source code. 






