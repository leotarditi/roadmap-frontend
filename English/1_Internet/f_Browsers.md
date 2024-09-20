# How Browsers Work

## Introduction

Web browsers are the most commonly used software. In this guide, I'll explain how they work behind the scenes. We will look at what happens when you type `google.com` in the address bar until you see Google's page on your browser screen.

### Browsers We'll Discuss

Currently, there are five main desktop browsers: Chrome, Internet Explorer, Firefox, Safari, and Opera. On mobile devices, the major browsers are Android Browser, iPhone Browser, Opera Mini and Opera Mobile, UC Browser, Nokia S40/S60 browsers, and Chrome. All these browsers, except Opera, are based on WebKit. I will provide examples using the open-source browsers Firefox and Chrome, and Safari (which is partially open-source). According to StatCounter statistics (as of June 2013), Chrome, Firefox, and Safari represent about 71% of global desktop browser usage. On mobile devices, Android Browser, iPhone Browser, and Chrome constitute about 54% of usage.

## The Main Functionality of a Browser

The primary function of a browser is to present the web resource you choose by requesting it from the server and displaying it in the browser window. Typically, the resource is an HTML document, but it can also be a PDF, an image, or some other type of content. The user specifies the resource's location using a URI (Uniform Resource Identifier).

The way the browser interprets and displays HTML files is specified in the HTML and CSS specifications. The W3C (World Wide Web Consortium), which is the standards organization for the Web, maintains these specifications. For years, browsers adhered to only a portion of the specifications and developed their own extensions, causing significant compatibility issues for web authors. Nowadays, most browsers adhere to the specifications to a greater or lesser extent.

Browser user interfaces have a lot in common. Common UI elements include:

- Address bar for entering a URI
- Back and forward buttons
- Options for bookmarking
- Refresh and stop buttons to reload or stop loading current documents
- Home button that takes you to the home page

Interestingly, the browser UI is not specified in any formal specification but comes from good practices formed over years of experience and browsers imitating each other. The HTML5 specification does not define the UI elements a browser must have but lists some common elements. These include the address bar, status bar, and toolbar. Of course, there are browser-specific features, like Firefox's download manager.

## High-Level Infrastructure

The main components of a browser are:

1. **User Interface**: Includes the address bar, back/forward button, bookmark menu, etc. It displays all parts of the browser except the window where you see the requested page.
2. **Browser Engine**: Orders actions between the UI and the rendering engine.
3. **Rendering Engine**: Responsible for displaying the requested content. For example, if the requested content is HTML, the rendering engine parses HTML and CSS and displays the parsed content on the screen.
4. **Networking Tools**: For network calls, such as HTTP requests, using different implementations for different platforms behind a platform-independent interface.
5. **UI Backend**: Used to draw basic widgets like windows and combo boxes. This backend exposes a generic interface that is not platform-specific. Underneath, it uses platform-specific UI methods.
6. **JavaScript Interpreter**: Used to parse and execute JavaScript code.
7. **Data Storage**: This is a persistence layer. The browser may need to store various types of data locally, such as cookies. Browsers also support storage mechanisms like localStorage, IndexedDB, WebSQL, and FileSystem.

## Rendering Engines

The responsibility of the rendering engine is, well... rendering, which is displaying the requested content on the browser screen.

By default, the rendering engine can display images and HTML and XML documents. It can show other types of data through plugins or extensions, for example, to display PDF documents with a PDF reader plugin. However, in this chapter, we will focus on the main use case: displaying images and HTML with CSS formatting.

Different browsers use different rendering engines: Internet Explorer uses Trident, Firefox uses Gecko, and Safari uses WebKit. Chrome and Opera (from version 15) use Blink, a fork of WebKit.

**Analogy:** Think of the rendering engine as a house painter. The painter receives instructions (HTML and CSS) on how the house should look and takes care of painting each wall and room (rendering the content) according to those instructions.

WebKit is an open-source rendering engine that started as an engine for the Linux platform and was modified by Apple to be compatible with Mac and Windows.

### The Main Flow

The rendering engine starts by fetching the content of the requested document from the network layer. This is typically done in 8 KB chunks.

**Analogy:** Think of the rendering engine as a chef cooking a recipe. The chef doesn’t receive all the ingredients at once; instead, they receive them in parts (chunks) and start cooking while continuing to receive more ingredients.

Here is the basic flow of the rendering engine:

1. **Parsing**: The rendering engine begins parsing the HTML document and converts elements into DOM nodes in a tree called the "content tree."
2. **Styling**: The engine parses style data, both from external CSS files and style elements. The style information, along with visual instructions in the HTML code, is used to create another tree: the rendering tree.
3. **Layout**: The rendering tree contains rectangles with visual attributes like color and dimensions. The rectangles are in the correct order to be displayed on the screen.
4. **Painting**: The rendering tree is traversed, and each node is painted with the UI backend layer.

**Analogy:** Imagine parsing is like reading the recipe (HTML document), styling is like choosing the paint colors (CSS), layout is like planning the furniture arrangement in the room, and painting is the act of painting the walls and placing the furniture in the right place.

It is important to understand that this is a gradual process. To enhance the user experience, the rendering engine will attempt to display content on the screen as soon as possible. It will not wait until all HTML is parsed before starting to compile and lay out the rendering tree. Parts of the content will be parsed and displayed while the process continues with the rest of the content coming from the network.

## Analysis: General

Since modern web applications are so complex and can have a lot of user interaction, it is crucial to understand that parsing may not be linear. Additionally, because browsers represent and optimize content in different ways, internal workflows may vary between browsers. The approach described here is a simplification of the real process and does not account for all optimizations or peculiarities that may occur.

## HTML Parser

### What Does an HTML Parser Do?

Think of an HTML parser as a recipe reader. This reader takes a recipe written in a specific format (HTML) and converts it into a more understandable format, like a list of ingredients and steps to follow.

### HTML Grammar

HTML grammar is like a set of rules for writing recipes. These rules, defined by the W3C organization, dictate how recipes (in this case, HTML documents) should be written. Just as a recipe has specific ingredients and steps, HTML has tags and attributes.

### Differences from XML

Unlike XML, which is very strict (like a recipe book that doesn’t allow variations), HTML is more flexible (like a recipe book that allows substitutions). HTML allows certain errors and omissions, making it easier for authors but harder for formal definitions.

### HTML DTD

The DTD (Document Type Definition) is like a recipe book that describes which ingredients (tags) are allowed and how they should be organized. Although HTML is not exactly a context-free grammar, the DTD defines the basic rules for HTML structure.

## DOM (Document Object Model)

### What is the DOM?

The DOM is like a visual representation of the recipe once it's cooked. If HTML is the raw recipe, the DOM is the final dish. The DOM organizes HTML elements into a tree where each node represents a part of the recipe (tags and attributes).

### Example of the DOM

For a simple HTML document like:

```html
<html>
  <body>
    <p>Hello World</p>
    <div><img src="example.png"/></div>
  </body>
</html>
```

The DOM tree would look like:

```
Document
│
├── html
│   └── body
│       ├── p ("Hello World")
│       └── div
│           └── img (src="example.png")
```

### DOM Specification

The DOM is defined by the W3C and provides an interface for manipulating HTML and XML documents. Each node in the DOM tree represents an object in the document.

## Parsing Algorithm

### How Does Parsing Work?

Parsing HTML is like reading a recipe step by step and then organizing the ingredients in the kitchen. HTML does not follow a rigid formal grammar, so specialized techniques are used for parsing it.

### Parsing Stages

1. **Tokenization**: Imagine this stage as identifying ingredients and steps in a recipe. HTML tags and attributes are recognized and transformed into tokens.
   
2. **Tree Construction**: Here, tokens are organized into a DOM tree. It is like organizing ingredients in the kitchen to prepare the dish.

### Example of Tokenization

For the HTML:

```html
<html>
  <body>
    Hello world
  </body>
</html>
```

The token assignment process would be:

- **Initial State**: Reading the `<` character switches to the "Tag open" state.
- **Start Tag Token**: A token for `<html>` is created.
- **Data State**: Reading "Hello world" creates a text token.
- **End Tag Token**: A token for `</body>` is created, and so on.

### Tree Building

In tree building, tokens become DOM nodes. For example:

- The `<html>` token creates an `HTMLHtmlElement` node.
- The `<body>` token creates an `HTMLBodyElement` node.

## Browsers and Error Tolerance

### How Do Browsers Handle Errors?

Imagine that in the kitchen, if an ingredient is measured wrong, the chef adjusts it on the fly. Browsers do the same with HTML. They correct errors and display the content in the best possible way.

### Error Tolerance Examples

- **Misspelled Tags**: `<br>` instead of `</br>`.
- **Broken Tables**: A table inside another table not in a cell.

Browsers adjust the HTML structure to correct these errors and ensure that the page displays correctly.

## CSS Analysis

### What is CSS?

CSS is like the recipe book for presentation. While HTML provides the structure, CSS defines how it looks. The grammar of CSS can be formally analyzed, making it easier to process.

### CSS Grammar Example

The grammar of CSS is defined using regular expressions and BNF. For example, for a CSS rule:

```css
div.error, a.error {
  color: red;
  font-weight: bold;
}
```

- **Selector**: `div.error, a.error`
- **Declaration**: `color: red; font-weight: bold;`

The grammar defines how selectors and declarations are combined.

# Render Tree Construction

When your browser is ready to display a web page, it performs a series of steps to convert HTML and CSS code into something you can see on the screen. One of the most important steps is the construction of the **render tree**. Let's break down this process and use some analogies to make it easier to understand.

## What is the Render Tree?

Imagine you are building a miniature city model. You have blueprints (HTML) and materials (CSS) to construct buildings, roads, and parks. As you assemble each element, you decide how it will look and in what order it should be placed. The **render tree** is like the final model you see in your miniature city: it represents how the elements should be displayed on your web page.

In the browser, while constructing the **DOM tree** (Document Object Model), which is like a blueprint of HTML elements on your page, the render tree is also built. This tree contains all the visual elements and the order in which they will be displayed.

- **Firefox** refers to elements in the render tree as "frames."
- **WebKit** (the rendering engine for Safari) uses the term "render object."

### Render Object Analogy

Think of the render object as a master builder who knows how to design and build each type of building in your model. Each render object handles a rectangular area in the model, like an apartment block or a park, and knows how to place its elements.

```cpp
class RenderObject {
  virtual void layout();  // Organizes the object's space
  virtual void paint(PaintInfo);  // Draws the object
  virtual void rect repaintRect();  // Defines the object's area
  Node* node;  // DOM node
  RenderStyle* style;  // Computed style
  RenderLayer* containingLayer;  // Containing z-index layer
}
```

In this class, `RenderObject` is like the master builder who organizes and paints the elements in its assigned area.

## Relationship Between Render Tree and DOM Tree

Not all DOM nodes become visual elements. Imagine that in your city model you have plans for some elements that will not be built, like underground foundations. These will not appear in the final model, just as DOM elements with `display: none` do not appear in the render tree.

Additionally, some DOM elements can correspond to multiple visual elements. For example, a `<select>` element may be represented by several render objects: one for the dropdown area, one for the button, and one for the options list.

Also, some visual elements are placed in different parts of the render tree based on their style. Elements with absolute or floating positioning are placed in specific locations, while others follow the normal document flow.

### City Analogy

In your city model, buildings (visual elements) are not always constructed in the same order as in the blueprints (DOM). Some buildings may have special features (like a park instead of a skyscraper) and are placed in different areas of the model according to their characteristics (styles).

## Render Tree Construction

In **Firefox**, the process of building the render tree is handled by the `FrameConstructor`, which resolves the style and creates the corresponding frames (renderers). In **WebKit**, the process is called "attachment," where each DOM node is turned into a render object.

The root of the render tree corresponds to the visible area of the browser window, and this is where all the other blocks start being constructed.

### Construction Analogy

Think of the `FrameConstructor` as an architect who builds the basic structure of the city from the blueprints. Then, workers (render objects) add details to each building according to the blueprints and defined styles.

## Style Calculation

To paint each element correctly, the browser needs to calculate how CSS styles should be applied. This process is known as **style calculation**.

The style of each element comes from several sources: browser style sheets, author styles, and user styles. These styles are calculated and applied in a cascading manner, taking into account priority and specificity rules.

### Material Selection Analogy

When building a model building, you decide which materials to use (e.g., brick or wood). These materials are chosen according to a set of rules and priorities. Similarly, the browser selects style properties for each element based on CSS rules.

## Sharing Style Data

In WebKit, DOM nodes can share style objects (`RenderStyle`) if they meet certain conditions, such as having the same mouse state, class, or attributes. This helps optimize performance by avoiding repeated calculations.

### Shared Materials Analogy

If you have several buildings in your model that use the same type of brick, you might buy a large quantity at once to save costs. Similarly, sharing style objects among nodes helps reduce calculation time and memory usage.

# Frontend Design and Rendering Guide

## Design

Imagine you are organizing a party and need to place furniture in a room. First, you decide where each piece of furniture will go and how much space they will take up. This is similar to the design process in a web browser. Design calculates the position and size of elements on a web page.

**What does design do?**
- When you create an HTML element, like a div or a paragraph, it initially has no specific position or size. The process of calculating these values is called **layout** or **reflow**.
- HTML uses a flow-based layout model. This means that elements are placed sequentially from left to right and from top to bottom, like arranging furniture in a room in an orderly row.

**Coordinate System**
- The position of each element is measured relative to the root frame. The position (0,0) corresponds to the top-left corner of the browser window.

**Recursive Layout**
- The layout process starts at the root element (`<html>`) and then propagates through all child elements, calculating the geometric information for each one.

## Dirty Bits System

To avoid having to rearrange the entire room every time you make a small change, browsers use a **dirty bits** system.

**What is a dirty bit?**
- When a change is made to an element, that element and its children are marked as "dirty," indicating that they need a new layout. Only these elements need to be recalculated, rather than the entire layout.

## Incremental and Global Layout

**Global Layout**
- Sometimes, you need to reorganize the entire room, such as when making a style change that affects all elements on the page, like changing the font size. This is **global layout**.

**Incremental Layout**
- Other times, you only need to adjust part of the room, such as adding a new piece of furniture. This is **incremental layout**, where only the changed elements are updated.

## Asynchronous and Synchronous Layout

**Asynchronous Layout**
- Incremental layout is performed **asynchronously**, meaning it does not occur immediately but is scheduled to happen in the future.

**Synchronous Layout**
- Global layout generally occurs **synchronously**, meaning it happens immediately.

## Optimizations

**Cache Usage**
- To avoid recalculating the entire layout from scratch, the browser uses a **cache**. If an element's size or position changes, previously calculated values are consulted instead of recalculating everything.

**Local Layout**
- If only a small detail on the page changes, like adding text in a form field, the layout only affects that part, without recalculating the entire page.

## Layout Process

The layout process follows these basic steps:

1. **Determine the width of the parent element.**
2. **Place child elements within the parent element.**
3. **Calculate the total height of the parent element based on its children.**
4. **Mark the process as complete.**

## Width Calculation

Imagine adjusting the width of a table to fit a specific space. The browser calculates the width of HTML elements in a similar way, taking into account the container, margins, and borders.

**Example:**
```html
<div style="width: 30%"></div>
```
- The width is calculated as a percentage of the available container, adjusted for margins and borders.

## Line Breaks

When an element does not fit on one line, it wraps to the next line, similar to how furniture would be rearranged to fit in a room.

## Painting

**Global and Incremental Painting**
- **Global Painting**: Like repainting the entire room.
- **Incremental Painting**: Only repaints the affected area, similar to touching up a wall that has been damaged.

**Painting Order**
- Painting follows a specific order: background color, image, border, and then the content of the elements.

## Rectangular Storage and Dynamic Changes

**Rectangular Storage**
- Before repainting, some browsers store a bitmap of the previous screen to update only the changed areas.

**Dynamic Changes**
- Minor changes, like a color change, affect only the specific element. Major changes, like adding a new element, require layout and repainting of the page.

## Rendering Engine Threads

The browser uses a **main thread** to manage layout and painting, while network operations are handled in parallel threads.

**Event Loop**
- The browser maintains an **event loop** that waits

 for events (like user interactions) and processes them sequentially.

**Multi-Threaded Rendering**
- Some modern browsers use multiple threads to speed up rendering and avoid blocking the main thread.

## Conclusion

Rendering is a complex process involving many stages, from parsing HTML and CSS to calculating layout and painting. Understanding these steps helps in creating efficient and visually appealing web pages.

---

# Populating the Page: How Browsers Work

Users desire fast and interactive web experiences. Therefore, developers must work to optimize both aspects. To improve performance and speed perception, it's crucial to understand how browsers work.

## Overview

Fast websites provide better user experiences. Users expect content to load quickly and be easy to interact with. The two main performance issues in web development are latency and the fact that browsers operate on a single thread.

### Latency

Imagine you're at a store asking an employee for a product. If the employee needs to fetch the product from another department, it takes time. Latency is the time it takes to transmit data from the server to your browser. The goal is to minimize this time so that the site loads as quickly as possible.

### Single-Threaded Browsers

Think of your browser as a person who performs tasks one at a time. First, the browser has to complete one task (like painting the screen) before moving on to the next. This means it's crucial that each task is completed efficiently to ensure a smooth experience.

## Navigation

Navigation is the first step in loading a web page. It's like asking for directions in an unfamiliar city. The URL you enter is like the name of a street you want to visit. The browser first needs to find the IP address of the server hosting the page, which is done through a DNS lookup.

### DNS Lookup

If you've never visited a website before, the browser must find its IP address. This is like looking up an address in a phone book. The DNS lookup is done once per hostname and is cached for faster future visits.

### TCP Handshake

Once the IP address is known, the browser establishes a connection with the server through a three-way handshake (SYN-SYN-ACK). It's like two people shaking hands and agreeing on the details of a meeting before starting to talk. This ensures the connection is stable before starting to exchange data.

### TLS Negotiation

For secure connections (HTTPS), a second handshake called TLS negotiation is performed. It's like making sure both participants in a secret conversation are using the same encrypted language before starting to talk. This process adds time to the page load but ensures the data is secure.

## Response

With the connection established, the browser sends an HTTP GET request to fetch the HTML file of the page. The server responds with the HTML content, which includes references to other resources like CSS, JavaScript, and images.

### Congestion Control / TCP Slow Start

TCP slow start is like adjusting the amount of information you send to a friend so as not to overwhelm them. You send a few packets at first and then gradually increase the amount if everything goes well. This helps balance the load and optimize network performance.

## Parsing

When the browser receives the data, it starts parsing the information to convert it into a format it can display on the screen. It's like reading a book and turning it into a visual representation. The browser converts HTML into a DOM tree and CSS into a CSSOM tree.

### Building the DOM Tree

The DOM tree is like a blueprint of your house. Each node represents an element on the page, and the structure shows how they are organized. Elements that won't be displayed (like hidden scripts) are not included in the render tree.

### Preload Scanner

As the browser builds the DOM tree, the preload scanner searches for and downloads important resources (like CSS and JavaScript) in the background. It's like preparing ingredients for a recipe while you're cooking, so everything is ready when you need it.

### Building the CSSOM Tree

The CSSOM tree is like a style guide for the elements on the page. It converts CSS rules into a format that the browser can use to apply styles to elements.

## Other Processes

### JavaScript Compilation

JavaScript is parsed, compiled, and interpreted. This is like translating a text into a language that the browser can understand. The code is converted into a format that the browser can execute to make the page interactive.

### Building the Accessibility Tree

The accessibility tree is a semantic representation of the DOM that helps assistive devices interpret the content of the page. It's like having a Braille version of a book for visually impaired people.

## Render

The rendering process includes style, layout, painting, and sometimes composition. The CSSOM and DOM trees are combined into a render tree, which is used to calculate the layout of each visible element and then paint it on the screen.

### Style

The render tree combines the DOM and CSSOM. It's like combining an architectural blueprint with a decoration guide to build a visual model of the house.

### Layout

Layout determines the size and position of each element on the page. It's like arranging furniture in a room based on the dimensions of the space.

In summary, understanding how the browser works will help you optimize performance and improve the user experience on your web pages. Each step, from DNS lookup to rendering, plays a crucial role in how quickly and efficiently a page loads.
