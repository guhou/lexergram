# Lexergram

Lexergram is a tutorial covering the basics of web development using HTML and
CSS. This tutorial is designed to be accessible to audiences that are familiar
with computing concepts and the web, but have no prior experience with web
development. By the end of the tutorial, participants should have gained some
skills to develop web pages with common web technologies and resources.

## HTML

HTML stands for HyperText Markup Language. But what does that mean? Hypertext
means that text is interactive, and can be linked to other pieces of text. With
the web, we can link a piece of text to another section anywhere else in the
world! Markup is a way to describe text- e.g. "this text is a heading", "this
should be a list", etc. We call HTML a _language_ because it is a formal
language that both humans and computers can understand. It has its own syntax,
grammar, vocabulary, and semantics.

### The language of HTML

HTML describes _elements_- these represent the vocabulary of content. Many of
these elements will be familiar- headings, paragraphs, images, and lists. The
type of element is placed between angle brackets `<`, `>`.

In markup languages, the term 'whitespace' refers to spaces, line breaks,
and indentation. In HTML, whitespace is mostly ignored- this makes it easier
to keep our HTML neat, but it also means if we want line breaks, it must be
added as a markup element using, for example, a `<br>` element.
```html
<br>
```

Elements can also be used to describe a section of text. In this case, the
start of the section has a `<tag>` and the end of the section has a closing
tag with a slash- `</tag>`.

Common text elements include paragraphs (`<p>`) and headings. HTML has markup
for six levels of headings, with `<h1>` being the "top-level" heading, all
the way down to `<h6>`. These elements automatically add line spacing above
and below them.
```html
<h1> Cats for Adoption </h1>
<p> We have many cats available for adoption. Please help us find forever homes
for our furry friends. </p>
```

Some elements need some additional information to be provided in order to be
useful. This information is provided in the form of _attributes_. Attributes
are placed inside the starting tag of an element in the format `name="value"`.

Image tags (`<img>`) don't make much sense without an image to show! Reference
the image to display using the source (`src=`) attribute.
```html
<img src="coco.jpg" alt="A photo of Coco, up for adoption">
```

Elements can contain other elements as content- this is very commonly used to
build up the content structure of a whole page. When building structure, make
sure elements tags are properly nested inside each other.

HTML has markup for two main list types: ordered lists (`<ol>`) and unordered
lists (`<ul>`)- roughly speaking, this means 'numbered' or 'unnumbered'. Lists
aren't very useful without something in them, so lists usually have list item
(`<li>`) elements nested inside them.
```html
<ul>
    <li> Whiskas </li>
    <li> Fancy Feast </li>
    <li> Purina </li>
</ul>
```

### Resource: Codepen

[Codepen](https://codepen.io/) is an online editing and sharing tool for HTML,
CSS, and JavaScript. Today, we'll use it to write some HTML and CSS. A great
feature of Codepen is that it shows a live preview of your content as you write
it- this makes it great for experiments and prototypes.

### Resource: Unsplash

[Unsplash](https://unsplash.com/) is a website that has collections of
high-quality, free-to-use photos. For now, we'll use Unsplash to quickly add
some images to our page. Unsplash has a tool called
[Source](https://source.unsplash.com/) which makes this really easy to do.
Let's pick a random photo of the day from Unsplash, using some search keywords
of our choice.

```
https://source.unsplash.com/daily?YOUR_KEYWORD_HERE
https://source.unsplash.com/daily?cats
```

### Exercise 1: Use HTML to author a Lexergram post

Open [Codepen](https://codepen.io/), and create a new Pen from the menu bar.
The editor will show up with 3 editing panes- HTML, CSS, and JS, and a blank
area for displaying your page. For now, we will be working in the HTML area.

Create some HTML elements for a Lexergram post. For now, just focus on writing
the HTML- the page might look a bit strange and ugly, but we will fix that
next.

- make a `<header>` for a top banner
- include a heading with our page title
- create an `<article>` element for the main area of the page
- make some `<section>` elements to represent each post
- include an image
- include a paragraph to caption the image
- include an unordered list of tags to add to the image

```html
<header>
  <h1>Lexergram</h1>
</header>

<article>

  <section>
    <img src="https://source.unsplash.com/daily?cats">

    <p>
      This is my cat. His name is Cookie. He weighs 12kgs and eats prawns.
    </p>

    <ul>
      <li>cats</li>
      <li>catsoflexergram</li>
      <li>meow</li>
    </ul>
  </section>

</article>
```

## CSS

CSS stands for Cascading Style Sheets. In short, they're a way to make our page
look stylish. CSS is a different _language_ to HTML, but shares much of its
vocabulary, such as `h1`, `p`, `li`, `img`, and so on. CSS is made up of
`selectors`, which select elements of HTML to style, and `rules`, which tell
the browser to apply our desired styling.

There many different ways to select elements- the simplest way is to select all
elements that match a particular type. In this case, simply write the name of
the type to select.

```css
article {
  font-size: 12pt;
}

img {
  width: 500px;
}
```

CSS also has the concept of a 'class', which represents an element's purpose
or category. Classes must be manually added to HTML elements as attributes
(e.g. `<ul class="tags">`) but there is a shorthand to reference all elements
with a particular class in CSS by adding a `.` in front of the name.

```css
.tags {
    list-style: none;
}
```

Selectors can be chained together to restrict the scope where they apply- this
is very useful to apply rules only in a specific context. To chain rules, write
the nesting from left-to-right.

```css
ul li {
    display: inline-block;
}
```

### Measurements

A common need in layout is to make elements appear at a certain size, or at a
certain position. Because screen sizes vary wildly, using real-world
units such as millimetres doesn't work very well. Instead, CSS uses
screen-based measurement units, such as pixels (`px`). CSS can also define
measurements in relation to the current font size, the size of surrounding
elements, or the size of the browser window. A full list is available on
[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/length). For
simplicity, we will mostly use pixels today.

### Fonts

To make a web page look more appealing, we often change the font used to
display the text. A web page can use any font installed on the user's computer.
However, relying on a font to be installed is not very flexible, since we must
guess at what fonts will be installed on someone else's computer. In practice,
this limits us to the default fonts preinstalled on all computers- such as
Arial, Times New Roman, or Courier- yuck!

Fortunately, modern browsers support a technology called 'web fonts', which
allow them to dynamically load a font just for a particular page.
[Google Fonts](https://fonts.google.com/) provide a collection of web fonts
that are free to use on any website. Choose one or two fonts on Google Fonts,
and use the embed tool to get a copyable reference to the font bundle.

### Colours (colors)

Describing colour is a surprisingly complex topic, but on the web some simple
colour models are usually used. The simplest colour model is RGB, which
specifies how much red, blue, and green light to mix together to create a
colour on screen. Each colour is given a value between 0 and 255, where 0 is
completely off, and 255 is as bright as possible. All screen colours can be
represented as a combination of red, green, and blue.

```css
/* max red, half green, no blue = orange */
rgb(255, 127, 0)
```

A shorthand way to write colours is to use a hex code- hexadecimal is a
numbering system with a few extra digits A-F, counted like so:
`0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F, 10`. A colour can be written
as a hex code by converting the decimal value to hexadecimal and writing all
three channels together, preceded by a `#`.

```css
/* 255 = FF, 127 = 7F, 0 = 00 */
#FF7F00
```

[Adobe Color](https://color.adobe.com/) is an online colour picker tool to
choose colours and create colour palettes. Adobe Color is a quick way to pick
a few colours that work well together, without messing around with hex codes
too much! Make a palette or choose a predefined palette from the Explore tab.
We'll need to use the RGB values shown below the palette.

Exercise 2: use CSS to apply some layout to our HTML page
    - use a columnar layout with a width
    - add sizing, margins, and padding to image1
    - format list as an inline tag list

### Exercise 2: Add styling to our Lexergram post

-   use CSS `@import url()` too import our web fonts
-   use `font-family:`, `font-size:`, `font-style:` rule to set custom fonts
    for our header and article
-   use `background:` rule to add a background colour to our page
-   use `width:` and `height:` rules to control the size of elements on our
    page
-   use `margin:` and `padding:` to control the spacing around elements
-   use `display: inline-block` and `list-style: none` to reset formatting on
    list items

```css
/* import fonts */
@import url('https://fonts.googleapis.com/css?family=Fira+Sans:300,300i,700|Lobster');
```

```css
/* background styling */
body {
  margin: 0;
  background: #B2AABE;
}
```

```css
/* header styling */
header {
  background: #3D1A71;
}

h1 {
  margin: auto;
  padding: 20px;
  font-family: 'Lobster', cursive;
  font-size: 60px;  
  text-align: center;
  color: #FEFEFE;
}
```

```css
/* style the main body content */
article {
  margin: auto;
  font-family: 'Fira Sans', sans-serif;
  color: #3D1A71;
}
```

```css
/* style our Instagram cards */
section {
  background: #fefefe;
  margin: 20px auto;
  width: 400px;
  padding: 20px;
  box-shadow: 0px 0px 10px 10px rgba(61, 26, 113, 0.5);
}

img {
  width: 400px;
  height: 400px;
  object-fit: cover;
}
```

```css
/* do some fancy tag styling */
ul li {
  display: inline-block;
  list-style: none;
  font-style: italic;
}

/* this is a pseudo-element selector. It finds an element that doesn't really
exist, but we pretend that it comes 'before' the `li` that we select. */
ul li::before {
  content: '#';
}
```
