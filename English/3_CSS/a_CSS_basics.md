# CSS Box Model Explained through Analogies

In this article, I'll break down the **CSS Box Model**, a core concept in web development, using simple analogies. Understanding this model will help you design layouts more effectively, ensuring that your content fits perfectly within its container. Ready? Let's dive in!

## The Box Model: Understanding the Structure

Imagine a framed painting hanging on the wall. The **Box Model** is like that frame, with multiple layers surrounding the artwork. Just like a painting has the artwork, the matting, and the frame, the box model consists of different layers that define how elements appear on the web page.

### Layers of the Box Model:

- **Content Box**: This is like the artwork itself—the main content (e.g., text or image).
- **Padding Box**: This is the space between the artwork and the frame (the matting). It creates a cushion around your content.
- **Border Box**: The frame of the painting that provides a visible boundary.
- **Margin Box**: The empty space between the frames on a wall. This is the space between elements on a webpage.

Here's an example to make it clearer:

```html
<p>I am a paragraph of text.</p>
```

With the following CSS:

```css
p {
  width: 100px;
  height: 50px;
  padding: 20px;
  border: 1px solid;
}
```

You would expect the paragraph to be 100px wide, but the actual width becomes 142px. Why? The padding and border add extra space to the content, just like the frame adds to the dimensions of a painting.

## Controlling Box Sizing: Extrinsic vs. Intrinsic

In CSS, you can control how much space an element takes up using **extrinsic sizing** or **intrinsic sizing**.

### Extrinsic Sizing (You Control It)

Think of a fixed-size picture frame. No matter how large the artwork is, the frame stays the same size, causing the artwork to overflow if it's too big. This is what happens with extrinsic sizing when you set a specific width or height. Here's an example:

```css
p {
  width: 100px;
  height: 50px;
}
```

This controls the size, but if the content (like text) overflows, it can break out of the box.

### Intrinsic Sizing (Content Controls It)

Now imagine you have a flexible frame that adjusts to the size of the artwork. This is intrinsic sizing. The browser automatically sizes the box to fit the content inside. You can achieve this in CSS by not specifying a fixed size, or using `min-content`, which lets the content define its minimum size.

Example:

```css
p {
  width: min-content;
}
```

In this case, the box will resize to fit around the content, preventing overflow.

## Debugging the Box Model

When things don't fit as expected, you can use **browser DevTools** to inspect the box model. This will show you the content, padding, border, and margin in a visual way, helping you debug issues.

### Example Debugging Steps:
1. Open DevTools (usually by right-clicking on the page and selecting "Inspect").
2. Select the element you want to examine.
3. Look at the box model section to see how each layer affects the overall size.

## Box-Sizing Property: Content-Box vs. Border-Box

By default, the `box-sizing` property is set to `content-box`. This means the width and height you set are applied to the **content** only, and padding and border are added on top of it.

Example:

```css
.my-box {
  width: 200px;
  border: 10px solid;
  padding: 20px;
}
```

Here, the total width of `.my-box` will be 260px (200px content + 40px padding + 20px border).

However, you can use the `border-box` model to make things easier. With `box-sizing: border-box`, the width and height include the padding and border, making the size more predictable.

Example:

```css
.my-box {
  box-sizing: border-box;
  width: 200px;
  border: 10px solid;
  padding: 20px;
}
```

Now the box will be exactly 200px wide, including the border and padding!

## The Ultimate Analogy

Let's go back to the painting analogy:

- The **content box** is your artwork.
- The **padding box** is the matting (the space between the artwork and the frame).
- The **border box** is the frame itself.
- The **margin box** is the space between paintings on the wall.

If the artwork gets too large, like a big painting not fitting inside the frame, it spills over. That's the same as text overflowing out of its container in CSS!

By understanding these concepts, you’ll be able to manage your layouts with precision and avoid unexpected behavior in your web designs.

---

# CSS Selectors Explained with Analogies

In this article, we're going to explore **CSS Selectors** using simple analogies to make the concepts easier to grasp. While CSS can sometimes seem complicated, it's a lot like giving specific instructions to elements on a webpage, similar to telling members of a sports team where to go and what to do.

---

## What Are Selectors?

Imagine you're the coach of a sports team, and you're giving instructions to your players. You might say, "The first player on the field should wear a red jersey," or "All players in position B should stay behind the line." CSS selectors work the same way—you're telling different parts of your website how to behave.

Let's say you've got some text on your webpage, and you only want the **first paragraph** of an article to be larger and red. You'd write the following code:

```html
<article>
  <p>I want to be red and larger than the other text.</p>
  <p>I want to be normal-sized and the default color.</p>
</article>
```

To apply the styling to just the **first** paragraph, you'd use this selector:

```css
article p:first-of-type {
  color: red;
  font-size: 1.5em;
}
```

In this example, you're like the coach saying, "First player on the field, you're special—wear red and stand out!"

---

## Parts of a CSS Rule

Think of a **CSS rule** as an instruction you give to your players:

1. **Selector**: Who are you talking to? (e.g., all players, or a specific player)
2. **Declaration**: What should they do? (e.g., wear a red jersey)

A CSS rule looks like this:

```css
.my-css-rule {
  color: blue;
  font-size: 16px;
}
```

- **Selector**: `.my-css-rule` (you're talking to anyone with the class `my-css-rule`)
- **Declarations**: 
  - `color: blue;` (make your text blue)
  - `font-size: 16px;` (set your font size to 16px)

---

## Simple Selectors

### 1. Universal Selector

Imagine telling **everyone** on your team, "Wear red shoes." That’s what the universal selector `*` does:

```css
* {
  color: hotpink;
}
```

This makes **every single element** on your page hot pink. It’s like telling the entire team to follow the same rule.

---

### 2. Type Selector

The **type selector** is like saying, "Every goalie should stand near the goal." You're selecting by the player's **position**.

```css
section {
  padding: 2em;
}
```

This selector targets every `<section>` element, like saying, "All goalies, follow this rule."

---

### 3. Class Selector

A **class selector** is like grouping certain players and giving them the same instruction. For example, telling all defenders to stand in a line:

```css
.my-class {
  color: red;
}
```

Any element with the class `my-class` will turn red. Whether it's a `<div>`, `<button>`, or `<p>`, if it has the class `my-class`, it's following the rule.

---

### 4. ID Selector

An **ID selector** is like singling out **one player** on your team and giving them a special instruction. Since each player can only have one unique jersey number (ID), each webpage element should have a unique ID.

```css
#rad {
  border: 1px solid blue;
}
```

In this case, you’re telling one specific player to wear a blue border.

---

### 5. Attribute Selector

Imagine you need to select players based on something specific, like their shoe brand. The **attribute selector** does just that:

```css
[data-type='primary'] {
  color: red;
}
```

This rule looks for any element with the `data-type='primary'` attribute, like checking for players who wear a specific brand of shoes.

---

## Pseudo-classes and Pseudo-elements

### 1. Pseudo-classes

Sometimes, you want to apply rules based on **state**—like telling players to move when the ball is in play. For example, if you hover over a link, it changes color:

```css
a:hover {
  color: green;
}
```

This is like saying, "When you point at this player, they should change their behavior."

---

### 2. Pseudo-elements

Pseudo-elements are a little different—they're like saying, "Put a flag in front of every player." They allow you to insert content before or after elements:

```css
.my-element::before {
  content: 'Prefix - ';
}
```

In this case, you're placing a prefix before every `.my-element`.

---

## Complex Selectors

Sometimes you need to get more specific, just like in sports when you might say, "Only pass to the defender **immediately** next to you." This is where **combinators** come in.

### 1. Descendant Combinator

Imagine you’re selecting all defenders who are **children** of another player:

```css
p strong {
  color: blue;
}
```

This makes every `<strong>` tag inside a `<p>` element blue, just like telling all defenders inside a specific zone to follow the rule.

---

### 2. Next Sibling Combinator

This combinator is like saying, "Pass the ball to the **next player** in line." You use `+` to select the next sibling element:

```css
h1 + p {
  margin-top: 1em;
}
```

This adds space only to the `<p>` element that immediately follows an `<h1>`.

---

# The Cascade in CSS

## Introduction to the Cascade

CSS stands for Cascading Style Sheets, and the cascade is an essential algorithm used to determine which styles are applied to elements when multiple rules conflict. Think of it as a referee in a game—there are many players (CSS rules), but only one can win and be applied. The "cascade" decides which player wins based on a combination of factors like order of appearance, specificity, origin, and importance.

### Key Concept: Conflict Resolution

Imagine you have two coaches telling a player (an HTML element) to wear different colored jerseys (styles). One says "red" and the other says "blue". Who does the player listen to? The cascade is what makes this decision. In the following code, the second rule takes precedence simply because it comes last.

```css
button {
  color: red;
}

button {
  color: blue;
}
```

Here, the button will be blue because the second rule overwrites the first due to its later position in the stylesheet.

---

## Breaking Down the Cascade

The cascade algorithm can be broken down into **four stages**:

1. **Position and Order of Appearance**
2. **Specificity**
3. **Origin**
4. **Importance**

Let's walk through each stage using an analogy, so you can grasp the concept easily while understanding the underlying technicalities.

---

### 1. Position and Order of Appearance

Think of the cascade like a queue at a concert. Whoever gets in line last gets to be in front. Similarly, CSS rules that appear later in the stylesheet override earlier ones if they have the same specificity.

#### Example:

```css
.my-element {
  background: green;
  background: purple;
}
```

In this case, the background will be purple because it appears last. This concept also applies across different CSS sources like `<link>` and `<style>` elements. Styles that appear further down the page or later in the stylesheet will "win" over earlier ones.

#### Analogy: Who Speaks Last, Wins

Imagine two people arguing about what color to paint a room. The person who gets the last word in the conversation decides the final color. In CSS, it's exactly the same with styles—whoever speaks last gets to paint the room.

---

### 2. Specificity

Specificity is like ranking different kinds of suggestions on how to solve a problem. Some suggestions carry more weight than others. For example, CSS targeting an **ID** has more weight than one targeting a **class** or a **tag**.

#### Example:

```html
<h1 class="my-element">Heading</h1>
```

```css
.my-element {
  color: red;
}

h1 {
  color: blue;
}
```

Even though both rules target the `h1` element, the class selector `.my-element` has higher specificity, so the text will be red. Specificity is cumulative, so combining multiple selectors like `a.my-class.another-class[href]:hover` makes the rule even harder to override.

#### Analogy: Power of Influence

Imagine you’re in a classroom, and the teacher (ID selector) tells you to read a book. Later, a classmate (class selector) suggests you watch a movie instead. Even though the classmate gave you a suggestion last, you listen to the teacher because their instruction carries more weight.

---

### 3. Origin

CSS doesn't just come from your stylesheet. It can also originate from:

- **User agent styles** (default browser styles)
- **User custom styles** (from browser extensions or the operating system)
- **Authored styles** (the CSS you write)

These different origins have a hierarchy. Styles that come from the browser itself are the least specific, while user-defined or authored `!important` rules carry the most weight.

#### Example:

```css
/* User-agent style */
h1 { margin-block-start: 0.83em; }

/* Authored style */
h1 { margin-block-start: 2ch; }

@media (max-width: 480px) {
  h1 { margin-block-start: 1ch; }
}

/* User custom style */
h1 { margin-block-start: 2rem !important; }
```

In this case, the `!important` user custom style will win, and the margin will be `2rem`, even though there are other styles declared for `h1`.

#### Analogy: Different Authorities

Consider CSS origins like different levels of authority in a city: the local government (browser default styles), the state government (user custom styles), and the federal government (authored CSS). In the end, a federal mandate marked "urgent" (`!important`) will override any other lower-level decisions.

---

### 4. Importance

Not all rules are created equal. Some rules have more "importance" than others. The `!important` rule is a way to forcefully override all other rules, including those that may be more specific or come later in the stylesheet.

However, there's a catch. **Active animations** or **transitions** have even higher importance than `!important` rules. This ensures that visual changes continue smoothly, even if there's a conflict with a high-specificity rule.

#### Example:

```css
button {
  background: yellow !important;
  transition: background 0.5s ease;
}
```

Even though the `background: yellow` has the `!important` flag, if the button has an active transition, it might temporarily override this due to the higher importance of the transition rule.

#### Analogy: The Emergency Override

Imagine you're in a building with a strict "No Exit" policy. However, if the fire alarm goes off (an active animation or transition), even the strictest rule (`!important`) gets overridden for safety reasons.

---

## Conclusion: The Cascade in Action

The cascade is a powerful algorithm that makes sure there’s always a final style applied to every element. By understanding how position, specificity, origin, and importance interact, you can predict and control how your CSS is applied.

### Key Takeaways:

- **Position matters:** Last rule wins if specificity is the same.
- **Specificity matters more:** The more specific rule wins.
- **Origin hierarchy:** Browser styles < User styles < Your styles.
- **Importance trumps all:** `!important` beats everything except active animations or transitions.

By mastering the cascade, you’ll be well on your way to writing more effective and predictable CSS!

---

# The Cascade in CSS

- **Position:** The last rule wins.
- **Specificity:** The more specific rule wins.
- **Origin:** Browser < User < Author.
- **Importance:** `!important` beats everything except animations/transitions.

CSS is all about resolving conflicts and applying the correct styles. Understanding the cascade helps you take full control over your designs.

---

# Understanding Specificity in CSS

## What is Specificity?

Imagine you're cooking a meal for a group of people. You ask, “What should I make for dinner?” and you get different suggestions. Someone says, “Pasta,” another suggests “Pizza,” and a third person insists on “Salad.” Now, how do you decide which one to cook? You might prioritize based on who requested it (e.g., if your best friend or the chef in the house made a request). 

This is similar to how CSS (Cascading Style Sheets) works with conflicting styles. When different CSS rules apply to the same HTML element, CSS needs to determine which rule to follow. This decision-making process is guided by **specificity**.

In our example:

```html
<button class="branding">Hello, Specificity!</button>
```

```css
button {
  color: red;
}

.branding {
  color: blue;
}
```

We have two conflicting rules: One wants the button text to be red and the other wants it blue. Which one does CSS choose? The answer lies in **specificity**—which rule is more specific.

---

## Specificity Scoring: Think of it Like Points

Every CSS rule has a specificity score, which is like a total number of points. The rule with the highest points wins and gets applied.

### Rule of Thumb
- The **lower** the specificity score, the easier it is to manage your CSS over time.
- High specificity makes it difficult to override rules in the future.

Let’s break down how CSS scores these points.

### Scoring the Selectors

Each type of selector in CSS has a different score:

1. **Universal Selector (`*`)**: 0 points (it's like a suggestion that anyone can override)
2. **Element or Pseudo-Element Selector (`button`, `div`, `::before`)**: 1 point
3. **Class, Pseudo-Class, or Attribute Selector (`.branding`, `:hover`, `[type="button"]`)**: 10 points
4. **ID Selector (`#myButton`)**: 100 points
5. **Inline Style (`style="color:red;"`)**: 1,000 points (the ultimate chef’s decision)
6. **`!important` Rule**: 10,000 points (the master chef overrules all)

---

## Example Time: Scoring Specificity

Consider this CSS and HTML example:

```html
<a class="my-class another-class" href="#">A link</a>
```

### CSS Rules:
1. `a { color: red; }`: This is an element selector. Score: **1 point**.
2. `a.my-class { color: green; }`: Now, we've added a class selector. Score: **11 points** (1 point for `a` + 10 points for `.my-class`).
3. `a.my-class.another-class { color: purple; }`: Another class! Score: **21 points**.
4. `a.my-class.another-class[href] { color: goldenrod; }`: We added an attribute selector. Score: **31 points** (1 point for `a` + 20 points for two classes + 10 points for the attribute).
5. `a.my-class.another-class[href]:hover { color: lightgrey; }`: Add a pseudo-class. Score: **41 points** (1 + 20 + 10 + 10).

In each step, we increased the specificity score, meaning the higher the score, the more "specific" or stronger the rule becomes.

---

## Increasing Specificity: A Double-Edged Sword

If you need to make a rule stronger, you can repeat selectors. For example, if you want to make sure `.my-button` overrides a conflicting rule, you can write:

```css
.my-button.my-button {
  background: blue;
}
```

This trick doubles the points for the class selector, but beware: If you find yourself doing this often, it could mean you're overcomplicating your CSS. Try simplifying your rules instead of just increasing specificity.

---

## Newer CSS Wins on Ties

If two selectors have the same specificity score, the last one wins. For example:

```css
.my-button {
  background: blue;
}

button {
  background: grey;
}
```

Both rules have the same score, but because `.my-button` comes last, the button will be blue. However, if we switch the order:

```css
button {
  background: grey;
}

.my-button {
  background: blue;
}
```

Now, the button will be grey because the `button` rule comes last and has the same specificity score.

---

## The Specificity Pyramid

Visualize specificity as a pyramid. At the bottom, you have elements (1 point), then classes (10 points), then IDs (100 points), and finally, inline styles and `!important` rules (1,000 and 10,000 points). The higher up the pyramid you go, the harder it is to override the rule.

```
            Inline Styles + !important (10,000)
                ID Selectors (100)
          Class, Pseudo-Class, Attribute (10)
  Element, Pseudo-Element Selectors (1)
       Universal Selector (*) (0)
```

---

## Final Tips

- Keep your CSS **simple**. Aim for lower specificity where possible.
- Use **`!important`** sparingly. It can cause more problems than it solves.
- Organize your styles in a way that makes future changes easier.

Specificity is like a game of who gets the final say. The higher the points, the louder the voice, but don't forget to keep things flexible for future adjustments!

---

# Inheritance in CSS - Understanding with Simple Analogies

## Introduction

Imagine you're in a big family reunion, and everyone seems to have similar traits. Maybe it's the same eye color or a familiar laugh. Just like in families, certain traits in CSS are "inherited" from parent elements to child elements. This concept helps keep our code DRY (Don't Repeat Yourself) by avoiding the need to redefine the same style over and over again.

In this article, we're going to understand the magic of inheritance in CSS, using easy-to-understand analogies and technical concepts.

---

## What is CSS Inheritance?

### The Family Analogy

Picture this: You are part of a family where everyone shares the same last name. You didn't choose it; it was inherited from your parents. Similarly, in CSS, some properties are inherited by child elements from their parent elements without needing to be explicitly defined for each one.

For example:
```html
<html>
  <body>
    <article>
      <p>Welcome to the family of inherited styles.</p>
    </article>
  </body>
</html>
```

Let's say we set a `color` on the `html` element:

```css
html {
  color: lightslategray;
}
```

Here, the `color` property is like the family trait. All child elements, such as `<body>`, `<article>`, and `<p>`, will "inherit" this color unless they explicitly choose their own.

---

## Why Does Inheritance Happen?

### Analogy: Hand-Me-Down Clothes

In some families, older siblings pass down clothes to younger siblings. Unless the younger sibling gets new clothes, they will wear what’s passed down. Similarly, unless we define new styles for child elements, they will use the styles from their parent.

For example:

```html
<article>
  <a href="#" class="my-button">Click me!</a>
</article>
```

CSS:
```css
article a {
  color: maroon;
}

.my-button {
  display: inline-block;
  padding: 1rem 2rem;
  background: pink;
  text-align: center;
}
```

Even though we styled `.my-button`, the link inherits the `color: maroon` from the `article a` rule. It’s like getting hand-me-down clothes—unless we change them, the inherited style stays!

---

## How Does Inheritance Work?

### Inheritance Flow: From Parents to Children

Inheritance in CSS is like a river flowing downstream. Parent elements pass certain properties down to their children. For example:

```html
<html>
  <body>
    <article>
      <p>Lorem ipsum dolor sit amet.</p>
    </article>
  </body>
</html>
```

And the CSS:

```css
html {
  color: lightslategray;
}

body {
  font-size: 1.2em;
}

p {
  font-style: italic;
}
```

- The `color` set on `<html>` cascades down to all elements that can inherit it.
- The `font-size` set on `<body>` applies to `<article>` and `<p>`, but not `<html>` (inheritance doesn’t flow upwards).
- The `font-style` is applied only to `<p>` since it’s specifically defined for it.

### Properties That Are Inherited by Default

Not every CSS property is inherited. Here’s a quick list of common inheritable properties:
- `color`
- `font-family`
- `font-size`
- `line-height`
- `text-align`

Think of these as family traits that are passed down by default.

---

## Managing Inheritance: Controlling What Gets Passed Down

Sometimes you want to break the chain of inheritance. Maybe a child in the family decides to start their own trend! CSS provides three special keywords for this:

### 1. `inherit`

This is like saying, "I’ll take whatever my parent gives me." You can use `inherit` to force an element to take the computed value of its parent.

```css
.my-component strong {
  font-weight: inherit;
}
```

### 2. `initial`

This is like saying, "I don’t want any hand-me-downs; give me the default style!" The `initial` keyword resets a property to its browser-defined default.

```css
aside strong {
  font-weight: initial;
}
```

### 3. `unset`

Think of this as a wildcard. If a property is inherited by default (like `color`), `unset` works like `inherit`. If it’s not inherited by default (like `margin`), `unset` works like `initial`.

```css
aside p {
  margin: unset;
  color: unset;
}
```

---

## Conclusion

Inheritance in CSS helps us write cleaner, more efficient code by allowing certain properties to be passed from parent to child elements. However, it's important to understand when and how to control it using keywords like `inherit`, `initial`, and `unset`. Just like family traits, inheritance can be helpful, but sometimes we need to adjust it to fit specific needs.

By understanding how inheritance works, you can make smarter decisions about your CSS and avoid unexpected results!
```

---

Here's a structured markdown file that integrates the provided article with analogies to make the concepts more understandable:

```markdown
# Color in CSS

## Introduction

Color is an important part of any website, and in CSS, there are many options for color types, functions, and treatments. Just like a painter chooses different types of paint for their canvas, developers must choose the right color methods to bring their web designs to life.

## Numeric Colors

Your first exposure to colors in CSS is likely through **numeric colors**. Think of numeric colors as a recipe where each ingredient represents a primary color: red, green, and blue.

### Hex Colors

```css
h1 {
  color: #b71540;
}
```

**Hexadecimal notation** (or **hex**) is like a shorthand version of the RGB color model. It assigns a numeric value to red, green, and blue. The hex scale runs from 0-9 and A-F, just like a secret code. 

For instance:
- **Black** is `#000000` (no color at all).
- To add transparency (like putting a sheer curtain over a window), you can add two more digits for **alpha** values. For example, to make black 50% transparent, write `#00000080`.

| Alpha Value | Hex Code      | Transparency Level |
|-------------|---------------|--------------------|
| 0%          | #00000000     | Fully transparent   |
| 50%         | #00000080     | Half transparent    |
| 75%         | #000000BF     | Mostly opaque       |

### RGB Colors

```css
h1 {
  color: rgb(183, 21, 64);
}
```

**RGB colors** are defined using the `rgb()` function. You can think of this as mixing paint. The numbers range from 0-255. 

- To create **black**, you need no red, green, or blue: `rgb(0, 0, 0)`.
- For **white**, all colors at full intensity: `rgb(255, 255, 255)`.

You can also define transparency here:
- Using `rgb(0, 0, 0 / 50%)` or `rgba(0, 0, 0, 0.5)` to create semi-transparent colors.

### HSL Colors

```css
h1 {
  color: hsl(344, 79%, 40%);
}
```

**HSL** stands for **Hue, Saturation, and Lightness**. Picture a color wheel where each degree represents a different color:

- **Hue** is like the flavor of your ice cream (chocolate, vanilla, etc.) measured in degrees from 0 to 360.
- **Saturation** is the strength of that flavor; 0% is bland (grayscale) while 100% is the full flavor.
- **Lightness** is the brightness of your flavor; 0% is black, 100% is white.

To create black in HSL, you can write `hsl(0, 0%, 0%)`, where hue doesn't matter since saturation and lightness are both 0.

## Color Keywords

There are **148 named colors** in CSS, which you can think of as a box of crayons. Some favorites include:
- `black`, `white`, `red`, `blue`, and `gray`.

Special keywords also exist:
- `transparent`: like clear glass, fully see-through.
- `currentColor`: this acts like a chameleon, adapting to the text color of its parent element.

## Where to Use Color in CSS

You can use colors in various CSS properties:
- **Text**: `color`, `text-shadow`, and `text-decoration-color`.
- **Background**: `background` or `background-color`.
- **Gradients**: Just like blending two or more paint colors together, gradients accept any color format.
- **Borders**: `border-color` and `outline-color` set the color for borders.

## Check Your Understanding

Test your knowledge of color!

Which of the following are valid colors?
- `rgb(255, 0, 0)` ✅
- `hsl(180deg 50% 50%)` ✅
- `#OOFZ2` ❌ (contains an invalid character)
- `rgba(400 0 1)` ❌ (red value out of range)
- `hotpink` ✅
- `#0f08` ✅

### Spot the Invalid HSL Color
- `hsl(.5turn 40% 60%)`
- `hsl(0, 0, 0)` ❌ (2nd and 3rd values should be percentages)
- `hsl(0 0% 0% / 20%)`
- `hsl(5, 0%, 90%)`
- `hsl(2rad 50% 50%)`

---

