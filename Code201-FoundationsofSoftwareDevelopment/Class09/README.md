## HTML Forms & Learning JS

# Why are forms so important in web development?

# Forms are one of the main ways to transfer data of the users to the website.Data is checked and stored at the severs.It gives the consumer direct use to change the settings at the beginning of the page.

# When designing a form, what are some key things to keep in mind when it comes to user experience?

# Accessability is essential for assuring the form interacts parallel with the screen readers and make sure it visually usable for users as well. Don't complicate the form; use only the necessary functions. Only ask the user for info that you definitely need.

# List 5 form elements and explain their importance.

# <input>  the default type is text but can also be used to add more interactivity by accepting passwords and emails. <textarea> used for long lines of texts like messages and notes. <fieldset> encapsulates related inputs in your form and gives them a label with <legend> <label> labels your input with text and also groups together with your inputs when read with a screen reader. <select> creates a drops with different <option>s allows users to select one option from many choices.

# How would you describe events to a non-technical friend?

# Events are like RSVP'ing. When something is going on that you want to attend; you acquire info. It's gives you the where, when, and how long the event will last. Your page does the same thing whenever you click, hover, or button over a(n) item. The page gets the RSVP and decides whether or not to take action and what action to take.

# When using the addEventListener() method, what 2 arguments will you need to provide?

# The first argument needs to be the string click to indicate that we want to listen to the click event. The second arguemnt is the function to call when the event happens.

# Describe the event object. Why is the target within the event object useful?

# Events are things that happen in the system you are programming — the system produces (or "fires") a signal of some kind when an event occurs, and provides a mechanism by which an action can be automatically taken (that is, some code running) when the event occurs. Events are fired inside the browser window, and tend to be attached to a specific item that resides in it. 

# The user selects, clicks, or hovers the cursor over a certain element.
# The user chooses a key on the keyboard.
# The user resizes or closes the browser window.
# A web page finishes loading.
# A form is submitted.
# A video is played, paused, or ends.
# An error occurs.

# What is the difference between event bubbling and event capturing?

# An alternative form of event propagation is event capture. This is like event bubbling but the order is reversed: so instead of the event firing first on the innermost element targeted, and then on successively less nested elements, the event fires first on the least nested element, and then on successively more nested elements, until the target is reached.Event bubbling describes how the browser handles events targeted at nested elements.