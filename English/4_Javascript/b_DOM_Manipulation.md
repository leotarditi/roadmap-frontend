# DOM Tree

The backbone of an HTML document is tags.

According to the Document Object Model (DOM), every HTML tag is an object. Nested tags are "children" of the enclosing one. The text inside a tag is an object as well.

All these objects are accessible using JavaScript, and we can use them to modify the page.

For example, `document.body` is the object representing the `<body>` tag.

Running this code will make the `<body>` red for 3 seconds:

```javascript
document.body.style.background = 'red'; // make the background red
setTimeout(() => document.body.style.background = '', 3000); // return back
```

Here we used `style.background` to change the background color of `document.body`, but there are many other properties, such as:

- `innerHTML` – HTML contents of the node.
- `offsetWidth` – the node width (in pixels).
- …and so on.

Soon we’ll learn more ways to manipulate the DOM, but first we need to know about its structure.

## An Example of the DOM

Let’s start with the following simple document:

```html
<!DOCTYPE HTML>
<html>
<head>
  <title>About elk</title>
</head>
<body>
  The truth about elk.
</body>
</html>
```

The DOM represents HTML as a tree structure of tags. Here’s how it looks:

```
▾
HTML
▾
HEAD
#text ↵␣␣
▾
TITLE
#text About elk
#text ↵
#text ↵
▾
BODY
#text ↵␣␣The truth about elk.↵
```

In the picture above, you can click on element nodes, and their children will open/collapse.

Every tree node is an object.

Tags are element nodes (or just elements) and form the tree structure: `<html>` is at the root, then `<head>` and `<body>` are its children, etc.

The text inside elements forms text nodes, labelled as `#text`. A text node contains only a string. It may not have children and is always a leaf of the tree.

For instance, the `<title>` tag has the text "About elk".

Please note the special characters in text nodes:

- a newline: ↵ (in JavaScript known as `\n`)
- a space: ␣

Spaces and newlines are totally valid characters, like letters and digits. They form text nodes and become a part of the DOM. So, for instance, in the example above, the `<head>` tag contains some spaces before `<title>`, and that text becomes a `#text` node (it contains a newline and some spaces only).

### Top-Level Exclusions

There are only two top-level exclusions:

1. Spaces and newlines before `<head>` are ignored for historical reasons.
2. If we put something after `</body>`, then that is automatically moved inside the body, at the end, as the HTML spec requires that all content must be inside `<body>`. So there can’t be any spaces after `</body>`.

In other cases, everything’s straightforward – if there are spaces (just like any character) in the document, then they become text nodes in the DOM, and if we remove them, then there won’t be any.

### No Space-Only Text Nodes

Here are no space-only text nodes:

```html
<!DOCTYPE HTML>
<html><head><title>About elk</title></head><body>The truth about elk.</body></html>
```

```
▾
HTML
▾
HEAD
▾
TITLE
#text About elk
▾
BODY
#text The truth about elk.
```

Spaces at string start/end and space-only text nodes are usually hidden in tools. Browser tools (to be covered soon) that work with DOM usually do not show spaces at the start/end of the text and empty text nodes (line-breaks) between tags.

Developer tools save screen space this way.

On further DOM pictures, we’ll sometimes omit them when they are irrelevant. Such spaces usually do not affect how the document is displayed.

### Autocorrection

If the browser encounters malformed HTML, it automatically corrects it when making the DOM.

For instance, the top tag is always `<html>`. Even if it doesn’t exist in the document, it will exist in the DOM because the browser will create it. The same goes for `<body>`.

As an example, if the HTML file is the single word "Hello", the browser will wrap it into `<html>` and `<body>`, and add the required `<head>`, and the DOM will be:

```
▾
HTML
▾
HEAD
▾
BODY
#text Hello
```

While generating the DOM, browsers automatically process errors in the document, close tags, and so on.

### Example with Unclosed Tags

A document with unclosed tags:

```html
<p>Hello
<li>Mom
<li>and
<li>Dad
```

…will become a normal DOM as the browser reads tags and restores the missing parts:

```
▾
HTML
▾
HEAD
▾
BODY
▾
P
#text Hello
▾
LI
#text Mom
▾
LI
#text and
▾
LI
#text Dad
```

### Tables Always Have `<tbody>`

An interesting “special case” is tables. By DOM specification, they must have a `<tbody>` tag, but HTML text may omit it. Then the browser creates `<tbody>` in the DOM automatically.

For the HTML:

```html
<table id="table"><tr><td>1</td></tr></table>
```

The DOM structure will be:

```
▾
TABLE
▾
TBODY
▾
TR
▾
TD
#text 1
```

You see? The `<tbody>` appeared out of nowhere. We should keep this in mind while working with tables to avoid surprises.

### Other Node Types

There are some other node types besides elements and text nodes.

For example, comments:

```html
<!DOCTYPE HTML>
<html>
<body>
  The truth about elk.
  <ol>
    <li>An elk is a smart</li>
    <!-- comment -->
    <li>...and cunning animal!</li>
  </ol>
</body>
</html>
```

```
▾
HTML
▾
HEAD
▾
BODY
#text ↵␣␣The truth about elk.↵␣␣
▾
OL
#text ↵␣␣␣␣
▾
LI
#text An elk is a smart
#text ↵␣␣␣␣
#comment comment
#text ↵␣␣␣␣
▾
LI
#text ...and cunning animal!
#text ↵␣␣
#text ↵↵↵
```

We can see here a new tree node type – comment node, labeled as `#comment`, between two text nodes.

We may think – why is a comment added to the DOM? It doesn’t affect the visual representation in any way. But there’s a rule – if something’s in HTML, then it also must be in the DOM tree.

Everything in HTML, even comments, becomes a part of the DOM.

Even the `<!DOCTYPE...>` directive at the very beginning of HTML is also a DOM node. It’s in the DOM tree right before `<html>`. Few people know about that. We are not going to touch that node; we even don’t draw it on diagrams, but it’s there.

The document object that represents the whole document is, formally, a DOM node as well.

### Node Types Summary

There are 12 node types. In practice, we usually work with 4 of them:

- **document** – the “entry point” into DOM.
- **element nodes** – HTML tags, the tree building blocks.
- **text nodes** – contain text.
- **comments** – sometimes we can put information there; it won’t be shown, but JS can read it from the DOM.

## See It for Yourself

To see the DOM structure in real-time, try [Live DOM Viewer](https://live.domviewer.com). Just type in the document, and it will show up as a DOM at an instant.

Another way to explore the DOM is to use the browser developer tools. Actually, that’s what we use when developing.

To do so, open the web page `elk.html`, turn on the browser developer tools, and switch to the **Elements** tab.

It should look like this:

![Browser Developer Tools Example](https://via.placeholder.com/600x400?text=Developer+Tools+Example)

You can see the DOM, click on elements, see their details, and so on.

Please note that the DOM structure in developer tools is simplified. Text nodes are shown just as text. And there are no “blank” (space-only) text nodes at all. That’s fine because most of the time we are interested in element nodes.

Clicking the button in the left-upper corner allows us to choose a node from the webpage using a mouse (or other pointer devices) and “inspect” it (scroll to it in the Elements tab). This works great when we have a huge HTML page (and corresponding huge DOM) and would like to see the place of a particular element in it.

Another way to do it would be

 to right-click an element and select the “Inspect” option. Try exploring the DOM, it’s useful!

## Conclusion

The DOM tree is a crucial concept for web development. Understanding its structure and how it represents HTML will help you manipulate web pages dynamically with JavaScript.

This document provided a basic overview of the DOM tree and some of its essential features. As you continue learning about web development, you will find the DOM to be a powerful tool for creating interactive and dynamic web applications.