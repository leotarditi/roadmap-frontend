# JavaScript Can Change HTML Content

In JavaScript, one of the most common ways to interact with HTML is by using the `getElementById()` method. This method allows JavaScript to "find" an HTML element by its `id` and then change its content.

### Analogy
Imagine your HTML page is like a board with sticky notes (elements), each note has a unique label (an `id`). JavaScript is like a pair of hands that can reach out to one of those notes (by using `getElementById`), and rewrite the text on it (by modifying the `innerHTML`).

### Example
```javascript
document.getElementById("demo").innerHTML = "Hello JavaScript";
```
In this example, JavaScript finds the sticky note labeled "demo" and replaces its content with "Hello JavaScript."

### Technical Explanation
- `innerHTML`: This property represents the content inside an HTML element. By assigning new content to `innerHTML`, you can change what's displayed on the page.

### Did You Know?
JavaScript allows you to use both single and double quotes when assigning text:
```javascript
document.getElementById('demo').innerHTML = 'Hello JavaScript';
```

---

## JavaScript Can Change HTML Attribute Values

JavaScript can also change the attributes of HTML elements, such as the source (`src`) of an image. Again, `getElementById()` is used to find the element, and then the specific attribute can be modified.

### Analogy
Think of an HTML element like a toy car, and the attributes are like the stickers or colors on the car. If you want to change how the car looks or behaves (like its color or which battery it uses), you modify these attributes.

### Example
```javascript
document.getElementById("myImage").src = "lightbulb-on.png";
```
Here, JavaScript is switching the `src` attribute of an image, changing which picture is displayed (in this case, turning a light bulb "on").

### Technical Explanation
- `src`: This is the attribute in an `<img>` tag that defines which image file should be displayed. By changing it, you can swap out the image on the page.

---

## JavaScript Can Change HTML Styles (CSS)

In addition to modifying HTML content and attributes, JavaScript can also change an element's style by manipulating CSS properties directly.

### Analogy
Imagine that HTML elements are like mannequins in a store window, and the CSS styles are the clothes they wear. JavaScript is like a stylist who can quickly change their outfit, for example, by making their font larger or changing the color of their shirt.

### Example
```javascript
document.getElementById("demo").style.fontSize = "35px";
```
In this case, JavaScript is changing the font size of the element with the `id` "demo" to 35 pixels.

### Technical Explanation
- `style`: This property allows you to access and modify the inline styles of an element. Any CSS rule, such as `fontSize`, `color`, or `margin`, can be changed dynamically through JavaScript.

---

## JavaScript Can Hide HTML Elements

You can use JavaScript to hide an element on the page by adjusting its `display` style.

### Analogy
Think of the HTML element as an object in a room. To hide it, it's like putting a blanket over the object—it’s still there, but no one can see it.

### Example
```javascript
document.getElementById("demo").style.display = "none";
```
Here, JavaScript is setting the `display` property of the element "demo" to "none", effectively making it disappear from the page.

---

## JavaScript Can Show HTML Elements

Similarly, JavaScript can also make a hidden element reappear by changing the `display` property back to "block" or another visible value.

### Analogy
Using the same room analogy, showing an element is like pulling the blanket off the object, making it visible again.

### Example
```javascript
document.getElementById("demo").style.display = "block";
```
With this code, the previously hidden "demo" element is made visible again.

---

## Did You Know?

JavaScript and Java might sound similar, but they are completely different languages in terms of design and concept.

- **JavaScript** was created by Brendan Eich in 1995 and became an official standard in 1997.
- **ECMA-262** is the formal name of the standard that defines JavaScript.
- **ECMAScript** is the official name of the language.

---

# Understanding the `<script>` Tag in HTML

## What is the `<script>` Tag?

Think of the `<script>` tag like a delivery van. It's how we get JavaScript, the language that brings your web pages to life, into your HTML. When we need to deliver functionality, like changing text or responding to a button click, we load JavaScript between `<script>` and `</script>` tags.

### Example:
```html
<script>
  document.getElementById("demo").innerHTML = "My First JavaScript";
</script>
```
In this example, we use JavaScript to change the content inside an HTML element with the `id="demo"`. It’s like telling the delivery van to bring in new content.

---

## Old School vs. New School: `type="text/javascript"`

In the early days, you had to specify the type of script, like putting a label on a box so people knew what was inside. That’s why you might see this:

```html
<script type="text/javascript"></script>
```

But today, JavaScript is the default language. So just like with a familiar delivery service, we don’t need to label the box anymore. The browser already knows that `<script>` means JavaScript.

---

## JavaScript Functions and Events

A **function** in JavaScript is like a little machine inside our delivery van. When you push the button (or in code, when you "call" the function), it does something, like delivering a message.

An **event** is the button you push. It could be clicking a button, typing into a form, or scrolling a page.

### Example:

```html
<button onclick="myFunction()">Click me</button>
<script>
  function myFunction() {
    alert("Button was clicked!");
  }
</script>
```

Here, the function is the machine that shows an alert, and the event is the button click that starts the machine. Simple, right?

---

## Where Should You Put the `<script>`?

The `<script>` can go in different parts of your HTML: either in the `<head>` or in the `<body>`. It’s like deciding whether to pack the delivery van early or wait until the end.

### Scripts in `<head>`

Placing a script in the `<head>` is like setting up your tools before the job starts. The script is ready as soon as the page begins loading.

### Example:
```html
<!DOCTYPE html>
<html>
<head>
  <script>
    function myFunction() {
      document.getElementById("demo").innerHTML = "Text changed!";
    }
  </script>
</head>
<body>
  <p id="demo">This is a paragraph.</p>
  <button onclick="myFunction()">Change Text</button>
</body>
</html>
```

### Scripts in `<body>`

Putting the script in the `<body>` is like waiting until the last minute to load the van. It can speed up the page display because the page doesn’t wait for the JavaScript to load.

### Example:
```html
<!DOCTYPE html>
<html>
<body>
  <p id="demo">This is a paragraph.</p>
  <button onclick="myFunction()">Change Text</button>
  <script>
    function myFunction() {
      document.getElementById("demo").innerHTML = "Text changed!";
    }
  </script>
</body>
</html>
```

### Which is Better?

Usually, placing scripts at the bottom of the `<body>` is better for performance. It’s like loading up the delivery van last, so it doesn’t slow down the rest of the work.

---

## External JavaScript

You can also load your JavaScript from an external file, just like calling for reinforcements from another warehouse. This is super useful when you want to use the same code across multiple pages.

### Example:
```html
<script src="myScript.js"></script>
```

This is like linking to a toolbox stored in a separate file (e.g., `myScript.js`). All your JavaScript lives there, and you just reference it whenever you need it.

### Benefits of External JavaScript:
- **Separation of concerns**: HTML is for structure, JavaScript is for behavior. It’s like keeping your tools organized by job type.
- **Easier maintenance**: If you need to update the script, you do it in one place. It’s like updating a central warehouse instead of every delivery van.
- **Faster loading**: Once the browser loads the script file, it can reuse it without loading it again. This is like using the same tools across multiple jobs.

---

## External Script References

You can reference external JavaScript files in three ways:
1. **Full URL**: Think of it as a direct address to a warehouse across the web.
   ```html
   <script src="https://www.example.com/js/myScript.js"></script>
   ```

2. **File path**: This points to a script on the same server, like pulling tools from the local storage room.
   ```html
   <script src="/js/myScript.js"></script>
   ```

3. **No path**: The script is in the same folder as the HTML file, like grabbing a tool from the van itself.
   ```html
   <script src="myScript.js"></script>
   ```

Each method is just another way to organize how you pull in JavaScript, depending on where the file lives.

---

## Conclusion

The `<script>` tag is your tool for bringing JavaScript into your HTML page. Whether you place it in the `<head>`, `<body>`, or use an external file, it's all about how and when you want to load those tools. And remember, organizing your JavaScript in external files helps keep things neat and efficient.

Next time, we’ll dive deeper into **JavaScript functions and events**, which are the real power tools of web development.

---

# JavaScript Display Possibilities 🚀

JavaScript gives you several ways to display data on a webpage. Think of JavaScript as a magician that can perform different tricks to show information. Each trick has its own style and purpose. Let’s dive into these display methods and understand them with simple analogies.

## 1. Writing into an HTML Element with `innerHTML` ✍️

Imagine you have a whiteboard (the HTML element), and you want to write something on it. JavaScript can grab a marker and write directly on the whiteboard using the `innerHTML` property.

### Example:
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My First Paragraph</p>

<p id="demo"></p> <!-- This is where we'll write -->

<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>

</body>
</html>
```

### Analogy:
`document.getElementById("demo")` is like pointing to a specific whiteboard, and `innerHTML` is the action of writing on it. This is one of the most common ways to update content on a webpage. You just say: "Write this on that board!"

## 2. Writing into the HTML Output with `document.write()` 📝

Imagine you are writing a letter as it’s being typed out. JavaScript can insert text or content into the webpage as it loads using `document.write()`. But there’s a catch—if you try to use this after the letter (page) is already complete, it will erase everything and start a new letter!

### Example:
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
document.write(5 + 6);
</script>

</body>
</html>
```

### Analogy:
`document.write()` is like writing on a piece of paper while it’s still coming out of the printer. Once the page is fully printed, using `document.write()` again is like tearing up the page and printing a new one. That’s why we only use this for testing purposes, not in a fully loaded webpage.

## 3. Displaying Data in an Alert Box with `window.alert()` 🔔

This is like tapping someone on the shoulder and showing them a sticky note. When you use `alert()`, it interrupts everything and shows a pop-up with a message.

### Example:
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```

### Analogy:
`window.alert()` is the equivalent of loudly saying, “Hey! Look at this!” It halts everything on the page and shows an alert box with your message. You can skip the `window` part, as JavaScript assumes you’re talking about the global window object.

## 4. Writing to the Console with `console.log()` 🛠️

This method is like keeping notes in a personal notebook behind the scenes. You don’t show this information to users on the webpage; instead, you log it in the browser’s developer tools, which helps you debug the code.

### Example:
```html
<!DOCTYPE html>
<html>
<body>

<script>
console.log(5 + 6);
</script>

</body>
</html>
```

### Analogy:
Think of `console.log()` as a private diary where you keep track of your calculations and thoughts. It’s not visible to your users, but you can use it to check if your code is running correctly. Super useful for debugging!

## 5. Printing the Page with `window.print()` 🖨️

JavaScript doesn't have a direct way to send content to a printer. However, it can ask the browser to print the current webpage using `window.print()`.

### Example:
```html
<!DOCTYPE html>
<html>
<body>

<button onclick="window.print()">Print this page</button>

</body>
</html>
```

### Analogy:
`window.print()` is like handing someone a button that says, “Print this document!” It doesn’t control the printer directly, but it triggers the browser’s print functionality for the user.

---

## Recap 📋
JavaScript has several ways to display data, depending on what you need:
- **`innerHTML`**: Like writing on a whiteboard everyone can see.
- **`document.write()`**: Like writing on a page as it prints—be careful, as it can overwrite everything.
- **`window.alert()`**: Like showing a sticky note in front of someone’s face.
- **`console.log()`**: Like keeping notes in a private diary (useful for debugging).
- **`window.print()`**: Like giving a button to print the current page.

---

# JavaScript Statements

## What are JavaScript Statements?

In programming, think of a computer program as a recipe. Just like a recipe lists the steps needed to create a dish, a computer program consists of a list of "instructions" that the computer "executes" to perform tasks.

### Example of JavaScript Statements

```javascript
let x, y, z;    // Statement 1
x = 5;          // Statement 2
y = 6;          // Statement 3
z = x + y;      // Statement 4
```

In this example:
- **Statement 1**: We declare three variables: `x`, `y`, and `z`. This is like setting up your ingredients on the table before you start cooking.
- **Statements 2-4**: We assign values to `x` and `y`, and calculate their sum to store in `z`. Each step is executed in order, just like following a recipe.

## JavaScript Programs

A JavaScript program is essentially a collection of statements (instructions) that the web browser executes. When you run a JavaScript program in HTML, the browser interprets these statements to perform actions on the webpage.

### Composition of JavaScript Statements

JavaScript statements are made up of:
- **Values**: The data you work with, like numbers and strings.
- **Operators**: Symbols that perform operations (e.g., `+`, `-`).
- **Expressions**: Combinations of values and operators that produce a value.
- **Keywords**: Reserved words that perform specific actions.
- **Comments**: Notes in the code that are ignored by the browser, used to explain code to other programmers.

For example, the statement below instructs the browser to display "Hello Dolly." inside an HTML element with the id of "demo":

```javascript
document.getElementById("demo").innerHTML = "Hello Dolly.";
```

Just like you follow each instruction in a recipe step by step, JavaScript statements are executed one after the other in the order they are written.

## Semicolons (;)

Semicolons are like periods at the end of sentences in a book. They indicate the end of a statement. It's good practice to add a semicolon at the end of each executable statement:

### Examples

```javascript
let a, b, c;  // Declare 3 variables
a = 5;        // Assign the value 5 to a
b = 6;        // Assign the value 6 to b
c = a + b;    // Assign the sum of a and b to c
```

You can also write multiple statements on one line separated by semicolons:

```javascript
a = 5; b = 6; c = a + b;
```

While it’s possible to omit semicolons, it's highly recommended to use them for clarity and to avoid potential issues.

## JavaScript White Space

JavaScript ignores extra spaces, which means you can format your code to make it more readable. 

For example, these two lines are equivalent:

```javascript
let person = "Hege";
let person="Hege";
```

A good practice is to add spaces around operators (e.g., `=`, `+`, `-`, `*`, `/`):

```javascript
let x = y + z;
```

## JavaScript Line Length and Line Breaks

To maintain readability, try to keep your lines under 80 characters. If a statement is too long, break it after an operator:

### Example

```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly!";
```

## JavaScript Code Blocks

JavaScript allows you to group statements together in code blocks using curly braces `{...}`. This helps define statements that should be executed together, similar to how you might group related instructions in a recipe.

### Example of a Function with Code Blocks

```javascript
function myFunction() {
  document.getElementById("demo1").innerHTML = "Hello Dolly!";
  document.getElementById("demo2").innerHTML = "How are you?";
}
```

In this tutorial, we use 2 spaces of indentation for code blocks to enhance readability. You will learn more about functions in later sections.

## JavaScript Keywords

JavaScript statements often start with a keyword, similar to how certain phrases signal the start of instructions in a recipe. Here are some common keywords you’ll encounter:

| Keyword | Description                                     |
|---------|-------------------------------------------------|
| `var`   | Declares a variable                             |
| `let`   | Declares a block-scoped variable               |
| `const` | Declares a block-scoped constant               |
| `if`    | Marks a block of statements to be executed on a condition |
| `switch`| Marks a block of statements to be executed in different cases |
| `for`   | Marks a block of statements to be executed in a loop |
| `function`| Declares a function                          |
| `return`| Exits a function                               |
| `try`   | Implements error handling to a block of statements |

Remember, JavaScript keywords are reserved words, meaning you cannot use them as names for variables. Just like you wouldn’t use a key ingredient as the name for another dish!

## Conclusion

Understanding JavaScript statements is crucial for becoming a proficient frontend developer. Each statement is like a step in a recipe, leading to the final dish—a dynamic, interactive web application. By practicing these concepts, you’ll be well on your way to mastering JavaScript!

---

# JavaScript Syntax

JavaScript syntax is the set of rules that dictate how JavaScript programs are constructed. Think of it as the grammar of a language, providing a structure that allows us to communicate effectively with the computer.

### How to Create Variables
```javascript
// Declare variables
var x; // old way of declaring variables
let y; // modern way of declaring variables
```

### How to Use Variables
```javascript
x = 5; // Assigning a value to x
y = 6; // Assigning a value to y
let z = x + y; // Adding x and y to create z
```

---

## JavaScript Values

The JavaScript syntax defines two types of values:

- **Fixed values**
- **Variable values**

Fixed values are called **Literals**, while variable values are referred to as **Variables**.

### JavaScript Literals

The two most important syntax rules for fixed values are:

1. **Numbers** can be written with or without decimals:
   - Example: `10.50`, `1001`
   
2. **Strings** are text, written within double or single quotes:
   - Example: `"John Doe"` or `'John Doe'`

### Analogy
Think of literals as the building blocks of a structure. Just like you can use either bricks (whole numbers) or tiles (decimal numbers) to build a house, you can use both types of literals in your code.

---

## JavaScript Variables

In programming, variables are used to store data values. They are like labeled boxes where you can keep things organized.

JavaScript uses the keywords `var`, `let`, and `const` to declare variables. An equal sign (`=`) is used to assign values to these variables.

### Example
```javascript
let x; // Declaring a variable
x = 6; // Assigning the value 6 to x
```

---

## JavaScript Operators

JavaScript uses **arithmetic operators** (`+`, `-`, `*`, `/`) to compute values:

### Example
```javascript
(5 + 6) * 10 // Evaluates to 110
```

Additionally, JavaScript uses an **assignment operator** (`=`) to assign values to variables.

### Example
```javascript
let x, y;
x = 5; // x now holds the value 5
y = 6; // y now holds the value 6
```

### Analogy
Imagine you have a calculator (JavaScript) and numbers (values). The operators are like buttons on the calculator that help you perform operations to get results.

---

## JavaScript Expressions

An **expression** is a combination of values, variables, and operators, which computes to a value. This process is called **evaluation**.

### Example
```javascript
5 * 10 // Evaluates to 50
x * 10 // Evaluates using the value of x
```

Values can also be strings:
```javascript
"John" + " " + "Doe" // Evaluates to "John Doe"
```

### Analogy
Think of an expression as a recipe. The ingredients (values) and the cooking methods (operators) come together to create a delicious dish (result).

---

## JavaScript Keywords

JavaScript keywords are used to identify actions to be performed. 

### Example
The `let` keyword tells the browser to create variables:
```javascript
let x, y;
x = 5 + 6; // 11
y = x * 10; // 110
```

The `var` keyword also tells the browser to create variables but is generally less recommended for modern coding.

### Analogy
Keywords in programming are like verbs in a sentence. They indicate the actions that should be taken.

---

## JavaScript Comments

Not all JavaScript statements are executed. 

Code after double slashes `//` or between `/*` and `*/` is treated as a comment and ignored:

### Example
```javascript
let x = 5;   // This will be executed
// x = 6;   // This will NOT be executed
```

### Analogy
Comments are like footnotes in a book. They provide additional information without affecting the main content.

---

## JavaScript Identifiers / Names

Identifiers are JavaScript names used to name variables, keywords, and functions. The rules for legal names are similar across most programming languages.

A JavaScript name must begin with:

- A letter (A-Z or a-z)
- A dollar sign (`$`)
- An underscore (`_`)

Subsequent characters may be letters, digits, underscores, or dollar signs. Importantly, numbers cannot be the first character.

### Analogy
Think of identifiers as labels on storage boxes. They help you identify what's inside without opening them.

---

## JavaScript is Case Sensitive

All JavaScript identifiers are case sensitive. 

### Example
The variables `lastName` and `lastname` are two different variables:
```javascript
let lastname, lastName;
lastName = "Doe";
lastname = "Peterson";
```

JavaScript does not interpret `LET` or `Let` as the keyword `let`.

### Analogy
Case sensitivity is like the difference between uppercase and lowercase letters in a password. Both forms are recognized as distinct.

---

## JavaScript and Camel Case

Historically, programmers have used different ways of joining multiple words into one variable name:

- **Hyphens** (not allowed): `first-name`, `last-name`
- **Underscore**: `first_name`, `last_name`
- **Upper Camel Case (Pascal Case)**: `FirstName`, `LastName`
- **Lower Camel Case** (most common): `firstName`, `lastName`

### Analogy
Camel case is like creating a name tag with multiple words. Instead of spaces, you capitalize the first letter of each word to keep it neat and readable.

---

## JavaScript Character Set

JavaScript uses the **Unicode** character set, which covers (almost) all characters, punctuations, and symbols in the world.

### Analogy
Think of Unicode as a giant library where every possible character is stored. You can find any character you need, no matter how unique or obscure.

---

## Conclusion

Understanding JavaScript syntax is essential for any aspiring frontend developer. It provides the foundation upon which you can build more complex applications. By using analogies, we can relate technical concepts to everyday experiences, making learning more accessible and enjoyable.

---

# JavaScript Comments

In programming, **comments** are like sticky notes you leave for yourself or others. They help explain what the code does, make it easier to read, and are ignored when the code runs. Think of them as instructions that only humans can see.

JavaScript comments are incredibly helpful when you or someone else revisits the code after a while. It's like leaving clues on how the code works, without altering its execution.

## Single Line Comments

A **single-line comment** in JavaScript starts with `//`. Everything written after the `//` on that line will be ignored by JavaScript, just like how you can skip reading the fine print if it doesn't change the main story.

### Example:

```javascript
// Change the heading:
document.getElementById("myH").innerHTML = "My First Page";

// Change the paragraph:
document.getElementById("myP").innerHTML = "My first paragraph.";
```

In this example, the comments (`// Change the heading`) are notes explaining what the code does. JavaScript will skip over those comments when it runs the code, but they are there to remind us of the purpose of the code.

### Another Example:

You can also add comments at the end of a line to explain what's happening:

```javascript
let x = 5;      // Declare x and assign it the value of 5
let y = x + 2;  // Declare y and assign it the value of x + 2
```

Here, the comments are like small labels you attach to each step, ensuring anyone reading the code understands why these variables were set up the way they were.

## Multi-line Comments

Sometimes you need a bigger sticky note — a **multi-line comment**. These start with `/*` and end with `*/`. Everything between those symbols is ignored by JavaScript, even if it spans multiple lines. Think of it as taping a whole paragraph of explanation onto your code.

### Example:

```javascript
/*
The code below will change
the heading with id = "myH"
and the paragraph with id = "myP"
in my web page.
*/
document.getElementById("myH").innerHTML = "My First Page";
document.getElementById("myP").innerHTML = "My first paragraph.";
```

In this case, the comment is a longer explanation about what the code will do. It’s like giving detailed instructions for someone who’s going to read and understand your code.

## Using Comments to Prevent Execution

When testing or debugging, you might want to temporarily "turn off" a piece of code without deleting it. Comments can help with this! By adding `//` at the beginning of a line of code, you turn it into a comment, and JavaScript will no longer execute that line. This is like putting the code on pause.

### Example:

```javascript
//document.getElementById("myH").innerHTML = "My First Page";
document.getElementById("myP").innerHTML = "My first paragraph.";
```

Here, the first line has been commented out, so only the second line will run. This is useful when you want to see how your page behaves without a certain piece of code, without permanently removing it.

### Preventing Multiple Lines from Executing

You can use a **multi-line comment** to prevent several lines of code from executing. It’s like putting multiple things on hold at once.

### Example:

```javascript
/*
document.getElementById("myH").innerHTML = "My First Page";
document.getElementById("myP").innerHTML = "My first paragraph.";
*/
```

In this case, none of the code between `/*` and `*/` will run. This is useful when you're trying to troubleshoot or experiment with other parts of the code.

---

## Key Takeaways:
- **Single-line comments**: Use `//` to add a short note on a single line.
- **Multi-line comments**: Use `/* ... */` to block out a section of code or leave longer explanations.
- **Prevent execution**: Use comments to temporarily stop a line or section of code from running during tests.

Just like a well-organized workspace with sticky notes and labels, comments help keep your code clean and understandable — for you and for anyone else working with it.

---

# JavaScript Variables

## Variables are Containers for Storing Data

Think of a JavaScript variable as a **box** where you can store different types of items, like numbers, text, or even other boxes. The key is knowing which box holds what item and using the right box at the right time.

In JavaScript, there are different ways to create these "boxes" (variables), and choosing the right one is important for how the program works.

### Ways to Declare Variables in JavaScript

1. **Automatically**: JavaScript is flexible and will sometimes create the box for you, but it's better to be clear and tell it exactly what you want.

    ```javascript
    x = 5;
    y = 6;
    z = x + y;
    ```

    Here, `x`, `y`, and `z` are automatically created by JavaScript. But it’s like getting a box without labeling it – things could get messy!

2. **Using `var`**: This is the older way to declare a variable, like giving a box a name.

    ```javascript
    var x = 5;
    var y = 6;
    var z = x + y;
    ```

    **Note**: `var` was the standard for years, but it has quirks that can lead to unexpected results. It’s like using an old label maker that sometimes gives you the wrong label.

3. **Using `let`**: This is the modern way to declare variables. It’s like getting a fresh, clearly labeled box.

    ```javascript
    let x = 5;
    let y = 6;
    let z = x + y;
    ```

4. **Using `const`**: This is like a box you seal shut – you can never change what's inside.

    ```javascript
    const x = 5;
    const y = 6;
    const z = x + y;
    ```

    Once `x` and `y` are set with `const`, they stay that way. It's like writing with a permanent marker on your box – no erasing or changing.

### Mixed Example

```javascript
const price1 = 5;
const price2 = 6;
let total = price1 + price2;
```

In this case, `price1` and `price2` are constant, so their values can't change. `total`, however, is flexible, and its value can change as needed.

---

## When to Use `var`, `let`, or `const`

- **Always declare variables**: Be clear about what you're doing. Don't let JavaScript guess.
- **Use `const`** when you want something that won’t change, like constants in a math equation.
- **Use `let`** when the value might change, but you still want control over when and how.
- **Use `var`** only if you're working with old code or browsers.

---

## Analogies for Better Understanding

- **Just Like Algebra**: If you've ever solved an equation like `x + 5 = 10`, you know that `x` is just a placeholder for a value. JavaScript variables work the same way:

    ```javascript
    let x = 5;
    let y = 6;
    let z = x + y;
    ```

    Here, `z` equals 11 because we’re adding the values of `x` and `y`. Variables act like placeholders or boxes that hold numbers or text.

- **JavaScript Identifiers**: Just like people have names to identify them, JavaScript variables need names too. These names are called **identifiers**, and they must follow certain rules:

    - Names can include letters, digits, underscores (`_`), and dollar signs (`$`).
    - Names must begin with a letter (or `$` or `_`).
    - Names are case-sensitive (e.g., `x` and `X` are different).
    - Reserved words (like `function` or `let`) can’t be used as variable names.

---

## The Assignment Operator

In JavaScript, the `=` is not the same as the equal sign in math. It’s more like an arrow that **assigns** a value:

```javascript
x = x + 5;
```

This is saying: "Take the current value of `x`, add 5 to it, and store the result back into `x`." In other words, it updates the box.

- **Note**: If you want to check if two things are equal, use `==` or `===`.

---

## JavaScript Data Types

- **Numbers**: These are values like `100` or `3.14`.
- **Strings**: These are text values, enclosed in quotes, like `"John Doe"` or `'Hello, world!'`.

    ```javascript
    const pi = 3.14;
    let person = "John Doe";
    let answer = 'Yes I am!';
    ```

---

## Declaring a Variable

To create a box (declare a variable), use `var`, `let`, or `const`:

```javascript
let carName = "Volvo";
```

Now, the box labeled `carName` holds the value `"Volvo"`. This value can later be displayed in your webpage, like this:

```javascript
document.getElementById("demo").innerHTML = carName;
```

---

## One Statement, Many Variables

You can create multiple boxes at once, like this:

```javascript
let person = "John Doe", carName = "Volvo", price = 200;
```

Or, if you prefer:

```javascript
let person = "John Doe",
    carName = "Volvo",
    price = 200;
```

---

## Value = Undefined

If you declare a variable but don't give it a value, it will be **undefined**. It's like an empty box:

```javascript
let carName;
```

---

## Re-Declaring Variables

If you use `var`, you can re-declare the same variable without losing its value:

```javascript
var carName = "Volvo";
var carName;
```

However, with `let` or `const`, re-declaring is not allowed.

---

## JavaScript Arithmetic and Strings

Just like in algebra, you can do arithmetic with JavaScript variables:

```javascript
let x = 5 + 2 + 3;
```

You can also add strings, but they will be **concatenated** (joined together):

```javascript
let x = "John" + " " + "Doe";
```

If you mix numbers and strings, the numbers will turn into strings and get concatenated too:

```javascript
let x = "5" + 2 + 3;  // x will be "523"
```

---

## The Dollar Sign ($) and Underscore (_)

In JavaScript, both `$` and `_` can be used in variable names, although it's not common practice.

```javascript
let $ = "Hello World";
let _lastName = "Johnson";
```

These symbols are sometimes used by professional developers in libraries like jQuery, where `$` is an alias for selecting elements.

---

# JavaScript Let

The `let` keyword was introduced in ES6 (2015). It is a modern way to declare variables in JavaScript, and it comes with a few important features that help avoid common pitfalls encountered with older declarations.

## Key Features of `let`

- **Block Scope**: Variables declared with `let` have **Block Scope**, meaning they are only accessible within the nearest enclosing `{}` block.
- **Declaration Before Use**: Variables declared with `let` must be declared before they are used.
- **Cannot be Redeclared**: Variables declared with `let` cannot be redeclared in the same scope.

### Block Scope

Before ES6, JavaScript only had **Global Scope** and **Function Scope**. With ES6, two new keywords were introduced: `let` and `const`, both of which provide **Block Scope**.

#### Example:

```javascript
{
  let x = 2;
}
// x can NOT be used here
```

### Global Scope

Variables declared with `var` always have **Global Scope** and can be accessed from outside the block.

#### Example:

```javascript
{
  var x = 2;
}
// x CAN be used here
```

### Cannot be Redeclared

When using `let`, you cannot accidentally redeclare a variable.

#### With `let`, you cannot do this:

```javascript
let x = "John Doe";
let x = 0; // This will cause an error
```

#### But with `var`, you can:

```javascript
var x = "John Doe";
var x = 0; // This is allowed
```

### Redeclaring Variables

Redeclaring a variable using `var` can lead to unexpected behavior. For example:

```javascript
var x = 10; // Here x is 10

{
  var x = 2; // Here x is 2
}

// Here x is 2
```

Using `let`, redeclaring a variable inside a block will not affect the variable outside the block:

```javascript
let x = 10; // Here x is 10

{
  let x = 2; // Here x is 2
}

// Here x is still 10
```

### Difference Between `var`, `let`, and `const`

| Keyword | Scope       | Redeclare | Reassign | Hoisted | Binds this |
|---------|-------------|-----------|----------|---------|------------|
| var     | No          | Yes       | Yes      | Yes     | Yes        |
| let     | Yes         | No        | Yes      | No      | No         |
| const   | Yes         | No        | No       | No      | No         |

### What is Good?

- `let` and `const` have **Block Scope**.
- `let` and `const` cannot be redeclared.
- They must be declared before use.
- They do not bind to `this`.
- They are not hoisted.

### What is Not Good?

- `var` does not have to be declared.
- `var` is hoisted, meaning it can be used before it is declared.
- `var` binds to `this`.

### Browser Support

The `let` and `const` keywords are not supported in Internet Explorer 11 or earlier. Here are the first browser versions with full support:

| Browser  | Version | Release Date |
|----------|---------|--------------|
| Chrome   | 49      | Mar, 2016    |
| Edge     | 12      | Jul, 2015    |
| Firefox   | 36      | Jan, 2015    |
| Safari   | 11      | Sep, 2017    |
| Opera    | 36      | Mar, 2016    |

### Redeclaring

Redeclaring a variable with `var` is allowed anywhere in a program:

```javascript
var x = 2; // Now x is 2
var x = 3; // Now x is 3
```

With `let`, redeclaring a variable in the same block is NOT allowed:

```javascript
var x = 2; // Allowed
let x = 3; // Not allowed

{
  let x = 2; // Allowed
  let x = 3; // Not allowed
}
```

However, redeclaring a variable with `let` in another block IS allowed:

```javascript
let x = 2; // Allowed

{
  let x = 3; // Allowed
}

{
  let x = 4; // Allowed
}
```

### Let Hoisting

Variables defined with `var` are hoisted to the top and can be initialized at any time, meaning you can use the variable before it is declared:

```javascript
carName = "Volvo"; // This is OK
var carName;
```

On the other hand, variables defined with `let` are also hoisted to the top of the block but not initialized. Thus, using a `let` variable before it is declared will result in a `ReferenceError`:

```javascript
carName = "Saab"; // This will cause a ReferenceError
let carName = "Volvo";
```

## Conclusion

Understanding the differences between `var`, `let`, and `const` is essential for writing clean and bug-free JavaScript code. Using `let` and `const` helps prevent errors related to variable redeclaration and scope, making your code more robust.

---

# JavaScript Const

The `const` keyword was introduced in ES6 (2015) to define variables that are meant to remain constant throughout the program.

## Key Features of const

1. **Cannot be Redeclared**  
   Variables defined with `const` cannot be redeclared within the same scope.

2. **Cannot be Reassigned**  
   Variables defined with `const` cannot be reassigned after their initial assignment.

3. **Block Scope**  
   Variables defined with `const` have block scope, meaning they are only accessible within the block they are declared in.

---

## 1. Cannot be Reassigned

Once a variable is defined with the `const` keyword, you cannot change its value.  

### Example
```javascript
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```

### Analogy
Imagine you have a trophy that you won in a competition (the `const` variable). Once you have that trophy, you cannot trade it for a different one (reassign). It’s yours to keep as a symbol of your achievement.

---

## 2. Must be Assigned

JavaScript `const` variables must be assigned a value at the time of declaration.

### Correct
```javascript
const PI = 3.14159265359;
```

### Incorrect
```javascript
const PI; // SyntaxError
PI = 3.14159265359; // Not allowed
```

### Analogy
Think of `const` as a gift. You can’t just wrap an empty box and call it a gift; you need to fill it with something (assign a value) at the moment of wrapping (declaration).

---

## 3. When to use JavaScript const?

Always declare a variable with `const` when you know that the value should not be changed. Use `const` when you declare:

- A new Array
- A new Object
- A new Function
- A new RegExp

### Analogy
Imagine you’re planting a tree (your `const` variable). Once you decide what type of tree it will be (the value), you shouldn’t change it to another type after it has been planted.

---

## Constant Objects and Arrays

The keyword `const` can be a bit misleading. It does not define a constant value but rather a constant reference to a value.

### You cannot:
- Reassign a constant value
- Reassign a constant array
- Reassign a constant object

### But you can:
- Change the elements of a constant array
- Change the properties of a constant object

### Example of Constant Arrays
```javascript
const cars = ["Saab", "Volvo", "BMW"];

// You can change an element:
cars[0] = "Toyota";

// You can add an element:
cars.push("Audi");
```

#### But you cannot reassign the array:
```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"]; // ERROR
```

### Analogy
Think of a `const` array as a toolbox (the reference). You can change the tools inside the box (the elements) but cannot change the box itself for another toolbox (reassign).

---

## Constant Objects

You can change the properties of a constant object:

### Example
```javascript
const car = {type: "Fiat", model: "500", color: "white"};

// You can change a property:
car.color = "red";

// You can add a property:
car.owner = "Johnson";
```

### But you cannot reassign the object:
```javascript
const car = {type: "Fiat", model: "500", color: "white"};
car = {type: "Volvo", model: "EX60", color: "red"}; // ERROR
```

### Analogy
Consider a `const` object like a family photo album (the reference). You can add or change photos (the properties) inside it but you cannot swap out the entire album for a different one (reassign).

---

## Difference Between var, let, and const

| Scope   | Redeclare | Reassign | Hoisted | Binds this |
|---------|-----------|----------|---------|------------|
| var     | No        | Yes      | Yes     | Yes        |
| let     | Yes       | No       | Yes     | No         |
| const   | Yes       | No       | No      | No         |

### What is Good?
- `let` and `const` have block scope.
- `let` and `const` cannot be redeclared.
- `let` and `const` must be declared before use.
- `let` and `const` do not bind to `this`.
- `let` and `const` are not hoisted.

### What is Not Good?
- `var` does not have to be declared.
- `var` is hoisted.
- `var` binds to `this`.

---

## Browser Support

The `let` and `const` keywords are not supported in Internet Explorer 11 or earlier. The following table defines the first browser versions with full support:

| Browser   | Version   | Release Date   |
|-----------|-----------|-----------------|
| Chrome    | 49        | Mar, 2016       |
| Edge      | 12        | Jul, 2015       |
| Firefox   | 36        | Jan, 2015       |
| Safari    | 11        | Sep, 2017       |
| Opera     | 36        | Mar, 2016       |

---

## Block Scope

Declaring a variable with `const` is similar to `let` regarding block scope.

### Example
```javascript
const x = 10;
// Here x is 10

{
  const x = 2;
  // Here x is 2
}

// Here x is 10
```

### Analogy
Imagine you are in a room (the block). The rules inside the room (the scope) are different from the rules outside. What happens inside stays inside; the outside world doesn’t know about it.

---

## Redeclaring

Redeclaring a JavaScript `var` variable is allowed anywhere in a program.

### Example
```javascript
var x = 2;     // Allowed
var x = 3;     // Allowed
x = 4;         // Allowed
```

Redeclaring an existing `var` or `let` variable to `const`, in the same scope, is not allowed:

### Example
```javascript
var x = 2;     // Allowed
const x = 2;   // Not allowed
```

### Analogy
This is like trying to change a permanent marker's writing on a whiteboard (redeclaration of `const`). You can write as much as you want (use `var`), but once you've made a statement with a permanent marker (used `const`), you cannot erase it or write over it in the same spot.

---

## Hoisting

Variables defined with `var` are hoisted to the top and can be initialized at any time, meaning you can use the variable before it is declared:

### Example
```javascript
carName = "Volvo";
var carName; // This is OK
```

Variables defined with `const` are also hoisted to the top, but not initialized, which means using a `const` variable before it is declared will result in a `ReferenceError`:

### Example
```javascript
alert(carName); // ReferenceError
const carName = "Volvo";
```

### Analogy
Imagine hoisting as a magic trick where the name tag (variable) is brought to the front of the stage (top of the scope). When using `var`, the name is just there waiting to be filled in, while `const` requires you to fill it in first before anyone can call out the name.

---

# JavaScript Operators

JavaScript operators are used to perform different types of mathematical and logical computations, much like tools in a toolbox that help you build and fix things. 

## Examples

- The **Assignment Operator** `=` assigns values
- The **Addition Operator** `+` adds values
- The **Multiplication Operator** `*` multiplies values
- The **Comparison Operator** `>` compares values

---

## JavaScript Assignment

The Assignment Operator (`=`) assigns a value to a variable, like giving a name tag to a box so you know what’s inside.

### Assignment Examples

```javascript
let x = 10; // We have a box named 'x' that contains the value 10
// Assign the value 5 to x
x = 5; // Now the box 'x' contains the value 5
// Assign the value 2 to y
let y = 2; // We have another box named 'y' with value 2
// Assign the value x + y to z
let z = x + y; // Box 'z' now contains the value 7 (5 + 2)
```

---

## JavaScript Addition

The Addition Operator (`+`) adds numbers, just like combining apples and oranges into one basket.

### Adding

```javascript
let x = 5; // 5 apples
let y = 2; // 2 oranges
let z = x + y; // We now have 7 fruits in total
```

---

## JavaScript Multiplication

The Multiplication Operator (`*`) multiplies numbers, similar to finding out how many pieces of fruit are in several baskets.

### Multiplying

```javascript
let x = 5; // 5 baskets
let y = 2; // Each basket has 2 pieces of fruit
let z = x * y; // We have 10 pieces of fruit in total
```

---

## Types of JavaScript Operators

There are different types of JavaScript operators, much like different categories of tools:

- **Arithmetic Operators**
- **Assignment Operators**
- **Comparison Operators**
- **String Operators**
- **Logical Operators**
- **Bitwise Operators**
- **Ternary Operators**
- **Type Operators**

---

## JavaScript Arithmetic Operators

Arithmetic Operators are used to perform arithmetic on numbers, like a calculator.

### Arithmetic Operators Example

```javascript
let a = 3; // Base number
let x = (100 + 50) * a; // (150) * 3 = 450
```

| Operator | Description                           |
|----------|---------------------------------------|
| `+`      | Addition                              |
| `-`      | Subtraction                           |
| `*`      | Multiplication                        |
| `**`     | Exponentiation (ES2016)              |
| `/`      | Division                              |
| `%`      | Modulus (Division Remainder)         |
| `++`     | Increment                             |
| `--`     | Decrement                             |

*Note: Arithmetic operators are fully described in the JS Arithmetic chapter.*

---

## JavaScript Assignment Operators

Assignment operators assign values to JavaScript variables, like adding ingredients to a recipe.

### Assignment

```javascript
let x = 10; // Starting amount
x += 5; // Add 5 to the current amount of x (x = x + 5)
```

| Operator | Example   | Same As       |
|----------|-----------|---------------|
| `=`      | `x = y`   | `x = y`       |
| `+=`     | `x += y`  | `x = x + y`   |
| `-=`     | `x -= y`  | `x = x - y`   |
| `*=`     | `x *= y`  | `x = x * y`   |
| `/=`     | `x /= y`  | `x = x / y`   |
| `%=`     | `x %= y`  | `x = x % y`   |
| `**=`    | `x **= y` | `x = x ** y`  |

*Note: Assignment operators are fully described in the JS Assignment chapter.*

---

## JavaScript Comparison Operators

Comparison Operators compare values, similar to a judge evaluating different entries in a competition.

| Operator | Description                           |
|----------|---------------------------------------|
| `==`     | equal to                              |
| `===`    | equal value and equal type           |
| `!=`     | not equal                             |
| `!==`    | not equal value or not equal type    |
| `>`      | greater than                          |
| `<`      | less than                             |
| `>=`     | greater than or equal to              |
| `<=`     | less than or equal to                |
| `?`      | ternary operator                      |

*Note: Comparison operators are fully described in the JS Comparisons chapter.*

---

## JavaScript String Comparison

All the comparison operators can also be used on strings, like sorting names in alphabetical order.

### Example

```javascript
let text1 = "A"; // First name
let text2 = "B"; // Second name
let result = text1 < text2; // true, because "A" comes before "B"
```

Strings are compared alphabetically, so "20" is less than "5" because it compares character by character.

### Example

```javascript
let text1 = "20"; // String "20"
let text2 = "5";  // String "5"
let result = text1 < text2; // false
```

---

## JavaScript String Addition

The `+` operator can also be used to concatenate strings, similar to joining two pieces of rope.

### Example

```javascript
let text1 = "John"; // First name
let text2 = "Doe";  // Last name
let text3 = text1 + " " + text2; // "John Doe"
```

The `+=` operator can also concatenate strings:

```javascript
let text1 = "What a very ";
text1 += "nice day"; // "What a very nice day"
```

---

## Adding Strings and Numbers

Adding two numbers returns the sum, but adding a number and a string will return a string, like mixing paint colors.

### Example

```javascript
let x = 5 + 5;       // 10
let y = "5" + 5;     // "55"
let z = "Hello" + 5; // "Hello5"
```

If you add a number and a string, the result will be a string!

---

## JavaScript Logical Operators

Logical operators are like the conditions you set for a game, determining whether a move is valid.

| Operator | Description                           |
|----------|---------------------------------------|
| `&&`     | logical and                          |
| `||`     | logical or                           |
| `!`      | logical not                          |

*Note: Logical operators are fully described in the JS Comparisons chapter.*

---

## JavaScript Type Operators

Type operators help identify what kind of data you're dealing with, much like labeling different boxes.

| Operator       | Description                                   |
|----------------|-----------------------------------------------|
| `typeof`       | Returns the type of a variable                |
| `instanceof`   | Returns true if an object is an instance of an object type |

*Note: Type operators are fully described in the JS Type Conversion chapter.*

---

## JavaScript Bitwise Operators

Bitwise operators work on 32-bit numbers, manipulating data at the binary level, like turning on and off switches.

| Operator | Description             | Example        | Result | Decimal |
|----------|-------------------------|----------------|--------|---------|
| `&`      | AND                     | `5 & 1`        | `0001` | 1       |
| `|`      | OR                      | `5 | 1`        | `0101` | 5       |
| `~`      | NOT                     | `~ 5`          | `1010` | -6      |
| `^`      | XOR                     | `5 ^ 1`        | `0100` | 4       |
| `<<`     | left shift              | `5 << 1`       | `1010` | 10      |
| `>>`     | right shift             | `5 >> 1`       | `0010` | 2       |
| `>>>`    | unsigned right shift     | `5 >>> 1`      | `0010` | 2       |

*Note: Bitwise operators are fully described in the JS Bitwise chapter.*

---

# JavaScript Arithmetic

## JavaScript Arithmetic Operators

Arithmetic operators perform arithmetic on numbers (literals or variables). Think of these operators as different tools in a toolbox, each designed to perform a specific mathematical task. 

| Operator | Description                      |
|----------|----------------------------------|
| `+`      | Addition                         |
| `-`      | Subtraction                      |
| `*`      | Multiplication                   |
| `**`     | Exponentiation (ES2016)         |
| `/`      | Division                         |
| `%`      | Modulus (Remainder)             |
| `++`     | Increment                        |
| `--`     | Decrement                        |

## Arithmetic Operations

A typical arithmetic operation operates on two numbers. You can think of this as a recipe that combines two ingredients to create a dish.

The two numbers can be literals:

```javascript
let x = 100 + 50; // Using literal values
```

Or variables:

```javascript
let a = 20;
let b = 30;
let x = a + b; // Using variables
```

Or expressions:

```javascript
let x = (100 + 50) * a; // Using an expression
```

## Operators and Operands

The numbers in an arithmetic operation are called **operands**. The operation performed between these operands is defined by an **operator**. Think of operands as the ingredients and operators as the instructions on how to mix those ingredients.

```
Operand	Operator	Operand
100	    +	    50
```

### Adding

The addition operator (`+`) adds numbers together. It's like combining two fruits to make a fruit salad:

```javascript
let x = 5;
let y = 2;
let z = x + y; // z is now 7
```

### Subtracting

The subtraction operator (`-`) subtracts numbers. Think of it as taking one item away from a group:

```javascript
let x = 5;
let y = 2;
let z = x - y; // z is now 3
```

### Multiplying

The multiplication operator (`*`) multiplies numbers. Imagine you have several baskets, and each basket has the same number of apples:

```javascript
let x = 5;
let y = 2;
let z = x * y; // z is now 10
```

### Dividing

The division operator (`/`) divides numbers. Picture slicing a cake into equal pieces:

```javascript
let x = 5;
let y = 2;
let z = x / y; // z is now 2.5
```

### Remainder

The modulus operator (`%`) returns the remainder of a division. It's like figuring out how many full baskets of fruit you can make, and how many are left over:

```javascript
let x = 5;
let y = 2;
let z = x % y; // z is now 1
```

In arithmetic, dividing two integers produces a quotient and a remainder. In mathematics, the result of a modulo operation is the remainder from a division.

### Incrementing

The increment operator (`++`) increases a number by one. Think of it as adding one more cookie to your cookie jar:

```javascript
let x = 5;
x++; // x is now 6
```

### Decrementing

The decrement operator (`--`) decreases a number by one. Imagine taking one cookie out of your jar:

```javascript
let x = 5;
x--; // x is now 4
```

### Exponentiation

The exponentiation operator (`**`) raises the first operand to the power of the second operand. It’s like planting a seed that grows into a tree, which then produces more seeds:

```javascript
let x = 5;
let z = x ** 2; // z is now 25
```

This can also be expressed using the `Math.pow` function:

```javascript
let z = Math.pow(x, 2); // z is now 25
```

## Operator Precedence

Operator precedence describes the order in which operations are performed in an arithmetic expression. This is like having a set of rules for which tasks to complete first in a recipe.

```javascript
let x = 100 + 50 * 3; // Is the result equal to 150 * 3, or 100 + 150?
```

Just like in school mathematics, multiplication is done first. The multiplication (`*`) and division (`/`) operators have a higher precedence than addition (`+`) and subtraction (`-`).

You can change the precedence by using parentheses:

```javascript
let x = (100 + 50) * 3; // Here, the addition is done first
```

When many operations have the same precedence (like addition and subtraction, or multiplication and division), they are computed from left to right:

```javascript
let x = 100 + 50 - 3; // Adds first, then subtracts
let x = 100 / 50 * 3; // Divides first, then multiplies
```

## Notes

For a full list of operator precedence values, visit [JavaScript Operator Precedence Values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence).

---

# JavaScript Assignment

## JavaScript Assignment Operators

Assignment operators assign values to JavaScript variables. Think of them as a way to set up your workspace by giving each tool (variable) a specific value.

| Operator | Example      | Same As       |
|----------|--------------|---------------|
| =        | `x = y`     | `x = y`       |
| +=       | `x += y`    | `x = x + y`   |
| -=       | `x -= y`    | `x = x - y`   |
| *=       | `x *= y`    | `x = x * y`   |
| /=       | `x /= y`    | `x = x / y`   |
| %=       | `x %= y`    | `x = x % y`   |
| **=      | `x **= y`   | `x = x ** y`  |

### Shift Assignment Operators

These operators are like moving items left or right on a shelf. You’re just changing their positions.

| Operator | Example      | Same As       |
|----------|--------------|---------------|
| <<=      | `x <<= y`    | `x = x << y`  |
| >>=      | `x >>= y`    | `x = x >> y`  |
| >>>=     | `x >>>= y`   | `x = x >>> y` |

### Bitwise Assignment Operators

These operators perform bit-level operations, similar to flipping switches on a control panel.

| Operator | Example      | Same As       |
|----------|--------------|---------------|
| &=       | `x &= y`     | `x = x & y`   |
| ^=       | `x ^= y`     | `x = x ^ y`   |
| |=       | `x |= y`     | `x = x | y`   |

### Logical Assignment Operators

Think of these operators as making decisions. They decide whether to keep the current value or update it based on conditions.

| Operator | Example      | Same As                 |
|----------|--------------|-------------------------|
| &&=      | `x &&= y`    | `x = x && (x = y)`     |
| ||=      | `x ||= y`    | `x = x || (x = y)`     |
| ??=      | `x ??= y`    | `x = x ?? (x = y)`     |

> **Note:** The Logical assignment operators are a feature introduced in ES2020.

## The `=` Operator

The simple assignment operator assigns a value to a variable. Imagine labeling a box with its contents.

### Simple Assignment Examples
```javascript
let x = 10; // Box labeled 'x' with value 10
let y = 5;  // Box labeled 'y' with value 5
let z = x + y; // Box 'z' now contains the sum of 'x' and 'y'
```

## The `+=` Operator

The addition assignment operator adds a value to a variable. Picture it as adding more items to an already filled box.

### Addition Assignment Examples
```javascript
let x = 10; // Box 'x' contains 10
x += 5;     // Now box 'x' contains 15 (10 + 5)
let text = "Hello"; 
text += " World"; // Now box 'text' contains "Hello World"
```

## The `-=` Operator

The subtraction assignment operator subtracts a value from a variable. It's like removing some items from a box.

### Subtraction Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x -= 5;     // Now box 'x' contains 5 (10 - 5)
```

## The `*=` Operator

The multiplication assignment operator multiplies a variable. Imagine duplicating the contents of a box several times.

### Multiplication Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x *= 5;     // Now box 'x' contains 50 (10 * 5)
```

## The `**=` Operator

The exponentiation assignment operator raises a variable to the power of the operand. Think of it as a box that grows exponentially with each use.

### Exponentiation Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x **= 2;    // Now box 'x' contains 100 (10^2)
```

## The `/=` Operator

The division assignment operator divides a variable. This is like sharing the contents of a box among several others.

### Division Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x /= 5;     // Now box 'x' contains 2 (10 / 5)
```

## The `%=` Operator

The remainder assignment operator assigns a remainder to a variable. Imagine splitting candies and keeping the leftovers.

### Remainder Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x %= 3;     // Now box 'x' contains 1 (10 % 3)
```

## The `<<=` Operator

The left shift assignment operator shifts the bits of a variable to the left. Picture it as moving items further down a shelf.

### Left Shift Assignment Example
```javascript
let x = -100; // Box 'x' contains -100
x <<= 5;      // Now box 'x' is shifted left (multiplied by 2^5)
```

## The `>>=` Operator

The right shift assignment operator shifts the bits of a variable to the right. Think of it as moving items closer to the edge of a shelf.

### Right Shift Assignment Example
```javascript
let x = -100; // Box 'x' contains -100
x >>= 5;      // Now box 'x' is shifted right (divided by 2^5)
```

## The `>>>=` Operator

The unsigned right shift assignment operator shifts the bits of a variable to the right without keeping the sign. This is like moving items without considering their original position.

### Unsigned Right Shift Assignment Example
```javascript
let x = -100; // Box 'x' contains -100
x >>>= 5;     // Now box 'x' is shifted right without sign consideration
```

## The `&=` Operator

The bitwise AND assignment operator performs a bitwise AND operation on two operands and assigns the result. This is like keeping only the items that are common between two boxes.

### Bitwise AND Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x &= 5;     // Now box 'x' contains 0 (10 & 5)
```

## The `|=` Operator

The bitwise OR assignment operator performs a bitwise OR operation on two operands and assigns the result. This is akin to combining the items from two boxes.

### Bitwise OR Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x |= 5;     // Now box 'x' contains 15 (10 | 5)
```

## The `^=` Operator

The bitwise XOR assignment operator performs a bitwise XOR operation on two operands and assigns the result. Imagine you keep only the unique items from two boxes.

### Bitwise XOR Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x ^= 5;     // Now box 'x' contains 15 (10 ^ 5)
```

## The `&&=` Operator

The logical AND assignment operator assigns the second value if the first value is true. It’s like deciding to fill a box only if it’s already occupied.

### Logical AND Assignment Example
```javascript
let x = 10; // Box 'x' contains 10
x &&= 5;    // Box 'x' remains 10 (10 && 5 is true, x doesn't change)
```

## The `||=` Operator

The logical OR assignment operator assigns the second value if the first value is false. This is like saying, "If this box is empty, put something in it."

### Logical OR Assignment Example
```javascript
let x; // Box 'x' is empty
x ||= 5; // Now box 'x' contains 5 (x was empty)
```

## The `??=` Operator

The nullish coalescing assignment operator assigns the second value if the first value is null or undefined. Think of it as filling a box with something if it has nothing in it.

### Nullish Coalescing Assignment Example
```javascript
let x; // Box 'x' is empty
x ??= 5; // Now box 'x' contains 5 (x was null/undefined)
```

> **Note:** The `??=` operator is a feature introduced in ES2020.

---

# JavaScript Data Types

JavaScript has **8 Data Types**:

1. **String**
2. **Number**
3. **BigInt**
4. **Boolean**
5. **Undefined**
6. **Null**
7. **Symbol**
8. **Object**

---

## The Object Datatype

The **Object** data type is like a versatile toolbox that can hold various tools (values) and gadgets (functions). In JavaScript, objects can include built-in types as well as user-defined objects. Here are some examples:

### Built-in Object Types
- **Objects**: Think of a toolbox containing a variety of tools.
- **Arrays**: Like a shelf that holds different items (elements) in a specific order.
- **Dates**: A calendar that helps you track time.
- **Maps/Sets**: Like labeled containers for organizing items.
- **IntArrays/FloatArrays**: Special boxes for holding numbers, either whole or with decimal points.
- **Promises**: A commitment to fulfill a task in the future.

### Examples
```javascript
// Numbers:
let length = 16;  // Length of an item in centimeters
let weight = 7.5; // Weight of the item in kilograms

// Strings:
let color = "Yellow";       // Color of the item
let lastName = "Johnson";   // Person's last name

// Booleans
let x = true;   // This value indicates 'yes'
let y = false;  // This value indicates 'no'

// Object:
const person = {firstName:"John", lastName:"Doe"}; // Represents a person with properties

// Array object:
const cars = ["Saab", "Volvo", "BMW"]; // A shelf of car names

// Date object:
const date = new Date("2022-03-25"); // A date in the calendar
```

**Note**: A JavaScript variable can hold any type of data, like a toolbox that can change its tools as needed.

---

## The Concept of Data Types

In programming, **data types** are crucial for effective operation. Knowing the type of a variable is essential because it defines how you can manipulate it. 

### Why Data Types Matter
Consider this example:

```javascript
let x = 16 + "Volvo"; // Mixing a number and a string
```

Does it make sense to add "Volvo" to the number 16? Without data types, JavaScript cannot process this safely. It will treat the above example like this:

```javascript
let x = "16" + "Volvo"; // Converts 16 into a string
```

**Note**: When adding a number and a string, JavaScript treats the number as a string.

### Sequence Matters
JavaScript evaluates expressions from left to right. Different sequences can lead to different results:

```javascript
let x = 16 + 4 + "Volvo"; // Result: "20Volvo"
let y = "Volvo" + 16 + 4; // Result: "Volvo164"
```

In the first example, JavaScript treats 16 and 4 as numbers until it reaches "Volvo". In the second, it treats everything as strings.

---

## JavaScript Types are Dynamic

JavaScript is dynamically typed, meaning you can use the same variable to hold different types of data at different times.

### Example
```javascript
let x;       // x is undefined
x = 5;       // Now x is a Number
x = "John";  // Now x is a String
```

This flexibility is like using the same backpack for different items — it can change its contents based on what you need.

---

## JavaScript Strings

A **string** is like a sentence made up of characters. Strings are enclosed in quotes, either single or double.

### Examples
```javascript
// Using double quotes:
let carName1 = "Volvo XC60";

// Using single quotes:
let carName2 = 'Volvo XC60';
```

You can use quotes inside a string, as long as they don't match the surrounding quotes:

```javascript
let answer1 = "It's alright"; // Single quote inside double quotes
let answer2 = "He is called 'Johnny'"; // Single quotes inside double quotes
let answer3 = 'He is called "Johnny"'; // Double quotes inside single quotes
```

---

## JavaScript Numbers

All JavaScript numbers are stored as decimal (floating-point) values. They can be written with or without decimals.

### Examples
```javascript
// With decimals:
let x1 = 34.00;

// Without decimals:
let x2 = 34;
```

### Exponential Notation
Extra large or small numbers can be represented in scientific notation:

```javascript
let y = 123e5;    // 12300000
let z = 123e-5;   // 0.00123
```

**Note**: JavaScript numbers are always treated as double (64-bit floating point).

---

## JavaScript BigInt

**BigInt** is a new datatype (ES2020) that allows you to store large integers that cannot be represented by a regular JavaScript Number.

### Example
```javascript
let x = BigInt("123456789012345678901234567890");
```

---

## JavaScript Booleans

**Booleans** represent truth values and can only be true or false. They are essential for making decisions in code.

### Example
```javascript
let x = 5;
let y = 5;
let z = 6;

(x == y)       // Returns true
(x == z)       // Returns false
```

---

## JavaScript Arrays

Arrays are like shelves that store a collection of items (values). They are defined with square brackets.

### Example
```javascript
const cars = ["Saab", "Volvo", "BMW"]; // A shelf of car names
```

Array items are zero-indexed, meaning the first item is at position 0.

---

## JavaScript Objects

Objects are like boxes that hold multiple related items. They are defined with curly braces `{}`.

### Example
```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
}; // A box containing properties of a person
```

---

## The typeof Operator

The `typeof` operator is a useful tool to find the type of a variable in JavaScript.

### Example
```javascript
typeof "";             // Returns "string"
typeof 0;              // Returns "number"
```

---

## Undefined

A variable without a value has the value **undefined**. 

### Example
```javascript
let car;    // Value is undefined, type is undefined
car = undefined;    // Value is still undefined
```

---

## Empty Values

An **empty value** has a legal type, while **undefined** does not. An empty string is still considered a string.

### Example
```javascript
let car = "";    // The value is "", the typeof is "string"
```

---

# JavaScript Functions

## Introduction to Functions

A JavaScript function is a block of code designed to perform a specific task. Think of a function as an appliance in your kitchen: each one has a different function, like mixing, cooking, or blending. When you need to do a task, you simply use the appropriate appliance.

### Function Execution

A JavaScript function is executed when "something" invokes (calls) it. Just like when you decide to use an appliance, you turn it on and put it to work to accomplish what you need.

### Example

```javascript
// Function to compute the product of p1 and p2
function myFunction(p1, p2) {
  return p1 * p2;
}
```

---

## JavaScript Function Syntax

A function is defined with the `function` keyword, followed by a name and then parentheses `()`. 

### Function Naming Rules

Function names can contain letters, digits, underscores, and dollar signs, following the same rules as variables.

The parameters of the function are listed inside the parentheses `()` in the function definition:

```javascript
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

Function parameters are listed inside the parentheses `()` in the function definition.

Function arguments are the values received by the function when it is invoked. Inside the function, the arguments (the parameters) act as local variables, just like having specific tools for each task.

---

## Function Invocation

The code inside the function will execute when "something" invokes it. This can happen in different scenarios:

- **When an event occurs** (when a user clicks a button).
- **When it is invoked** (called) from JavaScript code.
- **Automatically** (self-invoked).

### Invocation Example

```javascript
// The function is called, the return value will end up in x
let x = myFunction(4, 3);
```

---

## Function Return

When JavaScript reaches a `return` statement, the function will stop executing. If the function was invoked from a statement, JavaScript will return to execute the code that follows the invoking statement.

Functions often compute a return value. The return value is "returned" back to the "caller".

### Example

```javascript
function myFunction(a, b) {
  // The function returns the product of a and b
  return a * b;
}
```

---

## Why Use Functions?

Functions allow you to reuse code. You can write code that can be used multiple times, like a recipe you can follow over and over again with different ingredients (arguments) to get different results.

---

## The () Operator

The `()` operator invokes (calls) the function. It’s like pressing the start button on an appliance to make it begin working.

### Example: Convert Fahrenheit to Celsius

```javascript
function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
}

let value = toCelsius(77);
```

Accessing a function with incorrect parameters can return an incorrect answer.

### Error Example

```javascript
let value = toCelsius(); // This can cause an error because no argument was passed
```

Accessing a function without `()` returns the function itself, not the result of the function.

### Reference Example

```javascript
let value = toCelsius; // Refers to the function object, not the result
```

---

## Functions Used as Variable Values

Functions can be used like variables in formulas, assignments, and calculations. 

### Direct Use Example

Instead of using a variable to store the return value of a function:

```javascript
let x = toCelsius(77);
let text = "The temperature is " + x + " Celsius";
```

You can use the function directly as a variable value:

```javascript
let text = "The temperature is " + toCelsius(77) + " Celsius";
```

---

## Local Variables

Variables declared within a JavaScript function become LOCAL to that function. This is similar to having a workspace where only you can access your tools.

### Local Variable Example

```javascript
function myFunction() {
  let carName = "Volvo"; // Local variable
  // code here CAN use carName
}

// outside the function, you cannot use carName
```

Since local variables are only recognized inside their functions, you can use variables with the same name in different functions.

Local variables are created when a function starts and deleted when the function completes.

---

# JavaScript Objects

## Real Life Objects

In real life, objects are things like houses, cars, people, animals, or any other subjects. Just as a car has specific characteristics and functions, JavaScript objects encapsulate related data and behaviors.

### Car Object Example

| Car Object | Properties                       | Methods                      |
|------------|----------------------------------|------------------------------|
|            | car.name = Fiat                 | car.start()                  |
|            | car.model = 500                 | car.drive()                  |
|            | car.weight = 850kg              | car.brake()                  |
|            | car.color = white                | car.stop()                   |

---

## Object Properties

A real-life car has properties like weight and color:

- `car.name = Fiat`
- `car.model = 500`
- `car.weight = 850kg`
- `car.color = white`

Car objects have the same properties, but the values differ from car to car, just like how every car has its own unique specifications.

---

## Object Methods

A real-life car has methods like start and stop:

- `car.start()`
- `car.drive()`
- `car.brake()`
- `car.stop()`

Car objects have the same methods, but the methods are performed at different times, like starting your car in the morning or braking at a stoplight.

---

## JavaScript Variables

JavaScript variables are containers for data values. They are like jars where you can store ingredients to use later.

### Example

```javascript
let car = "Fiat";
```

---

## JavaScript Objects

Objects are variables too. But unlike simple variables, objects can contain many values. They can be thought of as complex jars that can hold various ingredients.

### Example

```javascript
const car = {type: "Fiat", model: "500", color: "white"};
```

**Note:** It is a common practice to declare objects with the `const` keyword for readability and to prevent accidental reassignments.

---

## JavaScript Object Definition

### How to Define a JavaScript Object

There are several ways to define a JavaScript object:

1. **Using an Object Literal**
2. **Using the new Keyword**
3. **Using an Object Constructor**

### JavaScript Object Literal

An object literal is a list of name:value pairs inside curly braces `{}`.

```javascript
{firstName: "John", lastName: "Doe", age: 50, eyeColor: "blue"}
```

**Note:** Name:value pairs are also called key:value pairs.

---

### Creating a JavaScript Object

These examples create a JavaScript object with 4 properties:

#### Example 1: Object Literal

```javascript
// Create an Object
const person = {firstName: "John", lastName: "Doe", age: 50, eyeColor: "blue"};
```

Spaces and line breaks are not important. An object initializer can span multiple lines:

#### Example 2: Multi-line Object

```javascript
// Create an Object
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

#### Example 3: Empty Object and Adding Properties

This example creates an empty JavaScript object, and then adds 4 properties:

```javascript
// Create an Object
const person = {};

// Add Properties
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

### Using the new Keyword

This example creates a new JavaScript object using `new Object()`, and then adds 4 properties:

```javascript
// Create an Object
const person = new Object();

// Add Properties
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

**Note:** The examples above do exactly the same. However, using `new Object()` is less common. For readability, simplicity, and execution speed, it's best to use the object literal method.

---

## Object Properties

The named values in JavaScript objects are called properties.

| Property    | Value  |
|-------------|--------|
| firstName   | John   |
| lastName    | Doe    |
| age         | 50     |
| eyeColor    | blue   |

Objects written as name-value pairs are similar to:

- Associative arrays in PHP
- Dictionaries in Python
- Hash tables in C
- Hash maps in Java
- Hashes in Ruby and Perl

---

## Accessing Object Properties

You can access object properties in two ways:

1. `objectName.propertyName`
2. `objectName["propertyName"]`

### Examples

```javascript
person.lastName; // Accessing using dot notation
person["lastName"]; // Accessing using bracket notation
```

---

## JavaScript Object Methods

Methods are actions that can be performed on objects. They are like buttons on a car that initiate certain actions.

### Example

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  id: 5566,
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
};
```

In the example above, `this` refers to the person object:

- `this.firstName` means the `firstName` property of `person`.
- `this.lastName` means the `lastName` property of `person`.

---

## In JavaScript, Objects are King

If you understand objects, you understand JavaScript. Objects are containers for properties and methods.

- **Properties** are named values.
- **Methods** are functions stored as properties.

Properties can be primitive values, functions, or even other objects. In JavaScript, almost everything is an object, including:

- Objects
- Math
- Functions
- Dates
- Arrays
- Maps
- Sets

All JavaScript values, except primitives, are objects.

---

## JavaScript Primitives

A primitive value is a value that has no properties or methods.

For example, `3.14` is a primitive value.

### Primitive Data Types

JavaScript defines 7 types of primitive data types:

- string
- number
- boolean
- null
- undefined
- symbol
- bigint

### Immutability of Primitives

Primitive values are immutable; they cannot be changed. 

| Value   | Type     | Comment                  |
|---------|----------|--------------------------|
| "Hello" | string   | "Hello" is always "Hello"|
| 3.14    | number   | 3.14 is always 3.14      |
| true    | boolean  | true is always true       |
| false   | boolean  | false is always false     |
| null    | null     | null is always null       |
| undefined| undefined| undefined is always undefined|

---

## JavaScript Objects are Mutable

Objects are mutable: they are addressed by reference, not by value. 

If `person` is an object, the following statement will not create a copy of `person`:

```javascript
const x = person;
```

The object `x` is not a copy of `person`; it refers to the same object. Therefore, any changes to `x` will also affect `person`:

### Example

```javascript
// Create an Object
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};

// Create a copy
const x = person;

// Change Age in both
x.age = 10; // Changes the age for both x and person
```

---

# JavaScript Object Properties

## An Object is an Unordered Collection of Properties

Imagine an object in JavaScript as a toolbox. Inside this toolbox, you have different tools (properties) that you can use. Each tool has a name (key) and a specific purpose (value). Properties are the most important part of JavaScript objects.

- **Properties:** They are like tools in the toolbox. They can be changed, added, deleted, and some are read-only.

## Accessing JavaScript Properties

The syntax for accessing the property of an object is as follows:

1. **Using Dot Notation:**

   ```javascript
   // objectName.property
   let age = person.age;
   ```

   Think of this as using a tool from your toolbox. By mentioning the name of the toolbox (object) and then the name of the tool (property), you get the tool you need.

2. **Using Bracket Notation:**

   ```javascript
   // objectName["property"]
   let age = person["age"];
   ```

   Here, you’re using a label (property name) to access the tool inside the toolbox. This is useful if the name of the tool has spaces or special characters.

3. **Using Expressions:**

   ```javascript
   // objectName[expression]
   let age = person[x];
   ```

   In this case, `x` is a variable that stores the name of the tool, allowing you to access it dynamically.

### Examples

```javascript
person.firstname + " is " + person.age + " years old."; // Dot notation
person["firstname"] + " is " + person["age"] + " years old."; // Bracket notation
let x = "firstname";
let y = "age";
person[x] + " is " + person[y] + " years old."; // Using variables
```

## Adding New Properties

You can add new properties to an existing object by simply giving it a value:

### Example

```javascript
person.nationality = "English"; // Adding a new property
```

Think of this as adding a new tool to your toolbox. Now you have more options to work with.

## Deleting Properties

The `delete` keyword is used to remove a property from an object:

### Example

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};

delete person.age; // Deleting a property
```

You can also use bracket notation:

```javascript
delete person["age"];
```

### Note:

The `delete` keyword removes both the value of the property and the property itself. After deletion, you cannot use the property until it is added back again.

## Nested Objects

Property values in an object can be other objects. This is like having tools within tools in your toolbox.

### Example

```javascript
myObj = {
  name: "John",
  age: 30,
  myCars: {
    car1: "Ford",
    car2: "BMW",
    car3: "Fiat"
  }
};
```

You can access nested objects using dot notation or bracket notation:

### Examples

```javascript
myObj.myCars.car2;           // Dot notation
myObj.myCars["car2"];       // Bracket notation
myObj["myCars"]["car2"];    // Nested access
let p1 = "myCars";
let p2 = "car2";
myObj[p1][p2];              // Using variables to access
```

## Complete Object Reference

For a complete reference, you can consult our:

### [Complete JavaScript Object Reference](#)

The reference contains descriptions and examples of all object properties and methods.

## Conclusion

Understanding how object properties work in JavaScript is essential for managing data and creating dynamic applications. As you progress in your learning, remember that objects are powerful tools in your JavaScript toolbox, ready to help you build whatever you desire.

---

# JavaScript Object Methods

## What are Object Methods?

Object methods are like actions that you can perform on objects. Imagine an object as a smartphone, and methods are the applications (apps) that perform specific tasks on that smartphone. For instance, you can use a messaging app to send messages, or a photo app to take pictures.

A method is essentially a function definition stored as a property value within the object.

### Example of an Object with Methods

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  id: 5566,
  fullName: function() {
    return this.firstName + " " + this.lastName; // Combines first and last name
  }
};
```

In this example:
- `firstName`, `lastName`, and `id` are properties of the `person` object.
- `fullName` is a method that combines the `firstName` and `lastName` properties.

### Understanding `this`

In the context of methods, `this` refers to the object on which the method is being called. 

- `this.firstName` means the `firstName` property of the `person` object.
- `this.lastName` means the `lastName` property of the `person` object.

## Accessing Object Methods

You can access an object method using the following syntax:

```javascript
objectName.methodName();
```

### Example

When you invoke the `fullName` property with parentheses, it executes as a function:

```javascript
let name = person.fullName(); // Executes the method and returns "John Doe"
```

If you access the `fullName` property without parentheses, it returns the function definition itself:

```javascript
let name = person.fullName; // Returns the function definition
```

## Adding a Method to an Object

You can easily add a new method to an existing object:

### Example

```javascript
person.name = function () {
  return this.firstName + " " + this.lastName; // Another way to get the full name
};
```

Now, the `person` object has an additional method `name` that does the same thing as `fullName`.

## Using JavaScript Methods

You can also utilize built-in JavaScript methods within your object methods. For example, you can use the `toUpperCase()` method to convert text to uppercase:

### Example

```javascript
person.name = function () {
  return (this.firstName + " " + this.lastName).toUpperCase(); // Returns "JOHN DOE"
};
```

In this case, the `name` method now returns the full name in uppercase letters.

## Conclusion

Understanding object methods in JavaScript is essential for building interactive and dynamic applications. Methods allow you to perform actions on your objects, similar to how apps function on a smartphone. As you continue your journey in JavaScript, remember that mastering methods is crucial for efficient coding and problem-solving.

---

# Displaying Objects in JavaScript

## How to Display JavaScript Objects?

When you try to display a JavaScript object directly, the result will be `[object Object]`, which is not very informative. It's like trying to describe a box without opening it: you can only see its exterior.

### Example of Creating an Object

```javascript
// Create an Object
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

// Attempt to display the object directly
document.getElementById("demo").innerHTML = person; // Result: [object Object]
```

To display an object more informatively, there are several solutions:

1. **Displaying the Object Properties by Name**
2. **Displaying the Object Properties in a Loop**
3. **Displaying the Object using `Object.values()`**
4. **Displaying the Object using `JSON.stringify()`**

## Displaying Object Properties

You can display the properties of an object as a string:

### Example

```javascript
// Create an Object
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

// Display Properties
document.getElementById("demo").innerHTML =
  person.name + ", " + person.age + ", " + person.city;
```

### Displaying Properties in a Loop

The properties of an object can be collected using a loop:

### Example

```javascript
// Create an Object
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

// Build a Text
let text = "";
for (let x in person) {
  text += person[x] + " "; // Concatenate the values
}

// Display the Text
document.getElementById("demo").innerHTML = text;
```

**Note:** You must use `person[x]` in the loop. Using `person.x` will not work because `x` is the loop variable.

## Using `Object.values()`

`Object.values()` creates an array from the property values of the object:

### Example

```javascript
// Create an Object
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

// Create an Array
const myArray = Object.values(person);

// Display the Array
document.getElementById("demo").innerHTML = myArray; // Displays: John, 30, New York
```

## Using `Object.entries()`

`Object.entries()` makes it easier to work with objects in loops:

### Example

```javascript
const fruits = { Bananas: 300, Oranges: 200, Apples: 500 };

let text = "";
for (let [fruit, value] of Object.entries(fruits)) {
  text += fruit + ": " + value + "<br>"; // Concatenate fruit name and quantity
}
```

## Using `JSON.stringify()`

JavaScript objects can be converted to a string using the JSON method `JSON.stringify()`. This method is built into JavaScript and is supported in all major browsers.

### Example

```javascript
// Create an Object
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

// Stringify Object
let myString = JSON.stringify(person); // {"name":"John","age":30,"city":"New York"}

// Display String
document.getElementById("demo").innerHTML = myString;
```

**Note:** The result will be a string written in JSON notation.

## Conclusion

Understanding how to display objects in JavaScript is essential for debugging and providing clear information to users. Whether through specific properties, loops, or methods like `Object.values()` and `JSON.stringify()`, there are multiple ways to present data effectively.

---

# JavaScript Object Constructors

## Object Constructor Functions

Sometimes we need to create many objects of the same type. To achieve this, we use an **object constructor function**. 

It is considered good practice to name constructor functions with an upper-case first letter, which helps to distinguish them from regular functions.

### Object Type: Person

```javascript
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
}
```

**Note:** In the constructor function, `this` has no value until a new object is created. The value of `this` will become the new object.

### Creating New Objects

Now we can use `new Person()` to create many new `Person` objects:

```javascript
const myFather = new Person("John", "Doe", 50, "blue");
const myMother = new Person("Sally", "Rally", 48, "green");
const mySister = new Person("Anna", "Rally", 18, "green");
const mySelf = new Person("Johnny", "Rally", 22, "green");
```

## Property Default Values

A value assigned to a property will be a default value for all objects created by the constructor:

### Example

```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
  this.nationality = "English"; // Default value
}
```

### Adding a Property to an Object

Adding a property to an object created by the constructor is straightforward:

```javascript
myFather.nationality = "English"; // Assign nationality to myFather
```

**Note:** The new property will be added to `myFather`, not to any other `Person` objects.

## Adding a Property to a Constructor

You cannot add a new property directly to an object constructor. 

### Example

```javascript
Person.nationality = "English"; // This will not work
```

To add a new property, you must add it to the constructor function prototype:

### Example

```javascript
Person.prototype.nationality = "English"; // Add nationality to prototype
```

## Constructor Function Methods

A constructor function can also have methods defined within it:

### Example

```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
  this.fullName = function() {
    return this.firstName + " " + this.lastName;
  };
}
```

### Adding a Method to an Object

You can easily add a method to a created object:

```javascript
myMother.changeName = function(name) {
  this.lastName = name; // Change last name
}
```

**Note:** The new method will be added to `myMother`, not to any other `Person` objects.

## Adding a Method to a Constructor

You cannot add a new method to an object constructor function directly. The following code will produce a `TypeError`:

### Example

```javascript
Person.changeName = function(name) {
  this.lastName = name; // This will not work
}

// Trying to use the method will cause an error
myMother.changeName("Doe"); // TypeError: myMother.changeName is not a function
```

To add a new method, it must be done to the constructor function prototype:

### Example

```javascript
Person.prototype.changeName = function(name) {
  this.lastName = name; // Change last name
}

myMother.changeName("Doe"); // Works correctly now
```

**Note:** The `changeName()` function assigns the value of `name` to the person's `lastName` property, with `this` referring to `myMother`.

## Built-in JavaScript Constructors

JavaScript has built-in constructors for all native objects:

- `new Object()`   // A new Object object
- `new Array()`    // A new Array object
- `new Map()`      // A new Map object
- `new Set()`      // A new Set object
- `new Date()`     // A new Date object
- `new RegExp()`   // A new RegExp object
- `new Function()` // A new Function object

**Note:** The `Math` object is not a constructor. `Math` is a global object, and you cannot use the `new` keyword on `Math`.

## Did You Know?

- Use object literals `{}` instead of `new Object()`.
- Use array literals `[]` instead of `new Array()`.
- Use regex literals `/()/` instead of `new RegExp()`.
- Use function expressions `() => {}` instead of `new Function()`.

### Example of Primitive Types

```javascript
"";           // primitive string
0;            // primitive number
false;        // primitive boolean

{};           // object object
[];           // array object
/()/          // regexp object
function(){}; // function
```

---

# JavaScript Events

HTML events are "things" that happen to HTML elements. When JavaScript is used in HTML pages, it can "react" to these events.

## HTML Events

An HTML event can be something the browser does or something a user does. Here are some examples of HTML events:

- An HTML web page has finished loading
- An HTML input field was changed
- An HTML button was clicked

Often, when events happen, you may want to do something. JavaScript lets you execute code when events are detected. HTML allows event handler attributes, with JavaScript code, to be added to HTML elements.

### Analogy: The Steering Wheel of a Ship

Imagine your web page is a ship sailing in the sea. The events are like waves that affect the ship's movement. When the ship faces a wave (an event), you can turn the steering wheel (execute code) to react to that wave and keep the ship on the right course.

### Example of Event Attributes

With single quotes:
```html
<element event='some JavaScript'>
```

With double quotes:
```html
<element event="some JavaScript">
```

In the following example, an `onclick` attribute (with code) is added to a `<button>` element:

#### Example 1

```html
<button onclick="document.getElementById('demo').innerHTML = Date()">What time is it?</button>
```

In the example above, the JavaScript code changes the content of the element with `id="demo"`.

#### Example 2

In the next example, the code changes the content of its own element (using `this.innerHTML`):

```html
<button onclick="this.innerHTML = Date()">What time is it?</button>
```

JavaScript code is often several lines long. It's more common to see event attributes calling functions:

#### Example 3

```html
<button onclick="displayDate()">What time is it?</button>
```

## Common HTML Events

Here is a list of some common HTML events:

| Event       | Description                                      |
|-------------|--------------------------------------------------|
| `onchange`  | An HTML element has been changed                 |
| `onclick`   | The user clicks an HTML element                  |
| `onmouseover`| The user moves the mouse over an HTML element   |
| `onmouseout`| The user moves the mouse away from an HTML element |
| `onkeydown` | The user pushes a keyboard key                   |
| `onload`    | The browser has finished loading the page        |

The list is much longer: [W3Schools JavaScript Reference HTML DOM Events](https://www.w3schools.com/jsref/dom_obj_event.asp).

### Analogy: The Controls of a Car

Imagine HTML events are like actions you take while driving a car. When you press the accelerator (event), the car reacts (executes a function) by speeding up. Similarly, when an event occurs on your web page, you can make your code react to perform a specific action.

## JavaScript Event Handlers

Event handlers can be used to handle and verify user input, user actions, and browser actions. Some of the things that can be done include:

- Actions that should be done every time a page loads
- Actions that should be performed when the page is closed
- Actions that should be executed when a user clicks a button
- Content that should be verified when a user inputs data
- And more...

### Common Methods for Working with Events in JavaScript:

- HTML event attributes can execute JavaScript code directly.
- HTML event attributes can call JavaScript functions.
- You can assign your own event handler functions to HTML elements.
- You can prevent events from being sent or being handled.
- And more...

You will learn much more about events and event handlers in the HTML DOM chapters.

---

### Conclusion

Events are fundamental for interaction on web pages. Understanding how they work and how to react to them will allow you to create more dynamic and engaging web applications.

---

# JavaScript Strings

Strings are for storing text. They are written with quotes.

## Using Quotes

A JavaScript string is zero or more characters written inside quotes.

### Example

```javascript
let text = "John Doe";
```

You can use single or double quotes:

### Example

```javascript
let carName1 = "Volvo XC60";  // Double quotes
let carName2 = 'Volvo XC60';  // Single quotes
```

**Note:** Strings created with single or double quotes work the same. There is no difference between the two.

### Analogy: A Book Cover

Think of strings as the covers of books. Just like a book can have a cover made of different materials (paper or cloth), a string can be enclosed in single or double quotes. The content inside the cover (the text) remains the same, no matter the type of cover used.

## Quotes Inside Quotes

You can use quotes inside a string as long as they don't match the quotes surrounding the string:

### Example

```javascript
let answer1 = "It's alright";
let answer2 = "He is called 'Johnny'";
let answer3 = 'He is called "Johnny"';
```

### Analogy: Nested Boxes

Imagine you have a box (the outer quotes) that contains another smaller box (the inner quotes). As long as you don’t use the same type of box for both, everything fits perfectly without confusion.

## Template Strings

Templates were introduced with ES6 (JavaScript 2016). Templates are strings enclosed in backticks (`` `This is a template string` ``).

Templates allow single and double quotes inside a string:

### Example

```javascript
let text = `He's often called "Johnny"`;
```

**Note:** Templates are not supported in Internet Explorer.

### Analogy: A Flexible Envelope

Templates are like flexible envelopes that can hold various shapes and sizes of letters (quotes). They can accommodate all kinds of content without worrying about what type of envelope (quote) you're using.

## String Length

To find the length of a string, use the built-in `length` property:

### Example

```javascript
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length;
```

### Analogy: Measuring a Rope

Think of a string as a rope. Just as you can measure the length of a rope, you can measure how many characters are in a string.

## Escape Characters

Because strings must be written within quotes, JavaScript will misunderstand this string:

```javascript
let text = "We are the so-called "Vikings" from the north.";
```

The string will be chopped to `"We are the so-called "`.

To solve this problem, you can use a backslash escape character. The backslash escape character (`\`) turns special characters into string characters:

### Escape Sequences

| Code | Result    | Description         |
|------|-----------|---------------------|
| `\'` | `'`       | Single quote        |
| `\"` | `"`       | Double quote        |
| `\\` | `\`       | Backslash           |
| `\b` | (Backspace) | Backspace         |
| `\f` | (Form Feed) | Form Feed         |
| `\n` | (New Line) | New Line           |
| `\r` | (Carriage Return) | Carriage Return |
| `\t` | (Horizontal Tab) | Horizontal Tab |
| `\v` | (Vertical Tab) | Vertical Tab     |

### Analogy: Special Characters in a Movie Script

Imagine you’re writing a movie script. The backslash is like a director’s cue that tells the actors how to deliver special lines (like quotes) without disrupting the flow of the script (the string).

### Examples

```javascript
let text = "We are the so-called \"Vikings\" from the north.";  // Inserts a double quote
let text = 'It\'s alright.';                                     // Inserts a single quote
let text = "The character \\ is called backslash.";             // Inserts a backslash
```

## Breaking Long Lines

For readability, programmers often like to avoid long code lines. A safe way to break up a statement is after an operator:

### Example

```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly!";
```

A safe way to break up a string is by using string addition:

### Example

```javascript
document.getElementById("demo").innerHTML = "Hello " +
"Dolly!";
```

## JavaScript Strings as Objects

Normally, JavaScript strings are primitive values, created from literals:

```javascript
let x = "John";
```

But strings can also be defined as objects with the keyword `new`:

```javascript
let y = new String("John");
```

### **Caution:** Avoid String Objects

**Do not create String objects.** The `new` keyword complicates the code and slows down execution speed. String objects can produce unexpected results:

### Comparison Example

```javascript
let x = "John";
let y = new String("John");

console.log(x == y);  // true
console.log(x === y); // false
```

### Analogy: Two Ways to Introduce Yourself

Introducing yourself can be done in two ways: casually saying, "Hi, I'm John" (primitive string) or presenting a formal ID card stating, "I am John" (string object). While they may refer to the same person, the ID card (string object) adds unnecessary complexity.

---

# JavaScript String Methods

## Basic String Methods
JavaScript strings are primitive and immutable: All string methods produce a new string without altering the original string.

### String length
The `length` property returns the length of a string:

```javascript
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length;
```

### Extracting String Characters
There are 4 methods for extracting string characters:

- **The `at(position)` Method**
- **The `charAt(position)` Method**
- **The `charCodeAt(position)` Method**
- **Using property access `[]` like in arrays**

### JavaScript String `charAt()`
The `charAt()` method returns the character at a specified index (position) in a string:

```javascript
let text = "HELLO WORLD";
let char = text.charAt(0);
```

### JavaScript String `charCodeAt()`
The `charCodeAt()` method returns the code of the character at a specified index in a string. The method returns a UTF-16 code (an integer between 0 and 65535).

```javascript
let text = "HELLO WORLD";
let char = text.charCodeAt(0);
```

### JavaScript String `at()`
ES2022 introduced the string method `at()`:

Examples:

Get the third letter of the name:

```javascript
const name = "W3Schools";
let letter = name.at(2);
```

Get the third letter of the name:

```javascript
const name = "W3Schools";
let letter = name[2];
```

The `at()` method allows the use of negative indexes while `charAt()` does not. For example, you can now use `myString.at(-2)` instead of `charAt(myString.length - 2)`.

### Browser Support
The `at()` method is a new addition to JavaScript and is supported in all modern browsers since March 2023:

| Browser  | Version  |
|----------|----------|
| Chrome   | 94       |
| Edge     | 94       |
| Firefox   | 93      |
| Safari   | 16.4     |
| Opera    | 79       |

### Property Access `[]`
Example:

```javascript
let text = "HELLO WORLD";
let char = text[0];
```

**Note:** Property access might be a little unpredictable:
- It makes strings look like arrays (but they are not).
- If no character is found, `[]` returns `undefined`, while `charAt()` returns an empty string.
- It is read-only. For example, `str[0] = "A"` gives no error (but does not work!).

### Extracting String Parts
There are 3 methods for extracting a part of a string:

- `slice(start, end)`
- `substring(start, end)`
- `substr(start, length)`

### JavaScript String `slice()`
`slice()` extracts a part of a string and returns the extracted part in a new string. It takes 2 parameters: start position and end position (end not included).

Example: Slice out a portion of a string from position 7 to position 13:

```javascript
let text = "Apple, Banana, Kiwi";
let part = text.slice(7, 13);
```

**Note:** JavaScript counts positions from zero, meaning:
- The first position is 0.
- The second position is 1.

If you omit the second parameter, the method will slice out the rest of the string:

```javascript
let text = "Apple, Banana, Kiwi";
let part = text.slice(7);
```

If a parameter is negative, the position is counted from the end of the string:

```javascript
let text = "Apple, Banana, Kiwi";
let part = text.slice(-12);
```

This example slices out a portion of a string from position -12 to position -6:

```javascript
let text = "Apple, Banana, Kiwi";
let part = text.slice(-12, -6);
```

### JavaScript String `substring()`
`substring()` is similar to `slice()`, but the difference is that start and end values less than 0 are treated as 0.

Example:

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substring(7, 13);
```

### JavaScript String `substr()`
`substr()` is similar to `slice()`, but the difference is that the second parameter specifies the length of the extracted part.

Example:

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substr(7, 6);
```

If you omit the second parameter, `substr()` will slice out the rest of the string.

Example:

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substr(7);
```

If the first parameter is negative, the position counts from the end of the string.

Example:

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substr(-4);
```

### Converting to Upper and Lower Case
A string is converted to upper case with `toUpperCase()`:

A string is converted to lower case with `toLowerCase()`:

#### JavaScript String `toUpperCase()`
Example:

```javascript
let text1 = "Hello World!";
let text2 = text1.toUpperCase();
```

#### JavaScript String `toLowerCase()`
Example:

```javascript
let text1 = "Hello World!";       // String
let text2 = text1.toLowerCase();  // text2 is text1 converted to lower
```

### JavaScript String `concat()`
`concat()` joins two or more strings:

Example:

```javascript
let text1 = "Hello";
let text2 = "World";
let text3 = text1.concat(" ", text2);
```

The `concat()` method can be used instead of the plus operator. These two lines do the same:

```javascript
text = "Hello" + " " + "World!";
text = "Hello".concat(" ", "World!");
```

**Note:** All string methods return a new string. They don't modify the original string. Formally said: Strings are immutable: Strings cannot be changed, only replaced.

### JavaScript String `trim()`
The `trim()` method removes whitespace from both sides of a string:

Example:

```javascript
let text1 = "      Hello World!      ";
let text2 = text1.trim();
```

### JavaScript String `trimStart()`
ECMAScript 2019 added the String method `trimStart()` to JavaScript. The `trimStart()` method works like `trim()`, but removes whitespace only from the start of a string.

Example:

```javascript
let text1 = "     Hello World!     ";
let text2 = text1.trimStart();
```

### JavaScript String `trimEnd()`
ECMAScript 2019 added the string method `trimEnd()` to JavaScript. The `trimEnd()` method works like `trim()`, but removes whitespace only from the end of a string.

Example:

```javascript
let text1 = "     Hello World!     ";
let text2 = text1.trimEnd();
```

### JavaScript String Padding
ECMAScript 2017 added two new string methods to JavaScript: `padStart()` and `padEnd()` to support padding at the beginning and at the end of a string.

#### JavaScript String `padStart()`
The `padStart()` method pads a string from the start. It pads a string with another string (multiple times) until it reaches a given length.

Example: Pad a string with "0" until it reaches the length 4:

```javascript
let text = "5";
let padded = text.padStart(4, "0");
```

Example: Pad a string with "x" until it reaches the length 4:

```javascript
let text = "5";
let padded = text.padStart(4, "x");
```

**Note:** The `padStart()` method is a string method. To pad a number, convert the number to a string first.

Example:

```javascript
let numb = 5;
let text = numb.toString();
let padded = text.padStart(4, "0");
```

### Browser Support
`padStart()` is an ECMAScript 2017 feature. ES2017 is supported in all modern browsers since September 2017:

| Browser  | Version  |
|----------|----------|
| Chrome   | 58       |
| Edge     | 15       |
| Firefox  | 52       |
| Safari   | 11       |
| Opera    | 45       |

### JavaScript String `padEnd()`
The `padEnd()` method pads a string from the end. It pads a string with another string (multiple times) until it reaches a given length.

Example:

```javascript
let text = "5";
let padded = text.padEnd(4, "0");
```

Example:

```javascript
let text = "5";
let padded = text.padEnd(4, "x");
```

**Note:** The `padEnd()` method is a string method. To pad a number, convert the number to a string first.

Example:

```javascript
let numb = 5;
let text = numb.toString();
let padded = text.padEnd(4, "0");
```

### Browser Support
`padEnd()` is an ECMAScript 2017 feature. ES2017 is supported in all modern browsers since September 2017:

| Browser  | Version  |
|----------|----------|
| Chrome   | 58      

 |
| Edge     | 15       |
| Firefox  | 52       |
| Safari   | 11       |
| Opera    | 45       |

### Searching a String
The `indexOf()` and `lastIndexOf()` methods are used to search for a string in another string.

### JavaScript String `indexOf()`
The `indexOf()` method returns the first index (position) of a specified value in a string.

Example:

```javascript
let text = "HELLO WORLD";
let position = text.indexOf("O");
```

### JavaScript String `lastIndexOf()`
The `lastIndexOf()` method returns the last index (position) of a specified value in a string.

Example:

```javascript
let text = "HELLO WORLD";
let position = text.lastIndexOf("O");
```

### JavaScript String `search()`
The `search()` method searches for a match between a regular expression and a string. It returns the index of the first match found, or -1 if no match was found.

Example:

```javascript
let text = "HELLO WORLD";
let position = text.search("W");
```

### JavaScript String `replace()`
The `replace()` method replaces a specified value with another value in a string. The `replace()` method returns a new string.

Example:

```javascript
let text = "HELLO WORLD";
let newText = text.replace("WORLD", "EVERYONE");
```

### JavaScript String `replaceAll()`
The `replaceAll()` method replaces all occurrences of a specified value in a string with another value. The `replaceAll()` method returns a new string.

Example:

```javascript
let text = "HELLO WORLD";
let newText = text.replaceAll("O", "X");
```

### JavaScript String `split()`
The `split()` method splits a string into an array of substrings.

Example:

```javascript
let text = "APPLE, BANANA, KIWI";
let fruits = text.split(", ");
```

### JavaScript String `includes()`
The `includes()` method checks whether a string contains a specified value, returning true or false.

Example:

```javascript
let text = "HELLO WORLD";
let isPresent = text.includes("WORLD");
```

### JavaScript String `startsWith()`
The `startsWith()` method checks whether a string starts with a specified value, returning true or false.

Example:

```javascript
let text = "HELLO WORLD";
let isStarting = text.startsWith("HELLO");
```

### JavaScript String `endsWith()`
The `endsWith()` method checks whether a string ends with a specified value, returning true or false.

Example:

```javascript
let text = "HELLO WORLD";
let isEnding = text.endsWith("WORLD");
```

## Conclusion
JavaScript strings are an essential part of programming. Understanding these string methods will help you manipulate strings effectively, improving your coding efficiency.

---

# JavaScript String Search

## Introduction
Searching through strings in JavaScript is like looking for a book in a library. We use different tools and methods to find what we need. Below, we will explore several methods that allow us to locate text within strings.

## String Search Methods
- `String indexOf()`
- `String lastIndexOf()`
- `String search()`
- `String match()`
- `String matchAll()`
- `String includes()`
- `String startsWith()`
- `String endsWith()`

## JavaScript String indexOf()
The `indexOf()` method is like a librarian who tells you which shelf a book is on for the first time. It returns the index (position) of the first occurrence of a string in another string or -1 if the string is not found.

### Example
```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate"); // index will be 7
```

**Note:** JavaScript counts positions from zero. Therefore, 0 is the first position in a string, 1 is the second, and so on.

## JavaScript String lastIndexOf()
The `lastIndexOf()` method is like a librarian who tells you which shelf a book is on, but searching from the end to the beginning. It returns the index of the last occurrence of a specified text.

### Example
```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.lastIndexOf("locate"); // index will be 7
```

Both methods (`indexOf()` and `lastIndexOf()`) return -1 if the text is not found.

### Searching from a Specific Position
Both methods accept a second parameter that indicates the position to start the search.

### Example
```javascript
let index = text.indexOf("locate", 15); // index will be -1
```

## JavaScript String search()
The `search()` method is like a detective searching for a keyword in a book. It returns the position of the match of a string or a regular expression.

### Example
```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.search("locate"); // index will be 7
```

### Comparison with `indexOf()`
Both methods accept similar arguments and return similar values, but there are differences:
- `search()` does not accept a second argument.
- `indexOf()` cannot take powerful search values (regular expressions).

## JavaScript String match()
The `match()` method is like an exam that evaluates whether there are matches of a pattern in text. It returns an array with the results.

### Example
```javascript
let text = "The rain in SPAIN stays mainly in the plain";
let matches = text.match("ain"); // ["ain"]
```

### Global Search
```javascript
let matches = text.match(/ain/g); // ["ain", "ain", "ain"]
```

## JavaScript String matchAll()
The `matchAll()` method is like a group of detectives searching for all matches in a book. It returns an iterator with all the results.

### Example
```javascript
const iterator = text.matchAll(/ain/g);
```

**Note:** `matchAll()` is an ES2020 feature and does not work in Internet Explorer.

## JavaScript String includes()
The `includes()` method is like asking if a store has a specific product. It returns `true` if the string contains a specified value and `false` otherwise.

### Example
```javascript
let text = "Hello world, welcome to the universe.";
let hasWorld = text.includes("world"); // true
```

## JavaScript String startsWith()
The `startsWith()` method is like checking if a book starts with a certain phrase. It returns `true` if the string begins with a specified value.

### Example
```javascript
let text = "Hello world, welcome to the universe.";
let startsWithHello = text.startsWith("Hello"); // true
```

## JavaScript String endsWith()
The `endsWith()` method is like checking if a book ends with a certain phrase. It returns `true` if the string ends with a specified value.

### Example
```javascript
let text = "John Doe";
let endsWithDoe = text.endsWith("Doe"); // true
```

## Conclusion
Understanding how to search and manipulate strings in JavaScript is essential for working with data. These methods are powerful tools that will allow you to access and modify information efficiently. As you progress on your journey as a frontend developer, mastering these techniques will be crucial.

---

# JavaScript Template Strings

## Introduction
JavaScript Template Strings are like versatile containers that allow you to create and manipulate strings with ease. They offer various features that make string handling simpler and more powerful.

## String Templates
### Template Strings
Template Strings, also known as Template Literals, are like modern kitchen tools that help you prepare meals more efficiently. They make it easier to cook up strings, especially when you need to mix different ingredients (variables, expressions) together.

### Beloved Child Has Many Names
Template Strings go by multiple names—Template Strings and Template Literals. They refer to the same concept, so don't be surprised if you hear both terms used interchangeably.

## Back-Ticks Syntax
Template Strings use back-ticks (``) instead of regular quotes ("" or ''). This is like using a special type of bowl to mix ingredients that can hold more than just one flavor.

### Example
```javascript
let text = `Hello World!`;
```

## Quotes Inside Strings
One of the perks of Template Strings is that they allow both single and double quotes inside the string. This is like having a universal recipe that can handle various spices without losing flavor.

### Example
```javascript
let text = `He's often called "Johnny"`;
```

## Multiline Strings
Template Strings can span multiple lines, allowing you to write longer passages without worrying about concatenation. This is like having a large canvas to paint a beautiful landscape instead of being confined to a small piece of paper.

### Example
```javascript
let text =
`The quick
brown fox
jumps over
the lazy dog`;
```

## Interpolation
Template Strings provide an easy way to interpolate variables and expressions into strings. This technique is known as **string interpolation**, which allows you to blend various elements seamlessly.

### Variable Substitutions
Template Strings allow you to incorporate variables directly into the string, just like adding ingredients to your dish for a richer flavor.

### Example
```javascript
let firstName = "John";
let lastName = "Doe";

let text = `Welcome ${firstName}, ${lastName}!`; // Welcome John, Doe!
```

The automatic replacement of variables with their real values is what we call string interpolation.

### Expression Substitution
You can also embed expressions within Template Strings, which is like adding a complex ingredient that transforms your dish into something extraordinary.

### Example
```javascript
let price = 10;
let VAT = 0.25;

let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`; // Total: 12.50
```

This process of automatically replacing expressions with their real values is also known as string interpolation.

## HTML Templates
Template Strings can be particularly useful for generating HTML dynamically. They simplify the creation of complex structures, just like an efficient recipe helps you combine ingredients to create a masterpiece.

### Example
```javascript
let header = "Template Strings";
let tags = ["template strings", "javascript", "es6"];

let html = `<h2>${header}</h2><ul>`;
for (const x of tags) {
  html += `<li>${x}</li>`;
}
html += `</ul>`;
```

## Browser Support
Template Strings are an ES6 feature (JavaScript 2015). They are fully supported in all modern browsers since June 2017:

| Browser     | Version |
|-------------|---------|
| Chrome      | 51      |
| Edge        | 15      |
| Firefox     | 54      |
| Safari      | 10      |
| Opera       | 38      |

**Note:** Template Strings are not supported in Internet Explorer.

## Conclusion
JavaScript Template Strings are powerful tools that simplify string handling in programming. By using back-ticks, allowing quotes inside strings, supporting multiline text, and enabling easy interpolation, they make it easier to create dynamic and complex strings in your applications.

---

# JavaScript Numbers

## Introduction
JavaScript has only one type of number, which makes it straightforward to work with numerical data. You can write numbers with or without decimals, much like you can have a fruit smoothie with or without chunks of fruit.

### Example
```javascript
let x = 3.14;    // A number with decimals
let y = 3;       // A number without decimals
```

## Scientific Notation
When dealing with extra large or small numbers, JavaScript uses scientific (exponent) notation, similar to how we might refer to a huge mountain in terms of height rather than counting each tiny rock.

### Example
```javascript
let x = 123e5;    // This means 12300000
let y = 123e-5;   // This means 0.00123
```

## 64-bit Floating Point
In JavaScript, all numbers are stored as double precision floating point numbers according to the IEEE 754 standard. This is like having a high-quality camera that captures every detail in 64 different shades of color.

- **Value (Fraction/Mantissa):** Stored in bits 0 to 51.
- **Exponent:** Stored in bits 52 to 62.
- **Sign:** Stored in bit 63.

## Integer Precision
Integers, which are numbers without a decimal point, are accurate up to 15 digits. Think of it as having a measuring tape that can only measure lengths up to 15 centimeters without losing precision.

### Example
```javascript
let x = 999999999999999;   // x will be 999999999999999
let y = 9999999999999999;  // y will be 10000000000000000 (lost precision)
```

## Floating Point Precision
Floating point arithmetic isn't always perfectly accurate. This is similar to measuring ingredients in cooking, where a small difference in the amount can affect the taste of the dish.

### Example
```javascript
let x = 0.2 + 0.1; // Not exactly 0.3
```

To work around this issue, you can multiply and divide to retain precision.

### Example
```javascript
let x = (0.2 * 10 + 0.1 * 10) / 10; // Correctly results in 0.3
```

## Adding Numbers and Strings
JavaScript uses the `+` operator for both addition and concatenation. It's like a multitool that can serve both as a knife for cutting (adding numbers) and a spoon for mixing (concatenating strings).

### Numeric Addition
If you add two numbers, the result is a number.

### Example
```javascript
let x = 10;
let y = 20;
let z = x + y; // z will be 30
```

### String Concatenation
If you add two strings, the result is a concatenation of those strings.

### Example
```javascript
let x = "10";
let y = "20";
let z = x + y; // z will be "1020"
```

### Number and String Addition
If you mix a number with a string, the result will still be a string concatenation. This is like trying to pour a cup of water into a bowl of cereal—it combines in a way you might not expect!

### Examples
```javascript
let x = 10;
let y = "20";
let z = x + y; // z will be "1020"

let a = "10";
let b = 20;
let c = a + b; // c will be "1020"
```

### Common Mistakes
It’s common to expect results that don’t align with JavaScript's behavior due to left-to-right execution.

#### Example of Misleading Addition
```javascript
let x = 10;
let y = 20;
let z = "The result is: " + x + y; // z will be "The result is: 1020"
```

The interpreter first calculates `10 + 20`, then concatenates the string, leading to confusion.

## Numeric Strings
JavaScript recognizes strings that contain numeric content and will attempt to convert them to numbers in numeric operations, just like a chef using measurements on a label.

### Working Examples
```javascript
let x = "100";
let y = "10";
let z = x / y; // z will be 10

let a = "100";
let b = "10";
let c = a * b; // c will be 1000

let d = "100";
let e = "10";
let f = d - e; // f will be 90
```

However, using `+` will concatenate the strings.

### Example
```javascript
let x = "100";
let y = "10";
let z = x + y; // z will be "10010"
```

## NaN - Not a Number
`NaN` is a special value that indicates a result is not a legal number. Think of it as a "no entry" sign for mathematical operations.

### Example
```javascript
let x = 100 / "Apple"; // x will be NaN
```

If the string is numeric, the result will be a valid number.

### Example
```javascript
let x = 100 / "10"; // x will be 10
```

You can use the global function `isNaN()` to check for `NaN`.

### Example
```javascript
let x = 100 / "Apple";
isNaN(x); // returns true
```

If you perform a mathematical operation with `NaN`, the result will also be `NaN`.

### Example
```javascript
let x = NaN;
let y = 5;
let z = x + y; // z will be NaN
```

Or it might result in a strange concatenation like `NaN5`.

### Example
```javascript
let x = NaN;
let y = "5";
let z = x + y; // z will be "NaN5"
```

Interestingly, `NaN` is still considered a number in JavaScript:

### Example
```javascript
typeof NaN; // returns "number"
```

## Infinity
Infinity (or -Infinity) is returned when a calculation exceeds the largest possible number, like trying to measure the height of a mountain that's too tall to exist!

### Example
```javascript
let myNumber = 2;
while (myNumber != Infinity) {
  myNumber = myNumber * myNumber; // Eventually reaches Infinity
}
```

Division by zero also produces Infinity:

### Example
```javascript
let x =  2 / 0; // x will be Infinity
let y = -2 / 0; // y will be -Infinity
```

Like `NaN`, `Infinity` is also a number:

### Example
```javascript
typeof Infinity; // returns "number"
```

## Hexadecimal
In JavaScript, numbers can be written in hexadecimal format by prefixing them with `0x`, similar to using a different language to represent colors.

### Example
```javascript
let x = 0xFF; // 255 in decimal
```

Be cautious with leading zeros; they can sometimes lead to unexpected interpretations.

## Number Base Conversions
JavaScript displays numbers in base 10 by default. However, you can convert them to various bases using the `toString()` method.

### Example
```javascript
let myNumber = 32;
myNumber.toString(2);  // Converts to binary (base 2)
myNumber.toString(8);  // Converts to octal (base 8)
myNumber.toString(10); // Converts to decimal (base 10)
myNumber.toString(16); // Converts to hexadecimal (base 16)
```

## JavaScript Numbers as Objects
Normally, JavaScript numbers are primitive values. But they can also be defined as objects using the `new` keyword, much like turning a basic tool into a specialized instrument.

### Example
```javascript
let x = 123;          // Primitive value
let y = new Number(123); // Object
```

### Warning: Avoid Creating Number Objects
Creating Number objects complicates your code and slows down execution speed. It's generally advised to stick with primitive values.

When using the `==` operator, objects can behave unexpectedly.

### Example
```javascript
let x = 500;
let y = new Number(500);
console.log(x == y); // true, because the values are equal
console.log(x === y); // false, because they are different types
```

Comparing two Number objects always returns false.

### Example
```javascript
let a = new Number(500);
let b = new Number(500);
console.log(a === b); // false, different objects
```

## Conclusion
Understanding JavaScript Numbers is essential for any frontend developer. By grasping how numbers work, including precision, operations, and special values like `NaN` and `Infinity`, you can better handle numerical data in your applications.

---

# JavaScript BigInt: A Traveler in the World of Large Numbers

## Introduction to BigInt
JavaScript BigInt is a special data type used to store very large integer values that cannot be represented by a normal JavaScript Number.

### Analogy
Imagine you have a toolbox. Normal numbers are like a regular screwdriver: they work for most tasks, but if you need a giant screwdriver (a really large number), you need a special tool, which is BigInt.

## Integer Precision in JavaScript
JavaScript integers are only accurate up to 15 digits:

```javascript
let x = 999999999999999; // Accurate
let y = 9999999999999999; // Not accurate
```

In JavaScript, all numbers are stored in a 64-bit floating-point format (IEEE 754 standard). This means large numbers cannot be represented accurately and are rounded.

### Analogy
It’s like a clock that can only show up to 12 hours. If you try to set it to 15 hours, the clock will reset to 3. Similarly, large numbers are "rounded" to fit this format.

### Safe Integer Range
JavaScript can safely represent integers:

- Up to **9007199254740991** ( \(2^{53} - 1\) )
- And down to **-9007199254740991** ( \(-2^{53} + 1\) )

Values outside this range lose precision.

## How to Create a BigInt
To create a BigInt, you can append `n` to the end of an integer or call `BigInt()`:

### Examples
```javascript
let x = 9999999999999999; // Normal
let y = 9999999999999999n; // BigInt
let z = BigInt(1234567890123456789012345); // BigInt
```

## BigInt: A New Data Type in JavaScript
The type of a BigInt is `"bigint"`:

### Example
```javascript
let x = BigInt(999999999999999);
let type = typeof x; // "bigint"
```

BigInt is the second numeric data type in JavaScript (after Number). With BigInt, the total number of supported data types in JavaScript is **8**:

1. String
2. Number
3. Bigint
4. Boolean
5. Undefined
6. Null
7. Symbol
8. Object

### Analogy
Imagine you have a store that sells different types of fruits. Each type of fruit represents a data type in JavaScript. BigInt is a new fruit that has been added to the store.

## BigInt Operators
Operators that can be used on a normal JavaScript Number can also be used on a BigInt.

### Example of BigInt Multiplication
```javascript
let x = 9007199254740995n;
let y = 9007199254740995n;
let z = x * y; // Multiplication
```

### Notes
- Arithmetic between a BigInt and a normal Number is not allowed (type conversion may lose information).
- The unsigned right shift (`>>>`) cannot be done on a BigInt (it does not have a fixed width).

## BigInt and Decimals
A BigInt cannot have decimals.

### Example of BigInt Division
```javascript
let x = 5n;
let y = x / 2; // Error: Cannot mix BigInt and other types
let z = Number(x) / 2; // Explicit conversion
```

## Hexadecimal, Octal, and Binary Notation for BigInt
A BigInt can also be written in hexadecimal, octal, or binary notation:

### Example in Hexadecimal
```javascript
let hex = 0x20000000000003n; // Hexadecimal
let oct = 0o400000000000000003n; // Octal
let bin = 0b100000000000000000000000000000000000000000000000000011n; // Binary
```

## Curiosity about Precision
Rounding can compromise program security.

### Example of MAX_SAFE_INTEGER
```javascript
9007199254740992 === 9007199254740993; // is true !!!
```

## Browser Support
BigInt is supported in all browsers since September 2020:

- Chrome 67
- Edge 79
- Firefox 68
- Safari 14
- Opera 54

## Minimum and Maximum Safe Integers
ES6 added max and min properties to the Number object:

- **MAX_SAFE_INTEGER**
- **MIN_SAFE_INTEGER**

### Example of MAX_SAFE_INTEGER
```javascript
let x = Number.MAX_SAFE_INTEGER; // 9007199254740991
```

### Example of MIN_SAFE_INTEGER
```javascript
let x = Number.MIN_SAFE_INTEGER; // -9007199254740991
```

## New Methods for the Number Object
ES6 also added 2 new methods to the Number object:

- **Number.isInteger()**
- **Number.isSafeInteger()**

### Number.isInteger() Method
The `Number.isInteger()` method returns `true` if the argument is an integer.

#### Example of isInteger()
```javascript
Number.isInteger(10); // true
Number.isInteger(10.5); // false
```

### Number.isSafeInteger() Method
A safe integer is an integer that can be exactly represented as a double-precision number.

The `Number.isSafeInteger()` method returns `true` if the argument is a safe integer.

#### Example of isSafeInteger()
```javascript
Number.isSafeInteger(10); // true
Number.isSafeInteger(12345678901234567890); // false
```

Safe integers are all integers from \(-(2^{53} - 1)\) to \((2^{53} - 1)\). This is safe: **9007199254740991**. This is not safe: **9007199254740992**.

---

# JavaScript Number Methods

Understanding JavaScript number methods is crucial for effective programming. Let's explore these methods, breaking them down using simple analogies to make the concepts more relatable.

## Overview of Number Methods

These number methods can be used on all JavaScript numbers:

| Method          | Description                                        |
|------------------|----------------------------------------------------|
| `toString()`     | Returns a number as a string                      |
| `toExponential()`| Returns a number written in exponential notation   |
| `toFixed()`      | Returns a number written with a specified number of decimals |
| `toPrecision()`  | Returns a number written with a specified length  |
| `valueOf()`      | Returns a number as a number                      |

---

## The `toString()` Method

Imagine you have a number like a fruit (say, an apple). The `toString()` method takes that apple and puts it in a shiny gift box (the string). 

### Example:
```javascript
let x = 123;
console.log(x.toString());        // "123"
console.log((123).toString());     // "123"
console.log((100 + 23).toString()); // "123"
```

---

## The `toExponential()` Method

Think of this method as a way to express a number in a compact form, like using an abbreviation. If you have a long name, you might say “Mr. Smith” instead of “Mister Smith.” 

### Example:
```javascript
let x = 9.656;
console.log(x.toExponential(2));  // "9.66e+0"
console.log(x.toExponential(4));  // "9.6560e+0"
console.log(x.toExponential(6));  // "9.656000e+0"
```
The parameter is optional; if omitted, JavaScript will use the default representation.

---

## The `toFixed()` Method

This method is like setting your watch to show the exact time. `toFixed()` specifies how many decimal places you want to see, just like adjusting your watch to show seconds.

### Example:
```javascript
let x = 9.656;
console.log(x.toFixed(0));   // "10"
console.log(x.toFixed(2));   // "9.66"
console.log(x.toFixed(4));   // "9.6560"
console.log(x.toFixed(6));   // "9.656000"
```

---

## The `toPrecision()` Method

Think of `toPrecision()` as tailoring a suit to fit perfectly. You specify how you want the number to fit (the length), and it adjusts accordingly.

### Example:
```javascript
let x = 9.656;
console.log(x.toPrecision());  // "9.656"
console.log(x.toPrecision(2));  // "9.7"
console.log(x.toPrecision(4));  // "9.656"
console.log(x.toPrecision(6));  // "9.65600"
```

---

## The `valueOf()` Method

This method is straightforward, like showing the actual weight of an object instead of describing it. `valueOf()` gives you the raw number without any decoration.

### Example:
```javascript
let x = 123;
console.log(x.valueOf());        // 123
console.log((123).valueOf());     // 123
console.log((100 + 23).valueOf()); // 123
```
In JavaScript, a number can be either a primitive value (`typeof = number`) or an object (`typeof = object`). `valueOf()` is used internally to convert number objects to primitive values.

---

## Converting Variables to Numbers

There are three JavaScript methods that can be used to convert a variable to a number:

| Method         | Description                                        |
|-----------------|---------------------------------------------------|
| `Number()`      | Returns a number converted from its argument.     |
| `parseFloat()`  | Parses its argument and returns a floating point number. |
| `parseInt()`    | Parses its argument and returns a whole number.    |

### The `Number()` Method

Using `Number()` is like trying to measure an object with a ruler. You expect it to give you a numerical representation of whatever you give it.

### Example:
```javascript
console.log(Number(true));          // 1
console.log(Number(false));         // 0
console.log(Number("10"));          // 10
console.log(Number("  10"));        // 10
console.log(Number("10.33"));       // 10.33
console.log(Number("John"));        // NaN
```
If the value cannot be converted, it returns `NaN` (Not a Number).

---

### The `parseInt()` Method

`parseInt()` is like picking out the first whole piece of fruit from a mixed basket. It grabs the initial integer it sees.

### Example:
```javascript
console.log(parseInt("-10"));      // -10
console.log(parseInt("10.33"));     // 10
console.log(parseInt("10 years"));   // 10
console.log(parseInt("years 10"));   // NaN
```

---

### The `parseFloat()` Method

Similarly, `parseFloat()` is like looking for the first number in a series but allowing for decimals. 

### Example:
```javascript
console.log(parseFloat("10.33"));   // 10.33
console.log(parseFloat("10 years")); // 10
console.log(parseFloat("years 10")); // NaN
```

---

## Number Object Methods

These object methods belong to the `Number` object:

| Method                        | Description                                       |
|-------------------------------|---------------------------------------------------|
| `Number.isInteger()`          | Returns true if the argument is an integer       |
| `Number.isSafeInteger()`      | Returns true if the argument is a safe integer   |
| `Number.parseFloat()`         | Converts a string to a number                    |
| `Number.parseInt()`           | Converts a string to a whole number              |

### The `Number.isInteger()` Method

This method checks if a number is a whole number, similar to checking if an apple is whole and not cut in half.

### Example:
```javascript
console.log(Number.isInteger(10));     // true
console.log(Number.isInteger(10.5));   // false
```

---

### The `Number.isSafeInteger()` Method

A safe integer is like a reliable vehicle that can handle various terrains without breaking down. This method ensures the integer is safe to use.

### Example:
```javascript
console.log(Number.isSafeInteger(10));          // true
console.log(Number.isSafeInteger(12345678901234567890)); // false
```

Safe integers range from -(2^53 - 1) to +(2^53 - 1).

---

### The `Number.parseFloat()` and `Number.parseInt()` Methods

Both `Number.parseFloat()` and `Number.parseInt()` serve the same purpose as their global counterparts but offer a more modular approach to JavaScript.

### Example:
```javascript
console.log(Number.parseInt("10"));          // 10
console.log(Number.parseFloat("10.33"));     // 10.33
```

---

## Conclusion

By understanding these JavaScript number methods, you can manipulate numbers effectively in your programs. Use the analogies to help remember the methods and their functionalities, making your journey into frontend development smoother and more intuitive.

---

# JavaScript Number Properties

## Number Properties

| Property             | Description                                                |
|----------------------|------------------------------------------------------------|
| `EPSILON`            | The difference between 1 and the smallest number > 1.     |
| `MAX_VALUE`          | The largest possible number in JavaScript.                 |
| `MIN_VALUE`          | The smallest possible number in JavaScript.                |
| `MAX_SAFE_INTEGER`   | The maximum safe integer (253 - 1).                        |
| `MIN_SAFE_INTEGER`   | The minimum safe integer -(253 - 1).                       |
| `POSITIVE_INFINITY`  | Infinity (returned on overflow).                          |
| `NEGATIVE_INFINITY`  | Negative infinity (returned on overflow).                 |
| `NaN`                | A value that stands for "Not a Number".                   |

## JavaScript EPSILON

The `Number.EPSILON` property represents the difference between the smallest floating-point number greater than 1 and 1.

**Example**
```javascript
let x = Number.EPSILON;
console.log(x); // 2.220446049250313e-16
```

**Note**: `Number.EPSILON` is an ES6 feature and does not work in Internet Explorer.

**Analogy**: Think of `EPSILON` as a ruler measuring the tiniest gap you can perceive between two objects. Though it seems like a small space, it’s crucial for understanding the precision of numbers.

## JavaScript MAX_VALUE

`Number.MAX_VALUE` is a constant representing the largest possible number in JavaScript.

**Example**
```javascript
let x = Number.MAX_VALUE;
console.log(x); // 1.7976931348623157e+308
```

**Analogy**: Imagine `MAX_VALUE` as the peak of a mountain. As you climb, you get closer to the top, but there’s a point where you can’t go any further. That’s the largest number JavaScript can handle.

## JavaScript MIN_VALUE

`Number.MIN_VALUE` is a constant representing the smallest possible number in JavaScript.

**Example**
```javascript
let x = Number.MIN_VALUE;
console.log(x); // 5e-324
```

**Analogy**: Think of `MIN_VALUE` as the bottom of an ocean. It’s the lowest point you can reach in the water, but there’s still a bit of water left, even if it’s very little.

## JavaScript MAX_SAFE_INTEGER

`Number.MAX_SAFE_INTEGER` represents the maximum safe integer in JavaScript, which is (253 - 1).

**Example**
```javascript
let x = Number.MAX_SAFE_INTEGER;
console.log(x); // 9007199254740991
```

**Analogy**: Consider `MAX_SAFE_INTEGER` as a safe deposit box. You can store items up to a certain limit; beyond that, items might get damaged or lost.

## JavaScript MIN_SAFE_INTEGER

`Number.MIN_SAFE_INTEGER` represents the minimum safe integer in JavaScript, which is -(253 - 1).

**Example**
```javascript
let x = Number.MIN_SAFE_INTEGER;
console.log(x); // -9007199254740991
```

**Note**: `MAX_SAFE_INTEGER` and `MIN_SAFE_INTEGER` are ES6 features and do not work in Internet Explorer.

**Analogy**: Think of `MIN_SAFE_INTEGER` as the bottom of a safe deposit box. It’s the lowest point you can store items without losing them.

## JavaScript POSITIVE_INFINITY

`Number.POSITIVE_INFINITY` represents positive infinity.

**Example**
```javascript
let x = Number.POSITIVE_INFINITY;
console.log(x); // Infinity
```

**Positive Infinity** is returned in case of an overflow:

```javascript
let x = 1 / 0; // Returns Infinity
console.log(x);
```

**Analogy**: Think of `POSITIVE_INFINITY` as the horizon. No matter how far you walk towards it, it always seems to be in the distance; you never reach it.

## JavaScript NEGATIVE_INFINITY

`Number.NEGATIVE_INFINITY` represents negative infinity.

**Example**
```javascript
let x = Number.NEGATIVE_INFINITY;
console.log(x); // -Infinity
```

**Negative Infinity** is returned in case of an overflow:

```javascript
let x = -1 / 0; // Returns -Infinity
console.log(x);
```

**Analogy**: Think of `NEGATIVE_INFINITY` as the bottom of a well. The deeper you dig, the further you get from the surface, but you never reach a bottom.

## JavaScript NaN - Not a Number

`NaN` is a reserved word in JavaScript that indicates a number that is not valid.

**Example**
```javascript
let x = Number.NaN;
console.log(x); // NaN
```

Attempting to perform an arithmetic operation with a non-numeric string will result in `NaN` (Not a Number):

```javascript
let x = 100 / "Apple"; // Returns NaN
console.log(x);
```

**Analogy**: Think of `NaN` as a puzzle with pieces that don’t fit together. No matter how hard you try, you can’t form a coherent picture with those pieces.

## Number Properties Cannot Be Used in Variables

Number properties belong to the Number object in JavaScript. These properties can only be accessed as `Number.MAX_VALUE`. 

Using `x.MAX_VALUE`, where `x` is a variable or value, will return `undefined`:

**Example**
```javascript
let x = 6;
console.log(x.MAX_VALUE); // undefined
```

**Analogy**: This is like trying to use a label that’s only on the box, not on the object inside the box. The object inside the box can’t access the properties of the box.

---

# JavaScript Arrays

## What is an Array?

An array is a special variable that can hold more than one value. Think of it as a box that can contain multiple items, making it easier to manage collections of data.

```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

### Why Use Arrays?

If you have a list of items (like car names), using single variables for each item can quickly become cumbersome. For example, consider this:

```javascript
let car1 = "Saab";
let car2 = "Volvo";
let car3 = "BMW";
```

But what if you want to find a specific car or if you had not 3 cars, but 300? The solution is an array! An array can hold many values under a single name, and you can access the values using their index numbers.

### Creating an Array

The easiest way to create a JavaScript array is using an array literal.

**Syntax:**

```javascript
const array_name = [item1, item2, ...];
```

It's common practice to declare arrays with the `const` keyword.

#### Example

```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

Spaces and line breaks are not important. A declaration can span multiple lines:

```javascript
const cars = [
  "Saab",
  "Volvo",
  "BMW"
];
```

You can also create an array and then provide the elements:

```javascript
const cars = [];
cars[0] = "Saab";
cars[1] = "Volvo";
cars[2] = "BMW";
```

### Using the JavaScript Keyword `new`

You can also create an array using the `new` keyword, but it’s not necessary. 

#### Example

```javascript
const cars = new Array("Saab", "Volvo", "BMW");
```

Both methods accomplish the same thing, but for simplicity and readability, it’s better to use the array literal method.

### Accessing Array Elements

To access an element in an array, refer to its index number. 

```javascript
const cars = ["Saab", "Volvo", "BMW"];
let car = cars[0]; // Access the first element
```

**Note:** Array indexes start at 0. So, `[0]` is the first element, and `[1]` is the second.

### Changing an Array Element

You can change the value of an array element by accessing it via its index:

```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars[0] = "Opel"; // Changes the first element to "Opel"
```

### Converting an Array to a String

You can convert an array to a string using the `toString()` method:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();
```

**Result:** `Banana,Orange,Apple,Mango`

### Access the Full Array

You can access the entire array by referring to its name:

```javascript
const cars = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = cars;
```

### Arrays are Objects

In JavaScript, arrays are a special type of objects. The `typeof` operator will return "object" for arrays.

```javascript
const person = ["John", "Doe", 46];
```

### Array Elements Can Be Objects

JavaScript allows arrays to hold variables of different types:

```javascript
myArray[0] = Date.now; // A function
myArray[1] = myFunction; // Another function
myArray[2] = myCars; // Another array
```

### Array Properties and Methods

JavaScript arrays come with built-in properties and methods that give them their power:

- `cars.length` // Returns the number of elements
- `cars.sort()` // Sorts the array

### The Length Property

The `length` property returns the number of elements in an array:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let length = fruits.length; // length will be 4
```

**Note:** The length property is always one more than the highest index.

### Accessing the First and Last Array Element

To access the first and last elements:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let firstFruit = fruits[0]; // First element
let lastFruit = fruits[fruits.length - 1]; // Last element
```

### Looping Through Array Elements

You can loop through an array using a `for` loop:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let text = "<ul>";
for (let i = 0; i < fruits.length; i++) {
  text += "<li>" + fruits[i] + "</li>";
}
text += "</ul>";
```

Or you can use the `forEach()` function:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let text = "<ul>";
fruits.forEach(function(value) {
  text += "<li>" + value + "</li>";
});
text += "</ul>";
```

### Adding Array Elements

The easiest way to add a new element to an array is with the `push()` method:

```javascript
const fruits = ["Banana", "Orange", "Apple"];
fruits.push("Lemon"); // Adds "Lemon" to the end of the array
```

You can also use the `length` property to add elements:

```javascript
fruits[fruits.length] = "Lemon"; // Adds "Lemon" to the end
```

#### WARNING!

Adding elements with high indexes can create undefined "holes" in an array:

```javascript
const fruits = ["Banana", "Orange", "Apple"];
fruits[6] = "Lemon"; // Creates undefined holes in the array
```

### Associative Arrays

Many programming languages support arrays with named indexes, called associative arrays or hashes. JavaScript does not support these. 

If you use named indexes in JavaScript, it will redefine the array as an object, which can lead to unexpected results:

```javascript
const person = [];
person["firstName"] = "John"; // Redefines person as an object
person.length; // Returns 0
```

### The Difference Between Arrays and Objects

- In JavaScript, arrays use numbered indexes, while objects use named indexes.
- Arrays are a special kind of object with numbered indexes.

### When to Use Arrays vs. Objects

- Use objects when you want the element names to be strings (text).
- Use arrays when you want the element names to be numbers.

### Recognizing an Array

To check if a variable is an array, you can use:

**Solution 1:**

```javascript
Array.isArray(fruits); // Returns true if fruits is an array
```

**Solution 2:**

```javascript
(fruits instanceof Array); // Returns true if fruits is an array
```

### Nested Arrays and Objects

Values in objects can be arrays, and values in arrays can be objects:

```javascript
const myObj = {
  name: "John",
  age: 30,
  cars: [
    { name: "Ford", models: ["Fiesta", "Focus", "Mustang"] },
    { name: "BMW", models: ["320", "X3", "X5"] },
    { name: "Fiat", models: ["500", "Panda"] }
  ]
};
```

To access arrays within objects, use a loop:

```javascript
for (let i in myObj.cars) {
  console.log(myObj.cars[i].name);
  for (let j in myObj.cars[i].models) {
    console.log(myObj.cars[i].models[j]);
  }
}
```

## Conclusion

Arrays are a fundamental part of JavaScript, providing a powerful way to manage collections of data. Understanding how to use them effectively will greatly enhance your ability to work with the language.

### Summary of Features:
- **Simple Analogies:** Each technical concept is explained with relatable analogies.
- **Code Examples:** Clear code snippets illustrate each point.
- **Warnings and Best Practices:** Important notes highlight potential pitfalls in using arrays.
- **Nested Structures:** Examples of nested arrays and objects provide a broader context.

---

# JavaScript Array Methods

## Basic Array Methods

### Array Length
**Concept**: The length property returns the size of an array.

**Analogy**: Imagine an array as a bookshelf. The `length` is like counting how many books are on that shelf.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let size = fruits.length; // size will be 4
```

### Array toString()
**Concept**: The `toString()` method converts an array to a string of comma-separated values.

**Analogy**: Think of `toString()` as a friendly librarian who gathers all the book titles and lists them on a single page.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.toString()); // Output: "Banana,Orange,Apple,Mango"
```

### Array at()
**Concept**: The `at()` method retrieves an element from an array using a specified index.

**Analogy**: If you have a box of chocolates, `at()` is like picking a specific chocolate by its position.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fruit = fruits.at(2); // fruit will be "Apple"
```

### Array join()
**Concept**: The `join()` method joins all elements of an array into a string with a specified separator.

**Analogy**: It’s like stringing together beads, where you can choose what type of string to use (comma, asterisk, etc.).

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.join(" * ")); // Output: "Banana * Orange * Apple * Mango"
```

### Popping and Pushing
**Concept**: Popping removes the last element from an array, while pushing adds a new element to the end.

**Analogy**: Picture a basket. You can remove the last apple (pop) or add a new apple to the basket (push).

**JavaScript Array pop()**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop(); // Removes "Mango"
```

**JavaScript Array push()**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi"); // Adds "Kiwi"
```

### Shifting Elements
**Concept**: Shifting removes the first element from an array and shifts all other elements down one index.

**Analogy**: Think of a row of people. If the first person leaves, everyone else shifts forward to fill the gap.

**JavaScript Array shift()**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift(); // Removes "Banana"
```

**JavaScript Array unshift()**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon"); // Adds "Lemon" at the beginning
```

### Changing Elements
**Concept**: You can change an element by accessing it through its index.

**Analogy**: If you have a recipe book, changing an ingredient is like switching one entry in the index.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[0] = "Kiwi"; // Replaces "Banana" with "Kiwi"
```

### Array delete()
**Warning**: Using `delete()` leaves undefined holes in the array. Use `pop()` or `shift()` instead.

**Analogy**: Deleting a book from the shelf without removing it leaves an empty space that nobody can use.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0]; // Leaves an undefined hole
```

### Merging Arrays (Concatenating)
**Concept**: Concatenation means joining arrays end-to-end.

**Analogy**: Think of it as connecting two chains; the links from both chains come together to form one longer chain.

**JavaScript Array concat()**:
```javascript
const myGirls = ["Cecilie", "Lone"];
const myBoys = ["Emil", "Tobias", "Linus"];
const myChildren = myGirls.concat(myBoys); // Merges both arrays
```

### Array copyWithin()
**Concept**: The `copyWithin()` method copies elements to another position in the same array.

**Analogy**: It’s like rearranging books on a shelf without adding or removing any.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.copyWithin(2, 0); // Copies "Banana" and "Orange" to positions 2 and 3
```

### Flattening an Array
**Concept**: Flattening reduces the dimensionality of an array.

**Analogy**: Imagine a multi-layer cake. Flattening it is like squishing the cake down to a single layer.

**JavaScript Array flat()**:
```javascript
const myArr = [[1, 2], [3, 4], [5, 6]];
const newArr = myArr.flat(); // Flattens to [1, 2, 3, 4, 5, 6]
```

### JavaScript Array splice()
**Concept**: The `splice()` method can add or remove items in an array.

**Analogy**: Think of it as editing a document; you can cut, add, or replace text.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi"); // Adds "Lemon" and "Kiwi" at index 2
```

### JavaScript Array slice()
**Concept**: The `slice()` method creates a new array by slicing out a part of an existing array.

**Analogy**: It’s like cutting a piece of cake; you take a slice but leave the rest intact.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1, 3); // Returns ["Orange", "Lemon"]
```

## Automatic toString
**Concept**: JavaScript automatically converts an array to a comma-separated string when a primitive value is expected.

**Analogy**: Just like a magic trick, when you call an array in a console, it transforms into a neat list of items.

**Example**:
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits); // Automatically outputs: "Banana,Orange,Apple,Mango"
```

---

# JavaScript Array Search

In this section, we'll explore various methods to search through arrays in JavaScript. Think of an array as a line of people waiting to enter a concert, and we want to find specific individuals (or values) in that line. Each person has a position, just like each value in the array has an index.

## Array Find and Search Methods

### Array `indexOf()`

The `indexOf()` method is like asking for the position of a friend in line. If your friend "Apple" is at the second position, you would get `1` (remember, we start counting from 0).

**Example:**

```javascript
const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.indexOf("Apple") + 1; // returns 1 (first occurrence)
```

**Syntax:**

```javascript
array.indexOf(item, start)
```

- `item`: The item you are searching for.
- `start`: Optional. The index at which to begin the search. Negative values will start counting from the end.

**Note:** If the item is not found, it returns `-1`. If it appears multiple times, only the position of the first occurrence is returned.

---

### Array `lastIndexOf()`

The `lastIndexOf()` method works like a reverse search, looking for the last occurrence of a friend in line. If there are several "Apple" friends, it tells you the position of the last one.

**Example:**

```javascript
const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.lastIndexOf("Apple") + 1; // returns 3 (last occurrence)
```

**Syntax:**

```javascript
array.lastIndexOf(item, start)
```

- `item`: The item to search for.
- `start`: Optional. The index to start the search. Negative values will start counting from the end.

---

### Array `includes()`

Introduced in ECMAScript 2016, `includes()` checks if a friend is present in line without giving their position.

**Example:**

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.includes("Mango")); // true
```

**Syntax:**

```javascript
array.includes(search-item)
```

**Note:** This method can also check for `NaN` values, unlike `indexOf()`.

**Browser Support:** This method is supported in all modern browsers but not in Internet Explorer.

---

### JavaScript Array `find()`

The `find()` method is like searching for the first friend in line who is taller than 18. It returns the value of the first person that satisfies the condition.

**Example:**

```javascript
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(value => value > 18); // returns 25
```

**Browser Support:** This is an ES6 feature and is supported in all modern browsers since June 2017.

---

### JavaScript Array `findIndex()`

Similar to `find()`, the `findIndex()` method returns the position (index) of the first person in line that satisfies the condition.

**Example:**

```javascript
const numbers = [4, 9, 16, 25, 29];
let firstIndex = numbers.findIndex(value => value > 18); // returns 3
```

**Browser Support:** This method is also an ES6 feature and is supported in all modern browsers.

---

### JavaScript Array `findLast()`

Introduced in ES2023, `findLast()` starts from the end of the line and returns the value of the first person that satisfies the condition.

**Example:**

```javascript
const temp = [27, 28, 30, 40, 42, 35, 30];
let high = temp.findLast(x => x > 40); // returns 42
```

**Browser Support:** Supported in modern browsers since July 2023.

---

### JavaScript Array `findLastIndex()`

The `findLastIndex()` method finds the index of the last person in line who satisfies a condition.

**Example:**

```javascript
const temp = [27, 28, 30, 40, 42, 35, 30];
let lastIndex = temp.findLastIndex(x => x > 40); // returns 4
```

**Browser Support:** Supported in modern browsers since July 2023.

---

# JavaScript Sorting Arrays

## Array Sort Methods

### Alphabetic Sort

Imagine you're organizing a box of crayons by color. You take each crayon and place it in order from A to Z, just like sorting an array alphabetically. In JavaScript, you can use the `sort()` method to accomplish this.

**Example:**
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();
console.log(fruits); // ["Apple", "Banana", "Mango", "Orange"]
```

### Reversing an Array

Now, let’s say you want to put those crayons back in reverse order, from Z to A. You can achieve this using the `reverse()` method.

**Example:**
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.reverse();
console.log(fruits); // ["Mango", "Apple", "Orange", "Banana"]
```

By combining `sort()` and `reverse()`, you can sort an array in descending order:

**Example:**
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort().reverse();
console.log(fruits); // ["Orange", "Mango", "Banana", "Apple"]
```

### JavaScript Array toSorted() Method

Starting with ES2023, the `toSorted()` method was introduced to sort an array without changing the original array. It’s like making a photocopy of your crayon box before sorting it, so you still have the original.

**Example:**
```javascript
const months = ["Jan", "Feb", "Mar", "Apr"];
const sorted = months.toSorted();
console.log(sorted); // ["Apr", "Feb", "Jan", "Mar"]
console.log(months); // ["Jan", "Feb", "Mar", "Apr"] (original remains unchanged)
```

### JavaScript Array toReversed() Method

Similarly, ES2023 added the `toReversed()` method to reverse an array without altering the original. It’s like flipping the crayons upside down, but still keeping the original order intact.

**Example:**
```javascript
const months = ["Jan", "Feb", "Mar", "Apr"];
const reversed = months.toReversed();
console.log(reversed); // ["Apr", "Mar", "Feb", "Jan"]
console.log(months); // ["Jan", "Feb", "Mar", "Apr"] (original remains unchanged)
```

### Numeric Sort

When sorting numbers, you must be cautious. Just like sorting a pile of toy cars by size, you can't compare them as if they were strings. For instance, "25" comes before "100" if treated as strings because "2" is less than "1". 

To fix this, provide a compare function in the `sort()` method.

**Example:**
```javascript
const points = [40, 100, 1, 5, 25, 10];
points.sort((a, b) => a - b);
console.log(points); // [1, 5, 10, 25, 40, 100]
```

### The Compare Function

The compare function defines an alternative sort order. It should return a negative, zero, or positive value based on its arguments:

- If the result is negative, `a` is sorted before `b`.
- If the result is positive, `b` is sorted before `a`.
- If the result is zero, the order remains unchanged.

**Example:**
```javascript
points.sort(function(a, b) {
  return a - b; // sorts numerically in ascending order
});
```

### Sorting an Array in Random Order

Sometimes, you want to shuffle your crayons randomly. You can use a sort function to accomplish this:

**Example:**
```javascript
const points = [40, 100, 1, 5, 25, 10];
points.sort(() => 0.5 - Math.random());
console.log(points); // The order will be random
```

However, the above method is not completely accurate. The Fisher Yates shuffle is a more reliable way to achieve randomness:

**Example:**
```javascript
const points = [40, 100, 1, 5, 25, 10];
for (let i = points.length - 1; i > 0; i--) {
  const j = Math.floor(Math.random() * (i + 1));
  [points[i], points[j]] = [points[j], points[i]]; // Swap elements
}
console.log(points); // Random order
```

### Find the Lowest (or Highest) Array Value

To find the min or max value in an array, you have several options:

1. Sort the array and check the first or last element.
2. Use `Math.min()` or `Math.max()`.
3. Write a homemade function.

**Using Math.min() on an Array:**

To find the lowest number in an array, use `Math.min.apply`:

**Example:**
```javascript
function myArrayMin(arr) {
  return Math.min.apply(null, arr);
}
console.log(myArrayMin([1, 2, 3])); // 1
```

**Using Math.max() on an Array:**

To find the highest number, use `Math.max.apply`:

**Example:**
```javascript
function myArrayMax(arr) {
  return Math.max.apply(null, arr);
}
console.log(myArrayMax([1, 2, 3])); // 3
```

### Homemade Min and Max Functions

You can create custom functions to find the minimum and maximum values:

**Find Min:**
```javascript
function myArrayMin(arr) {
  let min = Infinity;
  for (const num of arr) {
    if (num < min) {
      min = num;
    }
  }
  return min;
}
```

**Find Max:**
```javascript
function myArrayMax(arr) {
  let max = -Infinity;
  for (const num of arr) {
    if (num > max) {
      max = num;
    }
  }
  return max;
}
```

### Sorting Object Arrays

JavaScript arrays often contain objects, like a list of cars. You can sort these objects by their properties, much like organizing books by their titles.

**Example:**
```javascript
const cars = [
  {type:"Volvo", year:2016},
  {type:"Saab", year:2001},
  {type:"BMW", year:2010}
];

cars.sort((a, b) => a.year - b.year);
console.log(cars); // Sorted by year
```

### Stable Array Sort

Starting from ES2019, the `sort()` method ensures that elements with the same value maintain their relative position. 

**Example:**
```javascript
const myArr = [
  {name:"X00",price:100 },
  {name:"X01",price:100 },
  {name:"X02",price:100 },
  {name:"X03",price:100 },
  {name:"X04",price:110 },
  {name:"X05",price:110 },
  {name:"X06",price:110 },
  {name:"X07",price:110 }
];

myArr.sort((a, b) => a.price - b.price);
console.log(myArr); // X00, X01, X02, X03 will maintain their relative order
```

---

# JavaScript Array Iteration

## Array Iteration Methods

Array iteration methods operate on every array item:

- `Array forEach`
- `Array map()`
- `Array flatMap()`
- `Array filter()`
- `Array reduce()`
- `Array reduceRight()`

### See Also:
- Basic Array Methods
- Array Search Methods
- Array Sort Methods
- `Array every()`
- `Array some()`
- `Array from()`
- `Array keys()`
- `Array entries()`
- `Array with()`
- `Array Spread (...)`

---

## JavaScript Array forEach()

The `forEach()` method calls a function (a callback function) once for each array element. Think of it like a teacher (the `forEach` method) going through a list of students (the array) and giving each one a chance to answer a question.

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
let txt = "";
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt += value + "<br>";
}
```

Note that the function takes 3 arguments:
- The item value
- The item index
- The array itself

The example above uses only the value parameter. The example can be rewritten to:

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
let txt = "";
numbers.forEach(myFunction);

function myFunction(value) {
  txt += value + "<br>";
}
```

---

## JavaScript Array map()

The `map()` method creates a new array by performing a function on each array element. Imagine a chef (the `map` method) who takes each ingredient (the array items), processes it, and creates a new dish (the new array).

### Example

```javascript
const numbers1 = [45, 4, 9, 16, 25];
const numbers2 = numbers1.map(myFunction);

function myFunction(value, index, array) {
  return value * 2;
}
```

This method does not change the original array.

When a callback function uses only the value parameter, the index and array parameters can be omitted:

### Example

```javascript
const numbers1 = [45, 4, 9, 16, 25];
const numbers2 = numbers1.map(myFunction);

function myFunction(value) {
  return value * 2;
}
```

---

## JavaScript Array flatMap()

ES2019 added the `flatMap()` method to JavaScript. This method first maps all elements of an array and then creates a new array by flattening the array, similar to a baker who layers cake batter and then flattens it out into a single layer for baking.

### Example

```javascript
const myArr = [1, 2, 3, 4, 5, 6];
const newArr = myArr.flatMap((x) => x * 2);
```

### Browser Support
`flatMap()` is supported in all modern browsers since January 2020:
- Chrome 69
- Edge 79
- Firefox 62
- Safari 12
- Opera 56

---

## JavaScript Array filter()

The `filter()` method creates a new array with array elements that pass a test. Think of it as a security guard who only allows certain guests into a party based on specific criteria.

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
const over18 = numbers.filter(myFunction);

function myFunction(value) {
  return value > 18;
}
```

---

## JavaScript Array reduce()

The `reduce()` method runs a function on each array element to produce (reduce it to) a single value, like an accountant who summarizes all expenses into a single report.

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduce(myFunction);

function myFunction(total, value) {
  return total + value;
}
```

The `reduce()` method can accept an initial value:

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduce(myFunction, 100);

function myFunction(total, value) {
  return total + value;
}
```

---

## JavaScript Array reduceRight()

The `reduceRight()` method is similar to `reduce()`, but it works from right-to-left in the array, like reading a book from the back cover to the front.

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduceRight(myFunction);

function myFunction(total, value) {
  return total + value;
}
```

---

## JavaScript Array every()

The `every()` method checks if all array values pass a test. It’s like a teacher checking if every student in the class has completed their homework.

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
let allOver18 = numbers.every(myFunction);

function myFunction(value) {
  return value > 18;
}
```

---

## JavaScript Array some()

The `some()` method checks if some array values pass a test. It’s like asking if at least one student has their homework done.

### Example

```javascript
const numbers = [45, 4, 9, 16, 25];
let someOver18 = numbers.some(myFunction);

function myFunction(value) {
  return value > 18;
}
```

---

## JavaScript Array.from()

The `Array.from()` method returns an Array object from any object with a length property or any iterable object, like transforming a string into an array of characters.

### Example

```javascript
Array.from("ABCDEFG");
```

### Browser Support
`from()` is an ES6 feature (JavaScript 2015) and is fully supported in all modern browsers since June 2017.

---

## JavaScript Array keys()

The `Array.keys()` method returns an Array Iterator object with the keys of an array. It’s like giving you the index cards that correspond to each item in a library.

### Example

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const keys = fruits.keys();

for (let x of keys) {
  console.log(x);
}
```

### Browser Support
`keys()` is an ES6 feature (JavaScript 2015) and is supported in all modern browsers since June 2017.

---

## JavaScript Array entries()

The `entries()` method returns an Array Iterator object with key/value pairs, like a ledger that records transactions.

### Example

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const f = fruits.entries();

for (let x of f) {
  console.log(x);
}
```

---

## JavaScript Array with() Method

ES2023 added the `Array.with()` method as a safe way to update elements in an array without altering the original array, similar to a librarian who can check out a book without damaging it.

### Example

```javascript
const months = ["January", "February", "March", "April"];
const myMonths = months.with(2, "March");
```

---

## JavaScript Array Spread (...)

The `...` operator expands an iterable (like an array) into more elements, similar to pouring out contents from a container.

### Example

```javascript
const q1 = ["Jan", "Feb", "Mar"];
const q2 = ["Apr", "May", "Jun"];
const q3 = ["Jul", "Aug", "Sep"];
const q4 = ["Oct", "Nov", "Dec"];

const year = [...q1, ...q2, ...q3, ...q4];
```

### Browser Support
`...` is an ES6 feature (JavaScript 2015) and is supported in all modern browsers since June 2017.

---

# JavaScript Array Const

## ECMAScript 2015 (ES6)

In 2015, JavaScript introduced an important new keyword: `const`.

It has become a common practice to declare arrays using `const`:

### Example
```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

## Cannot Be Reassigned

An array declared with `const` cannot be reassigned:

### Example
```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"]; // ERROR
```

### Analogy
Think of `const` as a label on a box. If you label the box "Cars," you cannot change the label to "Autos" (reassign the variable). However, you can still change the items inside the box (modify the contents of the array).

## Arrays Are Not Constants

The keyword `const` can be a bit misleading. It does NOT define a constant array; it defines a constant reference to an array.

Because of this, we can still change the elements of a constant array.

### Elements Can Be Reassigned
You can change the elements of a constant array:

### Example
```javascript
// You can create a constant array:
const cars = ["Saab", "Volvo", "BMW"];

// You can change an element:
cars[0] = "Toyota"; // Changes "Saab" to "Toyota"

// You can add an element:
cars.push("Audi"); // Adds "Audi"
```

### Analogy
Imagine that the labeled box "Cars" contains several car models. You can swap "Saab" for "Toyota" or add a new car "Audi" to the collection, but the box will always bear the label "Cars."

## Browser Support

The `const` keyword is not supported in Internet Explorer 10 or earlier.

The following table defines the first browser versions with full support for the `const` keyword:

| Browser    | Version       |
|------------|---------------|
| Chrome     | 49            |
| IE         | 11 / Edge     |
| Firefox    | 36            |
| Safari     | 10            |
| Opera      | 36            |
| Date       | Mar, 2016     |

## Assigned When Declared

JavaScript `const` variables must be assigned a value when they are declared.

Meaning: An array declared with `const` must be initialized when it is declared.

### Example
This will not work:
```javascript
const cars; // ERROR
cars = ["Saab", "Volvo", "BMW"];
```

Arrays declared with `var` can be initialized at any time.

### Example
This is OK:
```javascript
cars = ["Saab", "Volvo", "BMW"]; // OK
var cars;
```

### Analogy
Think of `const` like an order at a restaurant. If you order a dish (declare the array), you must specify what you want (assign a value) when placing the order. If you just place the order without specifying, the waiter (the compiler) won’t know what to bring.

## Const Block Scope

An array declared with `const` has **block scope**.

An array declared in a block is not the same as an array declared outside the block:

### Example
```javascript
const cars = ["Saab", "Volvo", "BMW"];
// Here cars[0] is "Saab"
{
  const cars = ["Toyota", "Volvo", "BMW"];
  // Here cars[0] is "Toyota"
}
// Here cars[0] is "Saab"
```

An array declared with `var` does not have block scope:

### Example
```javascript
var cars = ["Saab", "Volvo", "BMW"];
// Here cars[0] is "Saab"
{
  var cars = ["Toyota", "Volvo", "BMW"];
  // Here cars[0] is "Toyota"
}
// Here cars[0] is "Toyota"
```

### Analogy
Imagine you have two rooms (blocks) in a house. In each room, you can have a box labeled "Cars," but each room can contain different models of cars without interfering with each other.

## Redeclaring Arrays

Redeclaring an array declared with `var` is allowed anywhere in a program:

### Example
```javascript
var cars = ["Volvo", "BMW"];   // Allowed
var cars = ["Toyota", "BMW"];  // Allowed
cars = ["Volvo", "Saab"];      // Allowed
```

Redeclaring or reassigning an array to `const`, in the same scope or in the same block, is not allowed:

### Example
```javascript
var cars = ["Volvo", "BMW"];     // Allowed
const cars = ["Volvo", "BMW"];   // Not allowed
{
  var cars = ["Volvo", "BMW"];   // Allowed
  const cars = ["Volvo", "BMW"]; // Not allowed
}
```

Redeclaring or reassigning an existing `const` array, in the same scope or in the same block, is not allowed:

### Example
```javascript
const cars = ["Volvo", "BMW"];   // Allowed
const cars = ["Volvo", "BMW"];   // Not allowed
var cars = ["Volvo", "BMW"];     // Not allowed
cars = ["Volvo", "BMW"];         // Not allowed

{
  const cars = ["Volvo", "BMW"]; // Allowed
  const cars = ["Volvo", "BMW"]; // Not allowed
  var cars = ["Volvo", "BMW"];   // Not allowed
  cars = ["Volvo", "BMW"];       // Not allowed
}
```

Redeclaring an array with `const`, in another scope, or in another block, is allowed:

### Example
```javascript
const cars = ["Volvo", "BMW"];   // Allowed
{
  const cars = ["Volvo", "BMW"]; // Allowed
}
{
  const cars = ["Volvo", "BMW"]; // Allowed
}
```

## Conclusion

The `const` keyword is a powerful tool in JavaScript, especially when working with arrays. By understanding how constant arrays work and their limitations, you can write cleaner, more effective code. Keep exploring and learning!

---

# JavaScript Date Objects

JavaScript Date Objects allow us to work with dates. When you create a new date, it might look like this:

```
Tue Oct 08 2024 15:01:51 GMT-0300 (Argentina Standard Time)
```

## Examples

```javascript
const d1 = new Date(); // Current date and time
const d2 = new Date("2022-03-25"); // Specific date
```

### Note
Date objects are **static**. The "clock" is not "running." The computer clock keeps ticking, but date objects do not update automatically.

## JavaScript Date Output

By default, JavaScript will use the browser's time zone and display a date as a full text string, like this:

```
Tue Oct 08 2024 15:01:51 GMT-0300 (Argentina Standard Time)
```

Later in this tutorial, you will learn more about how to display dates.

## Creating Date Objects

Date objects are created using the `new Date()` constructor. There are several ways to create a new date object:

### Different Ways to Create Date Objects
1. `new Date()`
2. `new Date(date string)`
3. `new Date(year, month)`
4. `new Date(year, month, day)`
5. `new Date(year, month, day, hours)`
6. `new Date(year, month, day, hours, minutes)`
7. `new Date(year, month, day, hours, minutes, seconds)`
8. `new Date(year, month, day, hours, minutes, seconds, ms)`
9. `new Date(milliseconds)`

### Using `new Date()`
`new Date()` creates a date object with the current date and time.

#### Example
```javascript
const d = new Date();
```

### Using `new Date(date string)`
`new Date(date string)` creates a date object from a date string.

#### Examples
```javascript
const d1 = new Date("October 13, 2014 11:13:00");
const d2 = new Date("2022-03-25");
```

### Note on Date Strings
Date string formats will be discussed in the next chapter.

### Using `new Date(year, month, ...)`
You can create a date object with a specified date and time by providing year, month, day, and so on.

#### Example
```javascript
const d = new Date(2018, 11, 24, 10, 33, 30, 0);
```

### Important Note
JavaScript counts months from 0 to 11, meaning January is 0 and December is 11. 

#### Example
```javascript
const d = new Date(2018, 15, 24, 10, 33, 30); // This is treated as March 24, 2019
```

### Overflowing Dates
If you specify a day higher than the maximum for that month, JavaScript will not throw an error; it will simply adjust the date:

```javascript
const d = new Date(2018, 5, 35, 10, 33, 30); // Treated as July 5, 2018
```

### Using 6, 5, 4, 3, 2, or 1 Numbers
- **6 numbers**: year, month, day, hour, minute, second
    ```javascript
    const d = new Date(2018, 11, 24, 10, 33, 30);
    ```

- **5 numbers**: year, month, day, hour, minute
    ```javascript
    const d = new Date(2018, 11, 24, 10, 33);
    ```

- **4 numbers**: year, month, day, hour
    ```javascript
    const d = new Date(2018, 11, 24, 10);
    ```

- **3 numbers**: year, month, day
    ```javascript
    const d = new Date(2018, 11, 24);
    ```

- **2 numbers**: year, month
    ```javascript
    const d = new Date(2018, 11);
    ```

- **1 number**: If you supply only one parameter, it will be treated as milliseconds.
    ```javascript
    const d = new Date(2018); // January 1, 2018
    ```

### Previous Century
One and two-digit years will be interpreted as 19xx:

#### Example
```javascript
const d1 = new Date(99, 11, 24); // December 24, 1999
const d2 = new Date(9, 11, 24); // December 24, 2009
```

## JavaScript Stores Dates as Milliseconds

JavaScript stores dates as the number of milliseconds since January 01, 1970.

- Zero time is: **January 01, 1970 00:00:00 UTC**.
- One day (24 hours) equals **86,400,000 milliseconds**.

Now, the current time might be represented as `1728410511980` milliseconds past January 01, 1970.

### Using `new Date(milliseconds)`
`new Date(milliseconds)` creates a new date object based on milliseconds since January 01, 1970.

#### Examples
- **Plus 100,000,000,000 milliseconds**:
    ```javascript
    const d = new Date(100000000000); // This will be some date in the future
    ```

- **Minus 100,000,000,000 milliseconds**:
    ```javascript
    const d = new Date(-100000000000); // This will be some date in the past
    ```

- **Plus 24 hours**:
    ```javascript
    const d = new Date(24 * 60 * 60 * 1000); // This will be January 2, 1970
    ```

- **Plus 0 milliseconds**:
    ```javascript
    const d = new Date(0); // This will be January 01, 1970
    ```

## Date Methods

Once a date object is created, several methods allow you to manipulate it. These methods enable you to get and set the year, month, day, hour, minute, second, and millisecond of date objects, using either local time or UTC (Coordinated Universal Time).

### Example of Date Methods
You will learn more about date methods and time zones in the upcoming chapters.

## Displaying Dates

JavaScript will output dates using the `toString()` method by default. This is a string representation of the date, including the time zone. The format is specified in the ECMAScript specification:

### Example
```javascript
// Output might look like:
Tue Oct 08 2024 15:01:51 GMT-0300 (Argentina Standard Time)
```

When you display a date object in HTML, it is automatically converted to a string using the `toString()` method:

```javascript
const d = new Date();
d.toString();
```

### Other Methods for Displaying Dates
- The `toDateString()` method converts a date to a more readable format:
    ```javascript
    const d = new Date();
    d.toDateString();
    ```

- The `toUTCString()` method converts a date to a string using the UTC standard:
    ```javascript
    const d = new Date();
    d.toUTCString();
    ```

- The `toISOString()` method converts a date to a string using the ISO standard:
    ```javascript
    const d = new Date();
    d.toISOString();
    ```

## Conclusion

Understanding JavaScript Date Objects is essential for managing and displaying dates in your applications. As you progress through this roadmap, you'll learn more about manipulating dates effectively.

---

# JavaScript Date Formats

When working with dates in JavaScript, it’s essential to understand how they are represented and handled. Imagine dates as time labels on a production line: they need to be precise and easy to interpret. Below, we will explore the different input and output formats for dates in JavaScript.

## JavaScript Date Input

There are generally three types of JavaScript date input formats:

| Type         | Example               |
|--------------|----------------------|
| ISO Date     | "2015-03-25"         |
| Short Date   | "03/25/2015"         |
| Long Date    | "Mar 25 2015" or "25 Mar 2015" |

### ISO Format

The ISO format follows a strict standard in JavaScript, much like a manual that everyone should follow. It is the recommended format and is presented as `YYYY-MM-DD` (Year-Month-Day). For example:

```javascript
const d = new Date("2015-03-25");
```

### Short Dates

Short dates typically have the format "MM/DD/YYYY". This format might be more familiar to those used to writing dates this way:

```javascript
const d = new Date("03/25/2015");
```

### Long Dates

Long dates are usually written in the "MMM DD YYYY" format, where "MMM" represents the month in abbreviated form (e.g., "Mar" for March):

```javascript
const d = new Date("Mar 25 2015");
```

## JavaScript Date Output

Regardless of the input format, JavaScript will, by default, display dates in a full text string format:

```
Tue Oct 08 2024 15:02:46 GMT-0300 (Argentina Standard Time)
```

### JavaScript ISO Dates

ISO 8601 is the international standard for the representation of dates and times. Using this format ensures that your dates are interpreted consistently.

#### Example (Complete Date)

```javascript
const d = new Date("2015-03-25");
```

Keep in mind that the computed date will be relative to your time zone. Depending on your location, the result could vary between March 24 and March 25.

#### ISO Dates (Year and Month)

You can write ISO dates without specifying the day:

```javascript
const d = new Date("2015-03");
```

In this case, the result could vary between February 28 and March 01, depending on the time zone.

#### ISO Dates (Only Year)

It’s also possible to write ISO dates with just the year:

```javascript
const d = new Date("2015");
```

This could result in dates ranging between December 31, 2014, and January 01, 2015.

#### ISO Dates (Date-Time)

ISO dates can include hours, minutes, and seconds:

```javascript
const d = new Date("2015-03-25T12:00:00Z");
```

In this format, "T" separates the date and time, and "Z" indicates that it is in UTC time.

If you want to adjust the time relative to UTC, you can remove the "Z" and add `+HH:MM` or `-HH:MM`:

```javascript
const d = new Date("2015-03-25T12:00:00-06:30");
```

### Time Zones

When setting a date without specifying the time zone, JavaScript will use the browser's time zone. For example, if a user browses from Central US, a date/time created in GMT will be converted to CDT.

## JavaScript Short Dates

Short dates are written using the "MM/DD/YYYY" syntax:

```javascript
const d = new Date("03/25/2015");
```

**Warnings:**
- In some browsers, months or days without leading zeros may cause errors:

```javascript
const d = new Date("2015-3-25"); // May fail
```

- The behavior of "YYYY/MM/DD" is undefined, and some browsers may guess the format or return NaN:

```javascript
const d = new Date("2015/03/25"); // Undefined
```

- The behavior of "DD-MM-YYYY" is also undefined:

```javascript
const d = new Date("25-03-2015"); // Undefined
```

## JavaScript Long Dates

Long dates are often written in the "MMM DD YYYY" format:

```javascript
const d = new Date("Mar 25 2015");
```

The month and day can be in any order:

```javascript
const d = new Date("25 Mar 2015");
```

The month can be written in full (January) or abbreviated (Jan):

```javascript
const d = new Date("January 25 2015");
const d = new Date("Jan 25 2015");
```

Commas are ignored, and names are case insensitive:

```javascript
const d = new Date("JANUARY, 25, 2015");
```

## Date Input - Parsing Dates

If you have a valid date string, you can use the `Date.parse()` method to convert it to milliseconds. This is like using a stopwatch that counts from a specific moment (January 1, 1970).

```javascript
let msec = Date.parse("March 21, 2012");
```

Then, you can use the number of milliseconds to convert it to a date object:

```javascript
const d = new Date(msec);
```

## Conclusion

Understanding date formats in JavaScript is essential for effectively working with temporal data. The analogies and technical concepts presented here are valuable tools on your path to becoming a frontend expert.

---

# JavaScript Get Date Methods

## The new Date() Constructor

In JavaScript, date objects are created with the `new Date()` constructor, similar to opening a diary to jot down the current date and time. When you use `new Date()`, it returns a date object reflecting the current date and time, just like writing today’s date in your diary.

### Get the Current Time

```javascript
const date = new Date();
```

This simple line retrieves the current date and time.

## Date Get Methods

JavaScript provides several methods to extract specific information from date objects. Think of these methods as tools in a toolbox, each designed to retrieve a particular piece of information about the date:

| Method             | Description                                        |
|--------------------|----------------------------------------------------|
| `getFullYear()`    | Get year as a four-digit number (yyyy)           |
| `getMonth()`       | Get month as a number (0-11)                     |
| `getDate()`        | Get day as a number (1-31)                       |
| `getDay()`         | Get weekday as a number (0-6)                    |
| `getHours()`       | Get hour (0-23)                                   |
| `getMinutes()`     | Get minute (0-59)                                 |
| `getSeconds()`     | Get second (0-59)                                 |
| `getMilliseconds()` | Get millisecond (0-999)                           |
| `getTime()`        | Get time in milliseconds since January 1, 1970   |

### Note 1

The get methods above return local time, like reading the time on your watch set to your local timezone. Universal time (UTC) is documented at the bottom of this page.

### Note 2

These get methods return information from existing date objects. In a date object, the time is static, like a photograph capturing a single moment. The "clock" is not "running," and the time in a date object is NOT the same as the current time.

## The getFullYear() Method

The `getFullYear()` method returns the year of a date as a four-digit number:

```javascript
const d = new Date("2021-03-25");
console.log(d.getFullYear()); // 2021

const d = new Date();
console.log(d.getFullYear()); // Current year
```

### Warning!

Old JavaScript code might use the non-standard method `getYear()`, which is supposed to return a two-digit year. However, `getYear()` is deprecated, meaning you should avoid using it—like using outdated technology that could break anytime.

## The getMonth() Method

The `getMonth()` method returns the month of a date as a number (0-11). Here’s where things get interesting! In JavaScript, January is month number 0, February is 1, and so on, until December, which is 11. 

```javascript
const d = new Date("2021-03-25");
console.log(d.getMonth()); // 2 (March)

const d = new Date();
console.log(d.getMonth()); // Current month
```

### Note

To get the month name, you can use an array of month names:

```javascript
const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
const d = new Date("2021-03-25");
let monthName = months[d.getMonth()];
console.log(monthName); // March
```

## The getDate() Method

The `getDate()` method returns the day of a date as a number (1-31):

```javascript
const d = new Date("2021-03-25");
console.log(d.getDate()); // 25

const d = new Date();
console.log(d.getDate()); // Current day
```

## The getHours() Method

The `getHours()` method returns the hours of a date as a number (0-23):

```javascript
const d = new Date("2021-03-25");
console.log(d.getHours()); // 0 (midnight)

const d = new Date();
console.log(d.getHours()); // Current hour
```

## The getMinutes() Method

The `getMinutes()` method returns the minutes of a date as a number (0-59):

```javascript
const d = new Date("2021-03-25");
console.log(d.getMinutes()); // 0

const d = new Date();
console.log(d.getMinutes()); // Current minute
```

## The getSeconds() Method

The `getSeconds()` method returns the seconds of a date as a number (0-59):

```javascript
const d = new Date("2021-03-25");
console.log(d.getSeconds()); // 0

const d = new Date();
console.log(d.getSeconds()); // Current second
```

## The getMilliseconds() Method

The `getMilliseconds()` method returns the milliseconds of a date as a number (0-999):

```javascript
const d = new Date("2021-03-25");
console.log(d.getMilliseconds()); // 0

const d = new Date();
console.log(d.getMilliseconds()); // Current milliseconds
```

## The getDay() Method

The `getDay()` method returns the weekday of a date as a number (0-6). In JavaScript, the first day of the week (day 0) is Sunday. Some countries consider Monday as the first day of the week.

```javascript
const d = new Date("2021-03-25");
console.log(d.getDay()); // 4 (Thursday)

const d = new Date();
console.log(d.getDay()); // Current weekday
```

### Note

You can use an array of names to return the weekday as a name:

```javascript
const days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
const d = new Date("2021-03-25");
let dayName = days[d.getDay()];
console.log(dayName); // Thursday
```

## The getTime() Method

The `getTime()` method returns the number of milliseconds since January 1, 1970:

```javascript
const d = new Date("1970-01-01");
console.log(d.getTime()); // 0

const d = new Date("2021-03-25");
console.log(d.getTime()); // Milliseconds since 1970
```

## The Date.now() Method

`Date.now()` returns the number of milliseconds since January 1, 1970, much like a timer running since a specific point in time:

```javascript
let ms = Date.now();
console.log(ms); // Current milliseconds since 1970
```

You can also calculate the number of years since January 1, 1970:

```javascript
const minute = 1000 * 60;
const hour = minute * 60;
const day = hour * 24;
const year = day * 365;

let years = Math.round(Date.now() / year);
console.log(years); // Years since 1970
```

### Note

`Date.now()` is a static method of the Date object. You cannot use it on a date object like `myDate.now()`. The syntax is always `Date.now()`.

## UTC Date Get Methods

JavaScript also provides UTC date methods, which use UTC time (Coordinated Universal Time). UTC time is the same as GMT (Greenwich Mean Time), but the difference between local time and UTC time can be up to 24 hours.

| Method                   | Same As              | Description                     |
|--------------------------|----------------------|---------------------------------|
| `getUTCDate()`           | `getDate()`          | Returns the UTC date            |
| `getUTCFullYear()`       | `getFullYear()`      | Returns the UTC year            |
| `getUTCMonth()`          | `getMonth()`         | Returns the UTC month           |
| `getUTCDay()`            | `getDay()`           | Returns the UTC day             |
| `getUTCHours()`          | `getHours()`         | Returns the UTC hour            |
| `getUTCMinutes()`        | `getMinutes()`       | Returns the UTC minutes         |
| `getUTCSeconds()`        | `getSeconds()`       | Returns the UTC seconds         |
| `getUTCMilliseconds()`    | `getMilliseconds()`   | Returns the UTC milliseconds     |

## The getTimezoneOffset() Method

The `getTimezoneOffset()` method returns the difference (in minutes) between local time and UTC time:

```javascript
let diff = d.getTimezoneOffset();
console.log(diff); // Difference in minutes
```

---

# JavaScript Set Date Methods

In JavaScript, you can use several methods to set specific parts of a date, such as the year, month, day, hour, minutes, seconds, and milliseconds. These methods allow you to modify a date according to your needs.

## Set Date Methods
The "set" methods in JavaScript allow you to change specific parts of a date object:

| Method               | Description                                                |
|----------------------|------------------------------------------------------------|
| `setDate()`          | Set the day of the month (1-31)                             |
| `setFullYear()`      | Set the year (optionally month and day)                     |
| `setHours()`         | Set the hour (0-23)                                         |
| `setMilliseconds()`  | Set the milliseconds (0-999)                                |
| `setMinutes()`       | Set the minutes (0-59)                                      |
| `setMonth()`         | Set the month (0-11)                                        |
| `setSeconds()`       | Set the seconds (0-59)                                      |
| `setTime()`          | Set the time in milliseconds since January 1, 1970          |

### **Analogy:**
Imagine you have a paper calendar and you want to change any detail of an appointment you already wrote down—like the day, hour, month, or even the year. JavaScript's "set" methods do the same thing, allowing you to modify specific parts of an existing date.

## The `setFullYear()` Method
The `setFullYear()` method sets the year of a date object.

### Example:
```javascript
const d = new Date();
d.setFullYear(2020);
```

This code changes the year of the current date to 2020.

### **Analogy:**
It’s like grabbing a page from your calendar and, instead of scratching out the entire date, you just change the year while leaving the rest as it is. In this case, you're changing the year to 2020, but the month and day remain the same.

This method can also optionally set the month and day:

### Example:
```javascript
const d = new Date();
d.setFullYear(2020, 11, 3);  // Year 2020, December 3
```

### **Extended Analogy:**
Now, not only do you change the year, but you also decide to move the date to a specific month (in this case, December, since months start at 0) and a specific day (the 3rd). It's like adjusting multiple details of your appointment on the calendar, not just the year.

## The `setMonth()` Method
The `setMonth()` method sets the month of a date object.

### Example:
```javascript
const d = new Date();
d.setMonth(11);  // December, because months start at 0
```

### **Analogy:**
Think of this as flipping through your calendar and changing the month of your appointment. You swap from the November page to the December page. Remember that in JavaScript, months start at 0, so 0 is January and 11 is December.

## The `setDate()` Method
The `setDate()` method sets the day of the month.

### Example:
```javascript
const d = new Date();
d.setDate(15);  // Sets the date to the 15th of the current month
```

### **Analogy:**
Imagine you already have an appointment on your calendar, but you want to move it to another day within the same month. You simply erase the old day and write down the new one, for example, moving it from the 1st to the 15th.

You can also use this method to **add days to a date**:

### Example:
```javascript
const d = new Date();
d.setDate(d.getDate() + 50);  // Adds 50 days to the current date
```

### **Analogy:**
Instead of picking an exact day, you decide to move your appointment forward by 50 days. If this shift takes the date into a different month or year, JavaScript automatically adjusts it, just like flipping forward through your calendar.

## The `setHours()` Method
The `setHours()` method sets the hours of a date object.

### Example:
```javascript
const d = new Date();
d.setHours(22);  // Sets the time to 10 PM
```

### **Analogy:**
This is like changing the time of a meeting in your schedule. You move it from the morning to the evening and write down 10 PM.

## The `setMinutes()` Method
The `setMinutes()` method sets the minutes of a date object.

### Example:
```javascript
const d = new Date();
d.setMinutes(30);  // Sets the minutes to 30
```

### **Analogy:**
It’s like fine-tuning the time of your appointment. For example, instead of having it at exactly 10:00, you change it to 10:30.

## The `setSeconds()` Method
The `setSeconds()` method sets the seconds of a date object.

### Example:
```javascript
const d = new Date();
d.setSeconds(30);  // Sets the seconds to 30
```

### **Analogy:**
If you were extremely precise with your scheduling, you could even adjust the exact seconds of an event. In this case, you decide that something will happen 30 seconds into the minute.

## Comparing Dates
You can easily compare dates in JavaScript to see which one comes before or after the other.

### Example:
```javascript
let text = "";
const today = new Date();
const someday = new Date();
someday.setFullYear(2100, 0, 14);  // Sets the date to January 14, 2100

if (someday > today) {
  text = "Today is before January 14, 2100.";
} else {
  text = "Today is after January 14, 2100.";
}
```

This code compares today's date to January 14, 2100, and tells you if today is before or after that date.

### **Analogy:**
Imagine you have two appointments on your calendar and you want to know which one comes first. You simply compare the two dates and decide which one is earlier. JavaScript lets you do the same thing by comparing two date objects to see which is "earlier" or "later."

## Note on JavaScript Months
Remember that JavaScript counts months from 0 to 11: January is 0, and December is 11. This is important to keep in mind when working with dates.

### **Analogy:**
It’s like having a row of numbered lockers where the first locker is labeled 0, not 1. So, if you’re looking for "January," instead of going to locker 1, you need to look in locker 0.

---

