## [Class04](/Class04/)

# Wireframe

>Purpose: A wireframe is a basic, low-fidelity representation of a website or application interface, used to illustrate and test its layout, structure and content before moving on to design and development.

>Content: A wireframe should include all the key elements of the interface, such as the header, footer, navigation menu, main content area, and any additional sections. The focus should be on the placement and organization of elements, not the design details.

>Simplicity: Wireframes should be simple, without unnecessary details, graphics, or colors. The purpose is to quickly test and iterate ideas without getting bogged down in design.

>Interactivity: Interactive elements, such as buttons and links, can be represented by simple boxes or shapes. The focus should be on testing the basic functionality of the interface, rather than the specific details of the interactions.

>Usability: Wireframes can be used to test the usability of an interface and ensure that it is easy to use and navigate. They can also help identify potential problems before they become more complicated and costly to fix.

>Collaboration: Wireframes can be a valuable tool for collaboration between designers, developers, stakeholders, and end-users, as they allow everyone to contribute and give feedback on the interface.

>Iteration: Wireframes are not meant to be final products, but rather a starting point for iteration and improvement. They can and should be revised and refined as feedback is received and ideas are developed further.

## HTML Basics

>HTML (HyperText Markup Language) is the code that is used to structure a web page and its content.

# What is HTML?

>HTML is a markup language that defines the structure of your content. HTML consists of a series of elements, which you use to enclose, or wrap, different parts of the content to make it appear a certain way, or act a certain way. The enclosing tags can make a word or image hyperlink to somewhere else, can italicize words, can make the font bigger or smaller, and so on.

# Anatomy of an HTML element

>The opening tag: This consists of the name of the element (in this case, p), wrapped in opening and closing angle brackets. >This states where the element begins or starts to take effect — in this case where the paragraph begins.

>The closing tag: This is the same as the opening tag, except that it includes a forward slash before the element name. 

>This states where the element ends — in this case where the paragraph ends. Failing to add a closing tag is one of the standard beginner errors and can lead to strange results.

>The content: This is the content of the element, which in this case, is just text.

>The element: The opening tag, the closing tag, and the content together comprise the element.

>Attributes contain extra information about the element that you don't want to appear in the actual content. Here, *class* is the attribute name and editor-note is the attribute value. The *class* attribute allows you to give the element a non-unique identifier that can be used to target it (and any other elements with the same *class* value) with style information and other things. Some attributes have no value, such as **required**.

>A space between it and the element name (or the previous attribute, if the element already has one or more attributes).

>The attribute name followed by an equal sign.

>The attribute value wrapped by opening and closing quotation marks.

## Nesting Element

>You can put elements inside other elements too — this is called nesting. If we wanted to state that our cat is very grumpy, we could wrap the word "very" in a <strong> element.

## Void Elements

>This contains two attributes, but there is no closing </img> tag and no inner content. This is because an image element doesn't wrap content to affect it. Its purpose is to embed an image in the HTML page in the place it appears.

## Anatomy of HTML document

><!DOCTYPE html> — doctype. It is a required preamble. In the mists of time, when HTML was young (around 1991/92), doctypes were meant to act as links to a set of rules that the HTML page had to follow to be considered good HTML, which could mean automatic error checking and other useful things. 

><html></html> — the <html> element. This element wraps all the content on the entire page and is sometimes known as the root element. It also includes the lang attribute, setting the primary language of the document.

><head></head> — the <head> element. This element acts as a container for all the stuff you want to include on the HTML page that isn't the content you are showing to your page's viewers.

><meta charset="utf-8"> — This element sets the character set your document should use to UTF-8 which includes most characters from the vast majority of written languages. Essentially, it can now handle any textual content you might put on it. 

><meta name="viewport" content="width=device-width"> — This viewport element ensures the page renders at the width of viewport, preventing mobile browsers from rendering pages wider than the viewport and then shrinking them down.

><title></title> — the <title> element. This sets the title of your page, which is the title that appears in the browser tab the page is loaded in. It is also used to describe the page when you bookmark/favorite it.

><body></body> — the <body> element. This contains all the content that you want to show to web users when they visit your page, whether that's text, images, videos, games, playable audio tracks, or whatever else.

## Links

>Links are very important — they are what makes the web a web! To add a link, we need to use a simple element — <a> — "a" being the short form for "anchor".

## Usage Notes

>Each <article> should be identified, typically by including a heading (<h1> - <h6> element) as a child of the <article> element.

>When an <article> element is nested, the inner element represents an article related to the outer element. For example, the comments of a blog post can be <article> elements nested in the <article> representing the blog post.

>Author information of an <article> element can be provided through the <address> element, but it doesn't apply to nested <article> elements.

>The publication date and time of an <article> element can be described using the datetime attribute of a <time> element.

## Key Resources

>HTML Introduction
If you're new to web development, be sure to read our HTML Basics article to learn what HTML is and how to use it.

>HTML Tutorials
For articles about how to use HTML, as well as tutorials and complete examples, check out our HTML Learning Area.

>HTML Reference
In our extensive HTML reference section, you'll find the details about every element and attribute in HTML.

## Main Root

<html>The <html> HTML element represents the root (top-level element) of an HTML document, so it is also referred to as the root element. All other elements must be descendants of this element.

## Doc. Metadata

>Metadata for styles and scripts may be defined in the page or link to another file that has the information.

<base>The <base> HTML element specifies the base URL to use for all relative URLs in a document. There can be only one <base> element in a document.

<head>The <head> HTML element contains machine-readable information (metadata) about the document, like its title, scripts,and style sheets.

<link>The <link> HTML element specifies relationships between the current document and an external resource. This element is most commonly used to link to CSS, but is also used to establish site icons (both "favicon" style icons and icons for the home screen and apps on mobile devices) among other things.

<meta>The <meta> HTML element represents Metadata that cannot be represented by other HTML meta-related elements, like base, link, script, style or title.

<style>The <style> HTML element contains style information for a document, or part of a document. It contains CSS, which is applied to the contents of the document containing the <style> element.

<title>The <title> HTML element defines the document's title that is shown in a Browser's title bar or a page's tab. It only contains text; tags within the element are ignored.


