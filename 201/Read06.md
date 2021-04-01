# Read06

## JS

### Article [Problem Domain](https://simpleprogrammer.com/understanding-the-problem-domain-is-the-hardest-part-of-programming/)

#### I learned from this article

1. Some of the hardest things about writing code
    - Learning a new technology
    - Naming things
    - Testing your code
    - Debugging
    - Fixing bugs
    - Making software maintainable
1. taking away the problem domain, or making it so trivial that it is easily understood can make both teaching and learning easier.
1. many problem domains are hard because they are like a puzzle with a blurry picture or no picture at all.
1. Programming is easy if you understand the problem domain
1. You can often make the problem domain easier by cutting out cases and narrowing your focus to a particular part of the problem.

### Object

#### I learned from this topic

1. If a variable is part of an object, it is called a **property**.
1. If a function is part of an object, it is called a method
1. what is keys and values in objects
1. how to create objects with literal notation
1. accessing the values using dot notation

### Document Object Model

#### I learned from this chapter

1. THE DOM TREE IS A MODEL OF A WEB PAGE
1. Scripts access and update this DOM tree (not the source HTML file).
1. how to work with the dom tree
1. DOM queries
    - getElementById('id');
    - querySelector('css selector')
    - getElementsByClassName('class') => Nodelist
    - getElementsByTagName('tagName) => Nodelist
    - querySelectorAll ('css selector') => Nodelist

1. DOM queries may return one element, or they may return a Nodelist
1. selecting an element from a nodelist
    - the item() method
    - array syntax: []
1. you can loop through each node in the nodelist
1. traversing the DOM
    - parentNode
    - previousSibling
    - nextSibling
    - firstChild
    - lastChild
1. Traversing the DOM can be difficult because some browsers add a text node whenever they come across whitespace between elements.
1. access and update a text node with nodeValue, textContent, innerText
1. adding and removing HTML content
    - innerHTML property
    - DOM manipulation
1. comparing techniques for updating html content between:
    - document.write
    - element.innerHTML
    - DOM MANIPULATION
1. If you add HTML to a page using innerHTML (or several jQuery methods), you need to be aware of Cross-Site Scripting Attacks or XSS
1. you can defend against XSS validating the inputs FILTER OR VALIDATE INPUT and LIMIT WHERE USER CONTENT GOES
1. DO use: textContent or innerText
1. DO NOT use: innerHTML

+ Attribute Nodes
1. getAttribute(), hasAttribute(), setAttribute(), removeAttribute()
1. creating Attribute and changing their values

+ examining the DOM in browsers

1. 
