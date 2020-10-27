# Build and Host Your Portfolio Website for Free
In this workshop you will learn the basics of HTML and CSS, how to use a CSS library like Bootstrap, how to deploy your webiste to GitHub pages, and then how to get a custom domain name for free using the GitHub student developer pack and point your domain at your Website.

## 1. Get Access to the GitHub Student Developer Pack
As verificatio may not be instant, if you don't already have access to the GitHub student developer pack, please sign up first by going to [hacksoc.net/github](https://hacksoc.net/github).

## 2. Duplicate the code on repl.it
Click the "Run it on Repl.it" button below to create your own version of this repository. There isn't much going on yet, but it does have some of the foudnations you need.

[![Run it on Repl.it](https://repl.it/badge/github/aaronosher/first-portfolio)](https://repl.it/github/aaronosher/first-portfolio)

## 3. Basics of HTML
HTML stands for Hyper Text Markup Language, and it is a superset of XML and syntax used for communicating by applications.

> If you've heard of JSON, XML is an alterive

A great resource for referencing how HTML works is [w3schools](https://www.w3schools.com/html/)

### Tags
At it's core, HTML is built using tags. Tags are the syntactic elements we wrap the content of our page in.

A tag is denoated by `<` and `>` around a tag name such as `<div>`.

Tags usually comen in pars, for example, to denote a paragraph we use the `<p>` tag. To mark the start of the paragraph we open the tag we start with <p> and then to mark the end, we close the tag with `</p>`.

```html
<p>
This is a paragraph
</p>
```

Self closing tags also exist, such as `<img>` which is used for rendering an image on the page. A self closing tag will move the `/` from the start of the tag to the end with a space before it such as:

```html
<img src="myImage.jpg" />
```
> `src` is an attribute, we'll talk about those in a minute

Here are some common tags that we'll be using

 - `<html>`: we wrap the entire HTML document in this tag
 - `<head>`: we wrap the page's header data in this tag
 - `<link>`: used for pointing at external resources (we'll talk about these later)
 - `<title>`: used to set the page tite
 - `<body>`: wraps the page body (the part that gets rendered)
 - `<div>`: used to separate a specific part of the page
 > `<section>`, `<header>`, `<nav>`, `<foot>` and some others tags are all aliases of `<div>` used for accessibility
 - `<p>`: used to denote a paragraph
 - `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`: denoate each of the six heading levels
 - `<img>`: used to render an image on the page
 - `<a>`: anchor tag used for hyperlinks
 - `<button>`: like `a` but for buttons
 - `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>`: tags used for building tables
 - `<ul>`, `<ol>`, `<li>`: tags for builing unordered (bulleted `<ul>`) and ordered (number `<li>`) lists

### Attributes
In both XML and HTML a tag can have attributes, these can affect their behaviour or how they look. Int this workshop we'll only be looking at five attributes: `src`, `target`, `href`, `id`, and `class`.

`src` indicates the remote source of an asset that should be used. Two main examples are `<img>` for displaying an image, and `<link>` which we use for loading stylesheets and fonts, etc.

`target` and `href` are used by the `a` tag to denote the hyperlink reference (href), which is where the link should take you. `target` indicates where the link should be opened. We won't usually use this for links to pages on our own website, but it's common to set it to `_blank` when you want to open up the link in a new window or tab, e.g. for exteranl sites.

`id` and `class` are used for referencing your element. `id`s must be unique, weheras `class` can be the same for multiple elements. We primarily use these for setting styles from a stylesheet, but may also use them when selecting the element using JavaScript (whcih is outside the scope of this workshop).

Attributes are added to an element by adding a space after the tag name and then using the `attribute="value"` syntax e.g. `<img src="something.jpg">`.

### Comments

To add an inline comment in HTML warp the comment with `<!--` and `-->`.

### Basic Structure of an HTML document

```html
<!DOCTYPE html>                 <!-- denotates that we're using HTML5 -->
<html>                          <!-- start the html part of the document -->
  <head>                        <!-- start of header information -->
    <title>My Document</title>  <!-- set the page title -->
  </head>                       <!-- end of header information -->
  <body>                        <!-- start of rendered body -->
    <h1>My Webpage</h1>         <!-- Level 1 heading -->
  </body>                       <!-- end of rendered body -->
</html>                         <!-- end of html document -->
```

## 4. Styles and CSS
In HTML we use Cascading Style Sheets (CSS) to style to document. 

Using CSS we can set things like borders, colour, text size, position, animations and more. 

In CSS there are two core concepts, the selector, and the styles.

### Selectors
Selectors are what we use to denote what we want to affect the styles of. Theree of the most common types of selectors are tag name, class, and id.

To reference a tag name we just enter the tag name without the `<` `>`, e.g. `div` for selecting all divs. 

To reference an id, we just put a `#` in front if it. e.g. `#myId`

To reference a class we just put a `.` in fron the the name. e.g. `.myClass`

We can also select states of an element, such as if it is active or being hovered over, we do that by adding `:<status>` after the element. e.g. we would use `a:hover` to style all anchor tags being hovered on.

### Styles

Styles are fairly simple, they are `key:value` pairs with `;` at the end of the line wrapped in `{` `}` after a selector.

Some of the most common styles we use are `color`, `text-decoration`, `text-align`

Here is an example of adjusting the appearence of links

```css
body {
  background-color: #3e3e3e;
}

a {
  text-decoration: none;
  color: #a500ff;
  font-size: 52pt;
}

a:hover {
  color: #53a552;
}

a.myClass {
  color: #dd5353;
}
```

## 5. Component Libraries
While CSS is super powerful, and useful, it's really difficult to fully take advantage of, and more than a foundational knowledge is outside the scope of this workshop.

Componet libraries are a super powerful way to level-up how your website looks. They can do things like make it easier for us to create navbars, make tables look good, do things with layout, and we can do all of it without really touchin my CSS.

We'll be using [Bootstrap](https://getbootstrap.com/)

To add Bootstrap to your project, we need to add the following lines to our `<head>`

```html
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
```

and the following two lines right above the closing `</body>` tag

```html
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ho+j7jyWK8fNQe+A12Hb8AhRq26LrZ/JpcUGGOn+Y7RsweNrtN/tE3MoK7ZeZDyx" crossorigin="anonymous"></script>
```

Let's start by using the [jumbotron](https://getbootstrap.com/docs/4.5/components/jumbotron/) component to make our header look a bit flashier

```html
<div class="jumbotron">
  <h1 class="display-4">Hello, world!</h1>
  <p class="lead">This is a simple hero unit, a simple jumbotron-style component for calling extra attention to featured content or information.</p>
</div>
```