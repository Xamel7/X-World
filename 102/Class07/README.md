## Programming with JavaScript

# Control Flow

>The control flow is the order in which the computer executes statements in a script.

>Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops.

>A typical script in JavaScript or PHP (and the like) includes many control structures, including conditionals, loops and functions. Parts of a script may also be set to execute when events occur.

>Control flow means that when you read a script, you must not only read from start to finish but also look at program structure and how it affects order of execution.

# JavaScript Functions

>A JavaScript function is a block of code designed to perform a particular task.

>A JavaScript function is executed when "something" invokes it (calls it).

# JavaScript Function Syntax

>A JavaScript function is defined with the function keyword, followed by a name, followed by parentheses ().

>Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

>The parentheses may include parameter names separated by commas:
(parameter1, parameter2, ...)

>The code to be executed, by the function, is placed inside curly brackets: {}

>Function parameters are listed inside the parentheses () in the function definition.

>Function arguments are the values received by the function when it is invoked.

>Inside the function, the arguments (the parameters) behave as local variables.

# Function Invocation

>The code inside the function will execute when "something" invokes (calls) the function:

>When an event occurs (when a user clicks a button)

>When it is invoked (called) from JavaScript code

>Automatically (self invoked)

# Function Return

>When JavaScript reaches a return statement, the function will stop executing.

>If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.

>Functions often compute a return value. The return value is "returned" back to the "caller"

# Why Functions?

>You can reuse code: Define the code once, and use it many times.

>You can use the same code many times with different arguments, to produce different results.

# The () Operator Invokes the Function

>Using the example above, toCelsius refers to the function object, and toCelsius() refers to the function result.

>Accessing a function without () will return the function object instead of the function result.

# Functions Used as Variable Values

>Functions can be used the same way as you use variables, in all types of formulas, assignments, and calculations.

# Local Variables

>Variables declared within a JavaScript function, become LOCAL to the function.

>Local variables can only be accessed from within the function.

>Since local variables are only recognized inside their functions, variables with the same name can be used in different functions.

>Local variables are created when a function starts, and deleted when the function is completed.

## JavaScript Operators

>The Assignment Operator (=) assigns a value to a variable.

Assignment Examples:
// Assign the value 5 to x
let x = 5;
// Assign the value 2 to y
let y = 2;
// Assign the value x + y to z:
let z = x + y;

>The Addition Operator (+) adds numbers:
let x = 5;
let y = 2;
let z = x + y;

The Multiplication Operator (*) multiplies numbers.
let x = 5;
let y = 2;
let z = x * y;

# Types of JavaScript Operators

>There are different types of JavaScript operators:

Arithmetic Operators
Assignment Operators
Comparison Operators
Logical Operators
Conditional Operators
Type Operators

# JavaScript Arithmetic Operators
Arithmetic Operators are used to perform arithmetic on numbers:
let a = 3;
let x = (100 + 50) * a;

Operator	Description
+	Addition
-	Subtraction
*	Multiplication
**	Exponentiation (ES2016)
/	Division
%	Modulus (Division Remainder)
++	Increment
--	Decrement

# JavaScript Assignment Operators

>Assignment operators assign values to JavaScript variables.

>The Addition Assignment Operator (+=) adds a value to a variable.
let x = 10;
x += 5;

# Adding JavaScript Strings

>The + operator can also be used to add (concatenate) strings.
let text1 = "John";
let text2 = "Doe";
let text3 = text1 + " " + text2;

The += assignment operator can also be used to add (concatenate) strings:
let text1 = "What a very ";
text1 += "nice day";

# Adding Strings and Numbers

>Adding two numbers, will return the sum, but adding a number and a string will return a string:
let x = 5 + 5;
let y = "5" + 5;
let z = "Hello" + 5;

# JavaScript Comparison Operators

Operator	Description
==	equal to
===	equal value and equal type
!=	not equal
!==	not equal value or not equal type
>	greater than
<	less than
>=	greater than or equal to
<=	less than or equal to
?	ternary operator

# JavaScript Logical Operators

Operator	Description
&&	logical and
||	logical or
!	logical not

# JavaScript Type Operators

Operator	Description
typeof	Returns the type of a variable
instanceof	Returns true if an object is an instance of an object type

# JavaScript Bitwise Operators

>Bit operators work on 32 bits numbers.

>Any numeric operand in the operation is converted into a 32 bit number. The result is converted back to a JavaScript number.

Operator	Description	Example	Same as	Result	Decimal
&	AND	5 & 1	0101 & 0001	0001	 1
|	OR	5 | 1	0101 | 0001	0101	 5
~	NOT	~ 5	 ~0101	1010	 10
^	XOR	5 ^ 1	0101 ^ 0001	0100	 4
<<	left shift	5 << 1	0101 << 1	1010	 10
>>	right shift	5 >> 1	0101 >> 1	0010	  2
>>>	unsigned right shift	5 >>> 1	0101 >>> 1	0010	  2










