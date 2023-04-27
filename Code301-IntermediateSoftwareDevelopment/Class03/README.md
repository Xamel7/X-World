## Passing Functions as Props

## React Docs - lists and keys

# What does .map() return?
It returns a new array where each item is the value returned from the callback function.

# If I want to loop through an array and display each value in JSX, how do I do that in React?
You can do that with the .map() function. It allows to iterate though the an array of data and transform each item into a react component

# Each list item needs a unique ____.
Key to determine which needs to be added,removed, or modified.

# What is the purpose of a key?
It to provide a unique id for each element in a list of elements regardless of the order of the list.

## The Spread Operator

# What is the spread operator?
It's a useful and syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function's arguments.It allows you to break down an array into it's individual elements.

# List 4 things that the spread operator can do.
Concatenating or combining arrays,copying an array,combining objects, and converting arrays like lists into arrays.

# Give an example of using the spread operator to combine two arrays.
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combinedArr = [...arr1, ...arr2];

console.log(combinedArr); // Output: [1, 2, 3, 4, 5, 6]

# Give an example of using the spread operator to add a new item to an array.
const arr1 = [1, 2, 3];
const newItem = 4;
const newArr = [...arr1, newItem];

console.log(newArr); // Output: [1, 2, 3, 4]

# Give an example of using the spread operator to combine two objects into one.
const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };
const newObj = { ...obj1, ...obj2 };

console.log(newObj); // Output: { a: 1, b: 2, c: 3, d: 4 }

## How to Pass Functions Between Components

# In the video, what is the first step that the developer does to pass functions between components?
He created a function in the "parent" element that will control the state.

# In your own words, what does the increment function do? 
It mapped through the array of the people objects in the state and increments the count on the person object with that was passed into function.

# How can you pass a method from a parent component into a child component?
By using the the props element from the parent.

# How does the child component invoke a method that was passed to it from a parent component?
You call the method that is being passed through as a prop.