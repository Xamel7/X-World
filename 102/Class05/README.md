## What is CSS?

>CSS (Cascading Style Sheets) allows you to create great-looking web pages

## What is css for?

>CSS can be used for very basic document text styling — for example, for changing the color and size of headings and links. It can be used to create a layout — for example, turning a single column of text into a layout with a main content area and a sidebar for related information.

## CSS syntax

>CSS is a rule-based language — you define the rules by specifying groups of styles that should be applied to particular elements or groups of elements on your web page.

>CSS properties have different allowable values, depending on which property is being specified.

## CSS modules
# Backgrounds & Borders

## CSS specifications

>All web standards technologies (HTML, CSS, JavaScript, etc.) are defined in giant documents called specifications (or "specs"), which are published by standards organizations (such as the W3C, WHATWG, ECMA, or Khronos) and define precisely how those technologies are supposed to behave.

## External CSS

>With an external style sheet, you can change the look of an entire website by changing just one file!

>Each HTML page must include a reference to the external style sheet file inside the <link> element, inside the head section.

## Internal CSS

>An internal style sheet may be used if one single HTML page has a unique style.

>The internal style is defined inside the <style> element, inside the head section.

## Inline CSS

>An inline style may be used to apply a unique style for a single element.

>To use inline styles, add the style attribute to the relevant element. The style attribute can contain any CSS property.

## Basic selectors

>Universal selector
Selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces.

Syntax: * ns|* *|*

>Type selector
Selects all elements that have the given node name.

Syntax: elementname

>Type selector
Selects all elements that have the given node name.

Syntax: elementname

>ID selector
Selects an element based on the value of its id attribute. There should be only one element with a given ID in a document.

Syntax: #idname

>Attribute selector
Selects all elements that have the given attribute.

Syntax: [attr] [attr=value] [attr~=value] [attr|=value] [attr^=value] [attr$=value] [attr*=value]
 
 ## Grouping selectors

 >Selector list
The , selector is a grouping method that selects all the matching nodes.

Syntax: A, B

## Combinators

>Descendant combinator
The " " (space) combinator selects nodes that are descendants of the first element.

Syntax: A B

>Child combinator
The > combinator selects nodes that are direct children of the first element.

Syntax: A > B

>General sibling combinator
The ~ combinator selects siblings. This means that the second element follows the first (though not necessarily immediately), and both share the same parent.

Syntax: A ~ B

>Adjacent sibling combinator
The + combinator matches the second element only if it immediately follows the first element.

Syntax: A + B

>Column combinator Experimental
The || combinator selects nodes which belong to a column.

Syntax: A || B

## Pseudo-classes and pseudo-elements

>Pseudo classes
The : pseudo allow the selection of elements based on state information that is not contained in the document tree.

>Pseudo elements
The :: pseudo represent entities that are not included in HTML.

## Structure of a selector

>Simple selector
A selector with a single component, such as a single id selector or type selector, that's not used in combination with or contains any other selector component or combinator.All basic selectors, attributes, and single pseudo-classes and pseudo-elements are simple selectors.

>Compound selector
A sequence of simple selectors that are not separated by a combinator. A compound selector represents a set of simultaneous conditions on a single element.
In a compound selector, the type selector or a universal selector in a compound selector must come first in the sequence of selectors. Only one type selector or universal selector is allowed in the sequence. Since whitespace represents the descendant combinator, no whitespace is allowed between the simple selectors in a compound selector.

>Complex selector
A sequence of one or more simple and/or compound selectors that are separated by combinators. A complex selector represents a set of simultaneous conditions on a set of elements. These conditions apply in the context of relationships described by the combinators.

>Relative selector
A selector representing an element relative to one or more anchor elements preceded by a combinator. 

>Selector list
A comma-separated list of simple, compound, or complex selectors. If the constituent selector type of a selector list is important but unspecified, it is called a complex selector list.



