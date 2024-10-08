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

