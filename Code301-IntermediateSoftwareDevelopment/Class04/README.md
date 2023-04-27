## React and Forms

# React Docs - Forms

# What is a ‘Controlled Component’?
A controlled component in react is a form element that gets it's value from a parent and returns it using a callback function to update the parents' state whenever the component changes.

# Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
It's best to update the the state as soon they enter their feedback.React makes this process so much smoother by providing realtime feedback.

# How do we target what the user is entering if we have an event handler on an input field?
We target them with the event.target.value method to access the value in the element that the user has just stored.

# Why would we use a ternary operator?
To store the value of an expression in a variable or to succinct your code.

# Rewrite the following statement using a ternary statement:
if(x===y){
  console.log(true);
} else {
  console.log(false);
}

console.log( x===y ? true : false )