# HTML

HTML (Hyper Text Markup Language) let's you create web pages. The [demo at the end of the programming section](../1-programming/demo/) used HTML to display a few instructions and use JS and seeing the responses in the browser console. By the end of this page, you should be able to understand what is going on in that demo.

HTML is a DOM tree. DOM stands for Document Object Model. Every element in HTML is a part of this tree. What this means is that most elements have a parent, and can have multiple children. ("most" since the first element, the root only has children). [This article gives an introduction to the DOM](https://medium.com/@josephchavez_33756/the-dom-tree-no-its-not-an-actual-tree-566cff758672).

## Structure

The following shows the basic structure of an HTML document.

```html
<html>
    <head>
        <title>HTML | Dev101</title>
    </head>
    <body>
        <p>Hello World!</p>
    </body>
</html>
```

Everything in this snippet is an element. The `html` is the root element and has two children - `head` and `body`. 

As mentioned before, the `head` gives your page an identity. It defines what the page is, the title, and much more. The `body` gives it structure. Everything inside the `body` element is what is rendered on the webpage. 

Copy this into an HTML file and open it using the live server and you should see "Hello World!" on the screen. Changing this text and saving will update the rendered text. Change what is written in the `title` element and the name of the page should update as well.

## Tags

Every element consists of a tag at the very least. Tags are identified by the angled brackets with the name of the element in between. There are opening and closing tags, and self-closing tags.

### Opening and Closing Tags

These tags are used to render contents directly on the page. All elements in the above snippet use opening and closing tags. These tags can have children elements. 

Example: `<p>This is a paragraph tag</p>`

### Self-Closing Tags

Technically, self-closing tags do not exist. These are actually called *void elements*. We will stick with self-closing tags throughout this series as that is the more common term used to refer to such elements. [Explanation between the two if you are interested.](https://developer.mozilla.org/en-US/docs/Glossary/Void_element#self-closing_tags) 

These tags cannot have any children. You can add `/>` at the end instead of the regular `>` but it doesn't do anything. (TIL from the link above as well). Most places have a forward slash and some formatters will add it for you as they are required by XML, SVG, etc. Don't worry if you don't understand those terms. They aren't required to learn basic HTML. For this series, we will keep the slashes in *void* elements.

Example: `<img src="./link/to/image" />`

## Attributes

Attributes are used to define additional properties for HTML elements. The `src` part in the example above is an attribute in the `img` element. The `img` element is used to display an image. The `src` attribute defines the source of the image.

Attributes are added in the opening tags for elements that have a closing tag. For self-closing elements, they are added in the element itself.

A few common basic attributes, which are used by almost all elements include:

- `style` - Used to add give your elements styles
- `id` - Used to *uniquely* identify an element
- `class` - Used to identify similar elements

We will use these three fairly often in the parts ahead as it will be easier to demonstrate how they work rather than talking about them in detail.