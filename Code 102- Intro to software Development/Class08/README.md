## Expressions and Operators

>This chapter describes JavaScript's expressions and operators, including assignment,comparison,arithmetic,bitwise,logical,string,ternary & more.

>At a high level, an expression is a valid unit of code that resolves to a value. There are two types of expressions: those that have side effects (such as assigning values) and those that purely evaluate.

>The expression x = 7 is an example of the first type. This expression uses the = operator to assign the value seven to the variable x. The expression itself evaluates to 7.

>Despite * and + coming in different orders, both expressions would result in 7 because * has precedence over +, so the *-joined expression will always be evaluated first. You can override operator precedence by using parentheses (which creates a grouped expression — the basic expression).

>JavaScript has both binary and unary operators, and one special ternary operator, the conditional operator. A binary operator requires two operands, one before the operator and one after the operator:

operand1 operator operand2

>his form is called an infix binary operator, because the operator is placed between two operands. All binary operators in JavaScript are infix.

>A unary operator requires a single operand, either before or after the operator:

operator operand
operand operator

## Assignment Operators

>An assignment operator assigns a value to its left operand based on the value of its right operand. The simple assignment operator is equal (=), which assigns the value of its right operand to its left operand.

# Assigning to properties

>If an expression evaluates to an object, then the left-hand side of an assignment expression may make assignments to properties of that expression. 

>In strict mode, the code above throws, because one cannot assign properties to primitives.

>It is an error to assign values to unmodifiable properties or to properties of an expression without properties (null or undefined).

# Destructuring

>For more complex assignments, the destructuring assignment syntax is a JavaScript expression that makes it possible to extract data from arrays or objects using a syntax that mirrors the construction of array and object literals.

>Chaining assignments or nesting assignments in other expressions can result in surprising behavior.

>Nevertheless, assignment chaining and nesting may occur sometimes, so it is important to be able to understand how they work.

>The evaluation result matches the expression to the right of the = sign in the "Meaning" column of the table above. That means that x = f() evaluates into whatever f()'s result is, x += f() evaluates into the resulting sum x + f(), x **= f() evaluates into the resulting power x ** y, and so on.

>In the case of logical assignments, x &&= f(), x ||= f(), and x ??= f(), the return value is that of the logical operation without the assignment, so x && f(), x || f(), and x ?? f(), respectively.

>When chaining these expressions without parentheses or other grouping operators like array literals, the assignment expressions are grouped right to left (they are right-associative), but they are evaluated left to right.

# Evaluation Example 1

>y = x = f() is equivalent to y = (x = f()), because the assignment operator = is right-associative. 

>However, it evaluates from left to right:

>The assignment expression y = x = f() starts to evaluate.

>The y on this assignment's left-hand side evaluates into a reference to the variable named y.

>The assignment expression x = f() starts to evaluate.

>The x on this assignment's left-hand side evaluates into a reference to the variable named x.

>The function call f() prints "F!" to the console and then evaluates to the number 2.

>That 2 result from f() is assigned to x.

>The assignment expression x = f() has now finished evaluating; its result is the new value of x, which is 2.

>That 2 result in turn is also assigned to y.

>The assignment expression y = x = f() has now finished evaluating; its result is the new value of y – which happens to be 2. x and y are assigned to 2, and the console has printed "F!".

# Example 2

>y = [ f(), x = g() ] also evaluates from left to right:

>The assignment expression y = [ f(), x = g() ] starts to evaluate.

>The y on this assignment's left-hand evaluates into a reference to the variable named y.

>The inner array literal [ f(), x = g() ] starts to evaluate.

>The function call f() prints "F!" to the console and then evaluates to the number 2.

>The assignment expression x = g() starts to evaluate.

>The x on this assignment's left-hand side evaluates into a reference to the variable named x.

>The function call g() prints "G!" to the console and then evaluates to the number 3.

>That 3 result from g() is assigned to x.

>The assignment expression x = g() has now finished evaluating; its result is the new value of x, which is 3. That 3 result becomes the next element in the inner array literal (after the 2 from the f()).

>The inner array literal [ f(), x = g() ] has now finished evaluating; its result is an array with two values: [ 2, 3 ].

>That [ 2, 3 ] array is now assigned to y.

>The assignment expression y = [ f(), x = g() ] has now finished evaluating; its result is the new value of y – which happens to be [ 2, 3 ]. x is now assigned to 3, y is now assigned to [ 2, 3 ], and the console has printed "F!" then "G!".

# Example 3

>x[f()] = g() also evaluates from left to right. (This example assumes that x is already assigned to some object. For more information about objects, read Working with Objects.)

>The assignment expression x[f()] = g() starts to evaluate.

>The x[f()] property access on this assignment's left-hand starts to evaluate.

>The x in this property access evaluates into a reference to the variable named x.

>Then the function call f() prints "F!" to the console and then evaluates to the number 2.

>The x[f()] property access on this assignment has now finished evaluating; its result is a variable property reference: x[2].

>Then the function call g() prints "G!" to the console and then evaluates to the number 3.

>That 3 is now assigned to x[2]. (This step will succeed only if x is assigned to an object.)

>The assignment expression x[f()] = g() has now finished evaluating; its result is the new value of x[2] – which happens to be 3. x[2] is now assigned to 3, and the console has printed "F!" then "G!".

# Avoid Assignment Chains

>In particular, putting a variable chain in a const, let, or var statement often does not work. Only the outermost/leftmost variable would get declared; other variables within the assignment chain are not declared by the const/let/var statement.

# Comparison Operators

>A comparison operator compares its operands and returns a logical value based on whether the comparison is true. The operands can be numerical, string, logical, or object values. Strings are compared based on standard lexicographical ordering, using Unicode values. In most cases, if the two operands are not of the same type, JavaScript attempts to convert them to an appropriate type for the comparison.

>This behavior generally results in comparing the operands numerically. The sole exceptions to type conversion within comparisons involve the === and !== operators, which perform strict equality and inequality comparisons. These operators do not attempt to convert the operands to compatible types before checking equality.

# Examples Operators

>Equal (==)-Returns true if the operands are equal.	3 == var1
"3" == var1

3 == '3'

>Not equal (!=)-Returns true if the operands are not equal.	var1 != 4
var2 != "3"

>Strict equal (===)-Returns true if the operands are equal and of the same type. See also Object.is and sameness in JS.	3 === var1

>Strict not equal (!==)-Returns true if the operands are of the same type but not equal, or are of different type.	var1 !== "3"
3 !== '3'

>Greater than (>)-Returns true if the left operand is greater than the right operand.	var2 > var1
"12" > 2

>Greater than or equal (>=)-Returns true if the left operand is greater than or equal to the right operand.	var2 >= var1
var1 >= 3

>Less than (<)-Returns true if the left operand is less than the right operand.	var1 < var2
"2" < 12

>Less than or equal (<=)-	Returns true if the left operand is less than or equal to the right operand.	var1 <= var2
var2 <= 5

# Arithmetic Operators

>An arithmetic operator takes numerical values (either literals or variables) as their operands and returns a single numerical value. The standard arithmetic operators are addition (+), subtraction (-), multiplication (*), and division (/).

>These operators work as they do in most other programming languages when used with floating point numbers (in particular, note that division by zero produces Infinity).

>Remainder (%)	Binary operator. Returns the integer remainder of dividing the two operands.	12 % 5 returns 2.

>Increment (++)	Unary operator. Adds one to its operand. If used as a prefix operator (++x), returns the value of its operand after adding one; if used as a postfix operator (x++), returns the value of its operand before adding one.	If x is 3, then ++x sets x to 4 and returns 4, whereas x++ returns 3 and, only then, sets x to 4.

>Decrement (--)	Unary operator. Subtracts one from its operand. The return value is analogous to that for the increment operator.	If x is 3, then --x sets x to 2 and returns 2, whereas x-- returns 3 and, only then, sets x to 2.

>Unary negation (-)	Unary operator. Returns the negation of its operand.	If x is 3, then -x returns -3.

>Unary plus (+)	Unary operator. Attempts to convert the operand to a number, if it is not already.	
+"3" returns 3.

+true returns 1.

>Exponentiation operator (**)	Calculates the base to the exponent power, that is, base^exponent	2 ** 3 returns 8.
10 ** -1 returns 0.1.

# Bitwise Operators

>A bitwise operator treats their operands as a set of 32 bits (zeros and ones), rather than as decimal, hexadecimal, or octal numbers.

>Bitwise operators perform their operations on such binary representations, but they return standard JavaScript numerical values.

>Bitwise AND	a & b	Returns a one in each bit position for which the corresponding bits of both operands are ones.

>Bitwise OR	a | b	Returns a zero in each bit position for which the corresponding bits of both operands are zeros.

>Bitwise XOR	a ^ b	Returns a zero in each bit position for which the corresponding bits are the same. [Returns a one in each bit position for which the corresponding bits are different.]

>Bitwise NOT	~ a	Inverts the bits of its operand.

>Left shift	a << b	Shifts a in binary representation b bits to the left, shifting in zeros from the right.

>Sign-propagating right shift-	a >> b	-Shifts a in binary representation b bits to the right, discarding bits shifted off.

>Zero-fill right shift-	a >>> b	-Shifts a in binary representation b bits to the right, discarding bits shifted off, and shifting in zeros from the left.

# Bitwise logical operators

>Conceptually, the bitwise logical operators work as follows:

>The operands are converted to thirty-two-bit integers and expressed by a series of bits (zeros and ones). Numbers with more than 32 bits get their most significant bits discarded.

>Each bit in the first operand is paired with the corresponding bit in the second operand: first bit to first bit, second bit to second bit, and so on.

>The operator is applied to each pair of bits, and the result is constructed bitwise.

>Note that all 32 bits are inverted using the Bitwise NOT operator, and that values with the most significant (left-most) bit set to 1 represent negative numbers (two's-complement representation). ~x evaluates to the same value that -x - 1 evaluates to.

# Bitwise shift operators

>The bitwise shift operators take two operands: the first is a quantity to be shifted, and the second specifies the number of bit positions by which the first operand is to be shifted. The direction of the shift operation is controlled by the operator used.

>Shift operators convert their operands to thirty-two-bit integers and return a result of either type Number or BigInt: specifically, if the type of the left operand is BigInt, they return BigInt; otherwise, they return Number.

>Left shift(<<)-This operator shifts the first operand the specified number of bits to the left. Excess bits shifted off to the left are discarded. Zero bits are shifted in from the right.	9<<2 yields 36, because 1001 shifted 2 bits to the left becomes 100100, which is 36.

>Sign-propagating right shift (>>)-This operator shifts the first operand the specified number of bits to the right. Excess bits shifted off to the right are discarded. Copies of the leftmost bit are shifted in from the left.	9>>2 yields 2, because 1001 shifted 2 bits to the right becomes 10, which is 2. Likewise, -9>>2 yields -3, because the sign is preserved.

>Zero-fill right shift (>>>)-This operator shifts the first operand the specified number of bits to the right. Excess bits shifted off to the right are discarded. Zero bits are shifted in from the left.	-19>>>2 yields 4, because 10011 shifted 2 bits to the right becomes 100, which is 4. For non-negative numbers, zero-fill right shift and sign-propagating right shift yield the same result.

# Logical operators

>Logical operators are typically used with Boolean (logical) values; when they are, they return a Boolean value. However, the && and || operators actually return the value of one of the specified operands, so if these operators are used with non-Boolean values, they may return a non-Boolean value. 


>Logical AND (&&)	expr1 && expr2	Returns expr1 if it can be converted to false; otherwise, returns expr2. Thus, when used with Boolean values, && returns true if both operands are true; otherwise, returns false.

>Logical OR (||)	expr1 || expr2	Returns expr1 if it can be converted to true; otherwise, returns expr2. 

>Thus, when used with Boolean values, || returns true if either operand is true; if both are false, returns false.

>Logical NOT (!)	!expr	Returns false if its single operand that can be converted to true; otherwise, returns true.

# Short-circuit evaluation

>As logical expressions are evaluated left to right, they are tested for possible "short-circuit" evaluation using the following rules:

>false && anything is short-circuit evaluated to false.
>true || anything is short-circuit evaluated to true.

>Note that for the second case, in modern code you can use the Nullish coalescing operator (??) that works like ||, but it only returns the second expression, when the first one is "nullish", i.e. null or undefined. It is thus the better alternative to provide defaults, when values like '' or 0 are valid values for the first expression, too.

# BigInt Operatirs

>Most operators that can be used between numbers can be used between BigInt values as well.

>One exception is unsigned right shift (>>>), which is not defined for BigInt values. This is because a BigInt does not have a fixed width, so technically it does not have a "highest bit".

>BigInts have higher precision than numbers when representing large integers, but cannot represent decimals, so implicit conversion on either side might lose precision.

# String operators

>In addition to the comparison operators, which can be used on string values, the concatenation operator (+) concatenates two string values together, returning another string that is the union of the two operand strings.

# Conditional (ternary) operator

>The conditional operator is the only JavaScript operator that takes three operands. The operator can have one of two values based on a condition. 

# Comma operator

>The comma operator (,) evaluates both of its operands and returns the value of the last operand. This operator is primarily used inside a for loop, to allow multiple variables to be updated each time through the loop. It is regarded bad style to use it elsewhere, when it is not necessary. Often two separate statements can and should be used instead.

# Unary operators

>A unary operation is an operation with only one operand.

# delete

>The delete operator deletes an object's property. The syntax is:

delete object.property;
delete object[propertyKey];
delete objectName[index];

>Where object is the name of an object, property is an existing property, and propertyKey is a string or symbol referring to an existing property.

# Deleting array elements

>Since arrays are just objects, it's technically possible to delete elements from them. This is however regarded as a bad practice, try to avoid it. When you delete an array property, the array length is not affected and other elements are not re-indexed. To achieve that behavior, it is much better to just overwrite the element with the value undefined. To actually manipulate the array, use the various array methods such as splice.

# typeof

>The typeof operator returns a string indicating the type of the unevaluated operand. operand is the string, variable, keyword, or object for which the type is to be returned. The parentheses are optional.

typeof myFun; // returns "function"
typeof shape; // returns "string"
typeof size; // returns "number"
typeof foo; // returns "object"
typeof today; // returns "object"
typeof doesntExist; // returns "undefined"

# void

>The void operator specifies an expression to be evaluated without returning a value. expression is a JavaScript expression to evaluate. The parentheses surrounding the expression are optional, but it is good style to use them to avoid precedence issues.

# Relational operators

>A relational operator compares its operands and returns a Boolean value based on whether the comparison is true.

# in

>The in operator returns true if the specified property is in the specified object. The syntax is:

propNameOrNumber in objectName

>Where propNameOrNumber is a string, numeric, or symbol expression representing a property name or array index, and objectName is the name of an object.

# instanceof

>The instanceof operator returns true if the specified object is of the specified object type. The syntax is:

objectName instanceof objectType

>Where objectName is the name of the object to compare to objectType, and objectType is an object type, such as Date or Array.

# Basic expressions

>All operators eventually operate on one or more basic expressions. These basic expressions include identifiers and literals, but there are a few other kinds as well. They are briefly introduced below, and their semantics are described in detail in their respective reference sections.

# this

>Use the this keyword to refer to the current object. In general, this refers to the calling object in a method. Use this either with the dot or the bracket notation:

this["propertyName"];
this.propertyName;

>Suppose a function called validate validates an object's value property, given the object and the high and low values:

function validate(obj, lowval, hival) {
  if (obj.value < lowval || obj.value > hival) {
    console.log("Invalid Value!");
  }
}

# Grouping operator

>The grouping operator ( ) controls the precedence of evaluation in expressions. For example, you can override multiplication and division first, then addition and subtraction to evaluate addition first.

const a = 1;
const b = 2;
const c = 3;

// default precedence
a + b * c     // 7
// evaluated by default like this
a + (b * c)   // 7

// now overriding precedence
// addition before multiplication
(a + b) * c   // 9

// which is equivalent to
a * c + b * c // 9

# new

>You can use the new operator to create an instance of a user-defined object type or of one of the built-in object types.

# super

>The super keyword is used to call functions on an object's parent.

## Loops & Iteration

>The various loop mechanisms offer different ways to determine the start and end points of the loop. There are various situations that are more easily served by one type of loop over the others.

# for statement

>A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop.

>When a for loop executes, the following occurs:

>The initializing expression initialization, if any, is executed. This expression usually initializes one or more loop counters, but the syntax allows an expression of any degree of complexity. This expression can also declare variables.

>The condition expression is evaluated. If the value of condition is true, the loop statements execute. Otherwise, the for loop terminates. (If the condition expression is omitted entirely, the condition is assumed to be true.)

>The statement executes. To execute multiple statements, use a block statement ({ }) to group those statements.

>If present, the update expression afterthought is executed.

>Control returns to Step 2.

# JavaScript

>Here, the for statement declares the variable i and initializes it to 0. It checks that i is less than the number of options in the <select> element, performs the succeeding if statement, and increments i by 1 after each pass through the loop.

# do...while statement

>The do...while statement repeats until a specified condition evaluates to false.

A do...while statement looks as follows:

do
  statement
while (condition);

>statement is always executed once before the condition is checked. (To execute multiple statements, use a block statement ({ }) to group those statements.)

>If condition is true, the statement executes again. At the end of every execution, the condition is checked. When the condition is false, execution stops, and control passes to the statement following do...while.

# while statement

>A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:

while (condition)
  statement

>If the condition becomes false, statement within the loop stops executing and control passes to the statement following the loop.

>The condition test occurs before statement in the loop is executed. If the condition returns true, statement is executed and the condition is tested again. If the condition returns false, execution stops, and control is passed to the statement following while.

# labeled statement

>A label provides a statement with an identifier that lets you refer to it elsewhere in your program. For example, you can use a label to identify a loop, and then use the break or continue statements to indicate whether a program should interrupt the loop or continue its execution.

# break statement

>Use the break statement to terminate a loop, switch, or in conjunction with a labeled statement.

>When you use break without a label, it terminates the innermost enclosing while, do-while, for, or switch immediately and transfers control to the following statement.

>When you use break with a label, it terminates the specified labeled statement.

# Example: Breaking to a label 
let x = 0;
let z = 0;
labelCancelLoops: while (true) {
  console.log("Outer loops: ", x);
  x += 1;
  z = 1;
  while (true) {
    console.log("Inner loops: ", z);
    z += 1;
    if (z === 10 && x === 10) {
      break labelCancelLoops;
    } else if (z === 10) {
      break;
    }
  }
}

# continue statement

>The continue statement can be used to restart a while, do-while, for, or label statement.

>When you use continue without a label, it terminates the current iteration of the innermost enclosing while, do-while, or for statement and continues execution of the loop with the next iteration. In contrast to the break statement, continue does not terminate the execution of the loop entirely. In a while loop, it jumps back to the condition. In a for loop, it jumps to the increment-expression.

>When you use continue with a label, it applies to the looping statement identified with that label.
















