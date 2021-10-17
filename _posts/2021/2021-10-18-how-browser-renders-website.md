---
layout: post
title: How the browser renders a Website?
---

To understand the mechanics of each step a browser goes through to render a web page by series of process, the processes can be broken down into these main stages:

1. Start to parse the HTML
2. Fetch external resources
3. Parse the CSS and build the CSSOM
4. Execute the JavaScript
5. Merge DOM and CSSOM to construct the render tree
6. Calculate layout and paint

## 1. Start to parse the HTML

When the browser begins to receive the HTML data of a page over the network, it immediately sets its parser to work to convert the HTML into a Document Object Model (DOM).

> The Document Object Model (DOM) is the data representation of the objects that comprise the structure and content of a document on the web.

The first step of this parsing process is to break down the HTML into tokens that represent start tags, end tags, and their contents. From that it can construct the DOM.

## 2. Fetch external resources

When the parser comes across an external resource like a CSS or JavaScript file, it goes off to fetch those files. The parser will continue as a CSS file is being loaded, although it will block rendering until it has been loaded and parsed (more on that in a bit).

JavaScript files are a little different - by default they block parsing of the HTML whilst the JavaScript file is loaded and then parsed. There are two attributes that can be added to script tags to mitigate this: defer and async. Both allow the parser to continue whilst the JavaScript file is loaded in the background, but they operate differently in the way that they execute. More on that in a bit too, but in summary:

`defer`means that the execution of the file will be delayed until the parsing of the document is complete. If multiple files have the defer attribute, they will be executed in the order that they were discovered in the HTML.

```
<script type="text/javascript" src="script.js" defer>
```

`async` means that the file will be executed as soon as it loads, which could be during or after the parsing process, and therefore the order in which async scripts are executed cannot be guaranteed.

```
<script type="text/javascript" src="script.js" async>
```

## 3. Parse the CSS and build the CSSOM

> The CSS Object Model (CSSOM) is a map of all CSS selectors and relevant properties for each selector in the form of a tree, with a root node, sibling, descendant, child, and other relationship. The CSSOM is very similar to the Document Object Model (DOM). Both of them are part of the critical rendering path which is a series of steps that must happen to properly render a website.
> The CSSOM, together with the DOM, to build the render tree, which is in turn used by the browser to layout and paint the web page.

Similar to HTML files and the DOM, when CSS files are loaded they must be parsed and converted to a tree - this time the CSSOM. It describes all of the CSS selectors on the page, their hierarchy and their properties.

Where the CSSOM differs to the DOM is that it cannot be built incrementally, as CSS rules can overwrite each other at various different points due to specificity. This is why CSS blocks rendering, as until all CSS is parsed and the CSSOM built, the browser can't know where and how to position each element on the screen.

## 4. Execute the JavaScript

## 5. Merge DOM and CSSOM to construct the render tree

## 6. Calculate layout and paint
