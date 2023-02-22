## Semantics

# Why is it important to use semantic elements in our HTML?

In programming, Semantics refers to the meaning of a piece of code — for example "what effect does running that line of JavaScript have?", or "what purpose or role does that HTML element have" (rather than "what does it look like?".)

# Semantics in HTML

In HTML, for example, the <h1> element is a semantic element, which gives the text it wraps around the role (or meaning) of "a top level heading on your page."

HTML should be coded to represent the data that will be populated and not based on its default presentation styling. Presentation (how it should look), is the sole responsibility of CSS.

Some of the benefits from writing semantic markup are as follows:

Search engines will consider its contents as important keywords to influence the page's search rankings (see SEO)

Screen readers can use it as a signpost to help visually impaired users navigate a page

Finding blocks of meaningful code is significantly easier than searching through endless divs with or without semantic or namespaced classes

Suggests to the developer the type of data that will be populated

Semantic naming mirrors proper custom element/component naming

# How many levels of headings are there in HTML?

There are six heading elements: <h1>h1</h1>, <h2>h2</h2>, <h3>h3</h3>, <h4>h4</h4>, <h5>h5</h5>, and <h6>h6</h6>. Each element represents a different level of content in the document; <h1> represents the main heading, <h2> represents subheadings, <h3> represents sub-subheadings, and so on.

# What are some uses for the <sup> and <sub> elements?

Superscript and subscript
You will occasionally need to use superscript and subscript when marking up items like dates, chemical formulae, and mathematical equations so they have the correct meaning. The <sup> and <sub> elements handle this job. For example:

<p>My birthday is on the 25<sup>th</sup> of May 2001.</p>
<p>
  Caffeine's chemical formula is
  C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>.
</p>
<p>If x<sup>2</sup> is 9, x must equal 3 or -3.</p>

# When using the <abbr> element, what attribute must be added to provide the full expansion of the term?

Another fairly common element you'll meet when looking around the Web is <abbr> — this is used to wrap around an abbreviation or acronym. When including either, provide a full expansion of the term in plain text on first use, along with the <abbr> to mark up the abbreviation. This provides a hint to user agents on how to announce/display the content while informing all users what the abbreviation means.

If providing the expansion in addition to the abbreviation makes little sense, and the abbreviation or acronym is a fairly shortened term, provide the full expansion of the term as the value of title attribute.

# What are ways we can apply CSS to our HTML?

>External stylesheet

An external stylesheet contains CSS in a separate file with a .css extension. This is the most common and useful method of bringing CSS to a document. You can link a single CSS file to multiple web pages, styling all of them with the same CSS stylesheet.

<!DOCTYPE html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8" />
    <title>My CSS experiment</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>

h1 {
  color: blue;
  background-color: yellow;
  border: 1px solid black;
}

p {
  color: red;
}

>Internal stylesheet

An internal stylesheet resides within an HTML document. To create an internal stylesheet, you place CSS inside a <style> element contained inside the HTML <head>.

<!DOCTYPE html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8" />
    <title>My CSS experiment</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>

Inline styles

Inline styles are CSS declarations that affect a single HTML element, contained within a style attribute. The implementation of an inline style in an HTML document might look like this:

<!DOCTYPE html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8" />
    <title>My CSS experiment</title>
  </head>
  <body>
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">
      Hello World!
    </h1>
    <p style="color:red;">This is my first CSS example</p>
  </body>
</html>

# Why should we avoid using inline styles?

Avoid using CSS in this way, when possible. It is the opposite of a best practice. First, it is the least efficient implementation of CSS for maintenance. One styling change might require multiple edits within a single web page. Second, inline CSS also mixes (CSS) presentational code with HTML and content, making everything more difficult to read and understand. Separating code and content makes maintenance easier for all who work on the website.

It's representing a type selector.

"color: black" and "padding: 5px" are the two declarations. 

"color" and "padding" are the properties.

String	

This is a sequence of text known as a string. To signify that the value is a string, enclose it in single or double quote marks.	

let myVariable = 'Bob'; or
let myVariable = "Bob";

Arithmetic operators

Arithmetic operators take numerical values (either literals or variables) as their operands and return a single numerical value.

Relational operators

A comparison operator compares its operands and returns a boolean value based on whether the comparison is true.

Binary logical operators

Logical operators implement boolean (logical) values and have short-circuiting behavior.

Assignment operators

An assignment operator assigns a value to its left operand based on the value of its right operand.

function convertTemperature(temp, scale) {
  if (scale === "C") {
    // convert Celsius to Fahrenheit
    return (temp * 9/5) + 32;
  } else if (scale === "F") {
    // convert Fahrenheit to Celsius
    return (temp - 32) * 5/9;
  } else {
    // invalid scale
    return "Invalid scale. Please enter 'C' or 'F'.";
  }
}

An if statement checks a condition and if it evaluates to true, then the code block will execute.

There is a way to chain on extra choices/outcomes to your if...else — using else if. Each extra choice requires an additional block to put in between if () { } and else { }

=== and !== — test if one value is identical to, or not identical to, another.
< and > — test if one value is less than or greater than another.
<= and >= — test if one value is less than or equal to, or greater than or equal to, another.

&& — AND; allows you to chain together two or more expressions so that all of them have to individually evaluate to true for the whole expression to return true.
|| — OR; allows you to chain together two or more expressions so that one or more of them have to individually evaluate to true for the whole expression to return true.
