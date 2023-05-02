## Putting it all together

# What is the single responsibility principle and how does it apply to components?
The principle states that a piece of code should only do one thing. If the object or function grows past this it should be broken down into smaller pieces.

# What does it mean to build a ‘static’ version of your application?
'Static' is a rough draft of your application that uses your data to draw the components but has no use for state to make it interactive.

# Once you have a static application, what do you need to add?
You'll need the interactivity from the state and add some event listeners to your application.

# What are the three questions you can ask to determine if something is state?
Does it remain unchanged over time? If so, it isn’t state.
Is it passed in from a parent via props? If so, it isn’t state.
Can you compute it based on existing state or props in your component? If so, it definitely isn’t state!

# How can you identify where state needs to live?
Identify every component that renders something based on that state.
Find their closest common parent component—a component above them all in the hierarchy.Decide where the state should live.
What is a “higher-order function”?

## Higher-Order Functions

# What is a “higher-order function”?
Functions that operate on other functions, either by taking them as arguments or by returning them.

# Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?
Returns a(n) arrow function that takes in an argument of n and returns the result of n > m where n is the argument passed into the outermost function.

# Explain how either map or reduce operates, with regards to higher-order functions.
Map() returns a new array by using a callback function from the original array of elements.Whatever your arguments that are passed through the perimeters will be the return value of the corresponding elements in the new array.