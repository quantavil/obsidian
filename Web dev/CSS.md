# Table of contents
 1. [[#Font]]
 2. [[#Text]]
 3. [[#CSS Selectors]]
 4. [[#Pseudo Classes & Pseudo Element]]
 5. [[#Cascading order]]
 6. [[#Inheritance]]
 7. [[#Border]]
 8. [[#Box Model]]
 9. [[#Colors]]
 10. [[#Transition]]
 11. [[#Transform]]
 12. [[#Background]]
 13. [[#CSS Flexbox]]



## What is CSS ?
CSS is a language for describing how the documents are presented visually - how they are arranged and styled.

```css
selector {
	property: value;
}
```


## Linking CSS Stylesheet to HTML
- **INLINE STYLE** : You can write your styles directly inline on each element, but this is NOT A GOOD IDEA most of the time.

```HTML
<body>    
<p style="color:red;">This is a paragraph.</p>  
</body>
```
- **THE `<STYLE>` ELEMET :** You can write your styles inside of a `<style>` element. This is easy, but it makes it impossible to share styles between documents. Not recommended either. 

- **EXTERNAL STYLESHEET :** Write your styles in a`.css`  file, and then include the using a `<link`> in the head of your html document. Recommended!
```HTML
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

## UNITS
-   Pixels: versatile, but not good for responsive websites as they're not scalable;
-   EMs: flexible and scalable unit which the browser translates into pixel values depending on the font size settings in your CSS; **the em unit means "my parent element's font-size"** 
```css
With font—size, 1em equals the font—size of the parent. 2em's is twice the font— size of the parent, etc.With other properties, lem is equal to the computed font-size of the element
itself.
```
-   REMs: flexible, scalable and always relative to the HTML element; **the rem unit means "The root element's font-size"**
```css
Relative to the root html element's font-size. Often easier to work with. If the root font-size is 20px, 1 rem is alwaus 20px, 2rem is alwaus 40px, etc.
```
-   Percent: always relative to another value and suitable for responsive web designs;
```css
PERCENTAGES ARE ALWAYS RELATIVE TO S0ME OTHER VALUE Sometimes, it's a value from the parent and other times it's a value from the element itself.
width: 50% - half the width of the parent
line—height: 50% — half the font—size of the element itself
```

## Font
```css
------------ 01: Font -----------

There are many properties related to the font, such as the face, weight, style, etc. These

properties allow you to change the style or complete look of your text.


/* Font-Family */

font-family: "Segoe UI", Tahoma, sans-serif; /* You can declare multiple fonts. */

/*if first font doesn't exists other ones will be declared serial wise */

/* Font-Style */

font-style: italic;

/* Font-Variant */

font-variant: small-caps;

/* Font-Weight */

font-weight: bold | 100;

/* Font-Size */

font-size: larger | 100px;

/* Font */

font: style variant weight size family;

```

## Text
```css
------------ 02: Text -----------

Text properties allow one to manipulate alignment, spacing, decoration, indentation, etc., in the document.

/* Text-Align */

text-align: justify;

/* Letter-Spacing */

letter-spacing: 0.15em | 5px;

/* Text-Decoration */

text-decoration: green wavy underline;

/* Word-Spacing */

word-spacing: 0.25em;

/* Text-Transform */

text-transform: uppercase;

/* Text-Indent */

text-indent: 0.5cm;

/* Line-Height */

line-height: normal | 2;

}

```

## CSS Selectors
```css
------------ 03: CSS Selectors -----------

/* Universal Selector -  selects all HTML elements on the page */
* {
    background-color: pink;
}

/* Element Selector - Select Everything of given type */
button {
    font-size: 20px;
}

h1,h2 {
    color:blueviolet;
}

/* id selector - uses the id attribute of an HTML element to select a specific element. 
The id of an element is unique within a page, so the id selector is used to select one unique element!*/
[[signup]] {
    background-color: [[22162b]];
    color: [[F4F7F5]];
}

/* class selector - selects HTML elements with a specific class attribute. */
.tag {
    color: red;
}

/* CSS [attribute] Selector - used to select elements with a specified attribute. */

/* <a> elements with a title attribute */
a[title] {
    color: purple;
}

/* <a> elements with an href matching "https://example.org" */
a[href="https://example.org"]
{
    color: green;
}

/* <a> elements with an href containing "example" */
a[href*="example"] {
    font-size: 2em;
}

/* <a> elements with an href ending ".org" */
a[href$=".org"] {
    font-style: italic;
}

/* <a> elements whose class attribute contains the word "logo" */
a[class~="logo"] {
    padding: 2px;
}

/* CSS Combinators - A combinator is something that explains the relationship between the selectors. 
There are four different combinators in CSS:
    descendant selector (space)
    child selector (>)
    adjacent sibling selector (+)
    general sibling selector (~)
*/

/* Descendant Selector - matches all elements that are descendants of a specified element. */
li a {
    color: [[18d761]];
}

.post a {
    color: teal;
}

/* Adjacent Sibling Selector - use to select an element that is directly after another specific element.

Sibling elements must have the same parent element, and "adjacent" means "immediately following". */

h2 + button {
    font-family: cursive;
}

/* Child Selector or Direct Descendent - selects all elements that are the children of a specified element. */

footer > a {
    color: [[88d4e0]];
}

/* general sibling selector - selects all elements that are next siblings of a specified element. */

div ~ p {
    background-color: yellow;
}
```

## Pseudo Classes & Pseudo Element
```css
------------ 04:  Pseudo Classes & Pseudo Element -----------
/* A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). */

button:hover {
    background-color: rgb(222, 84, 84);
}

.post button:active {
    background-color: green;
}

p:nth-of-type(2n + 1) {
    color: red;
  }

/* A CSS **pseudo-element** is a keyword added to a selector that lets you style a specific part of the selected element(s). */

p::first-line {
  color: blue;
  text-transform: uppercase;
}

p::selection {
    color: red;
    background-color: yellow;
}

```
[pseudo-class reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)  [pseudo-Element reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

## Cascading order

The cascading algorithm determines how to find the value to apply for each property for each document element. The following steps apply to the cascading algorithm:

1.  **Relevance**: It first filters all the rules from the different sources to keep only the rules that apply to a given element. That means rules whose selector matches the given element and which are part of an appropriate `media` at-rule.
2.  **Origin and importance**: Then it sorts these rules according to their importance, that is, whether or not they are followed by `!important`, and by their origin. Ignoring layers for the moment, the cascade order is as follows: 

Order (low to high)

1. user-agent (browser)
2. user
3. author (developer)
4. CSS @keyframe animations
5. author (developer) `!important`
6. user `!important`
 7. user-agent (browser) `!important`
8. CSS transitions 

3.  **Specificity:** In case of equality with an origin, the [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) of a rule is considered to choose one value or another. The specificity of the selectors are compared, and the declaration with the highest specificity wins. 
> !Important > Inline $Style_{Not-recommended}$ > Id Selectors  > Class , Attribute, Pseudo-Class Selector  > Element, Pseudo-Element Selector 

To Calculate Complex Specificity :  [Specificity Calculator](https://specificity.keegan.st/) 

4.  **Order of appearance**: In the origin with precedence, if there are competing values for a property that are in style block matching selectors of equal specificity, the last declaration in the style order is applied.

The cascade is in ascending order, meaning animations have precedence of normal values, whether those are declared in user, author, or user-agent styles, important values take precedence over animations, and transitions have precedence over important values.

## Inheritance
Some CSS properties inherit if you don't specify a value for them.
You can make any property inherit its parent's computed value with the `inherit` keyword.
```css
span {
  color: blue;
}

.extra span {
  color: inherit;
}
```


## Border
```css
------------ 07: Border -----------
Border properties are used to change the style, radius, color, etc., of buttons or other items of the document.

/* Border-Width */
border-width: 5px;

/* Border-Style */
border-style: solid;

/* Border-Color */
border-color: aqua;

/* Border-Radius */
border-radius: 15px;

/* Border */
border: width style color;

/* Box Sizing */
box-sizing: content-box | border-box ; /* The dimension of element is calcutated in 
content box as  width = width of the content, and height = height of the content (default) &
border-box as width = border + padding + width of the content, and height = border + padding + height of the content.
* /
```


## Box Model
```css
------------ 08: Box Model -----------
In laymen's terms, the CSS box model is a container that wraps around every HTML element. It
consists of margins, borders, padding, and the actual content.
It is used to create the design and layout of web pages.

/* Float */
float: none;

/* Clear */
clear: both;

/* Display */
display: inline | block | inline-block | none ; 
/* Inline: Width and height are ignored , margin padding push elements always horizontly but not vertically || block: block element break the flow of a document. Width, height, Margin, & Padding are respected || inline=block: Behaved like an inline element except Width,Height, Margin, & Padding are respected */
  
/* Height */
height: fit-content;

/* Width */
width: auto;

/* Margin */
margin: top right bottom left;

/* Padding */
padding: top right bottom left;

/* Overflow */
overflow: hidden;

/* Visibility */
visibility: visible;

/* z-index */ 
z-index: 1; /* When elements are positioned, they can overlap other elements. The z-index property specifies the stack order of an element (which element should be placed in front of, or behind, the others). An element can have a positive or negative stack order */

/* position */
position: static | relative | fixed | absolute | sticky;

```

### Position

![[pos.jpg]]

![CSS Position Property](https://miro.medium.com/max/1100/1*x5xm9DVS6QouWCAeII9w8A.png)

**Static**
The element is positioned according to the normal flow of the document. The [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/right), [`bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom), [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left), and [`z-index`](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index) properties have _no effect_. This is the default value.

**Relative**
The element is positioned according to the normal flow of the document, and then offset _relative to itself_ based on the values of `top`, `right`, `bottom`, and `left`. The offset does not affect the position of any other elements; thus, the space given for the element in the page layout is the same as if position were `static`.

**Absolute**
The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to its closest positioned ancestor, if any; otherwise, it is placed relative to the initial [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block). Its final position is determined by the values of `top`, `right`, `bottom`, and `left`.

**Fixed**

The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to the initial [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block) established by the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport), except when one of its ancestors has a `transform`, `perspective`, or `filter` property set to something other than `none` (see the [CSS Transforms Spec](https://www.w3.org/TR/css-transforms-1/#propdef-transform)), or the [`will-change`](https://developer.mozilla.org/en-US/docs/Web/CSS/will-change) property is set to `transform`, in which case that ancestor behaves as the containing block.  Its final position is determined by the values of `top`, `right`, `bottom`, and `left`.

**Sticky**

The element is positioned according to the normal flow of the document, and then offset relative to its _nearest scrolling ancestor_ and [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block) (nearest block-level ancestor), including table-related elements, based on the values of `top`, `right`, `bottom`, and `left`. The offset does not affect the position of any other elements.



## Colors
```css
------------ 09: Colors -----------

With the help of the color property, one can give color to text, shape, or any other object.

/* Color - 1 */

color: cornsilk;

/* Color - 2 */

color: [[fff8dc]];

/* Color - 3 */ 

color: rgba(255, 248, 220, 1); /* . An optional alpha component represents the color's transparency. */

/* Color - 4 */

color: hsl(48, 100%, 93%);

/* Opacity */

opacity: 1; /* Opacity is the degree to which content behind an element is hidden, and is the opposite of transparency. */

```


## Transition

```css
------------ 10: Transitions -----------

Transitions let you define the transition between two states of an element.


/* Transition-property */

transition-property: none;

/* Transition-duration */

transition-duration: 2s;

/* Transition-timing-function */

transition-timing-function: ease-in-out;

/* Transition-delay */

transition-delay: 20ms;

/* Transition */
transition: property duration timing-function delay

```

### Transition Property
The **`transition-property`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the CSS properties to which a [transition effect](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) should be applied.
[CSS Animatable Property](https://www.w3schools.com/cssref/css_animatable.asp)

### Transition timing Function
The `transition-timing-function` property specifies the speed curve of the transition effect.
The transition-timing-function property can have the following values:

-   `ease` - specifies a transition effect with a slow start, then fast, then end slowly (this is default)
-   `linear` - specifies a transition effect with the same speed from start to end
-   `ease-in` - specifies a transition effect with a slow start
-   `ease-out` - specifies a transition effect with a slow end
-   `ease-in-out` - specifies a transition effect with a slow start and end
-   `cubic-bezier(n,n,n,n)` - lets you define your own values in a cubic-bezier function

## Transform

The **`transform`** CSS property lets you rotate, scale, skew, or translate an element.
```css

----------- 12: Transform -----------
/* Keyword values */
transform: none;

/* Function values */
transform: matrix(1, 2, 3, 4, 5, 6);
transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
transform: perspective(17px);
transform: rotate(0.5turn);
transform: rotate3d(1, 2, 3, 10deg);
transform: rotateX(10deg);
transform: rotateY(10deg);
transform: rotateZ(10deg);
transform: translate(12px, 50%);
transform: translate3d(12px, 50%, 3em);
transform: translateX(2em);
transform: translateY(3in);
transform: translateZ(2px);
transform: scale(2, 0.5);
transform: scale3d(2.5, 1.2, 0.3);
transform: scaleX(2);
transform: scaleY(0.5);
transform: scaleZ(0.3);
transform: skew(30deg, 20deg);
transform: skewX(30deg);
transform: skewY(1.07rad);

/* Multiple function values */
transform: translateX(10px) rotate(10deg) translateY(5px);
transform: perspective(500px) translate(10px, 0, 20px) rotateY(3deg);

/* Global values */
transform: inherit;
transform: initial;
transform: revert;
transform: revert-layer;
transform: unset;
	
```

## Background

```css
----------- 12: Background -----------

As the name suggests, these properties are related to background, i.e., you can change the color,
image, position, size, etc., of the document.


/* Background-Image */
background-image: url("Path");

/* Background-Position */
background-position: right top |50% |8em;

/* Background-Size */
background-size: cover | contain |50% |3.2rem;

/* Background-Repeat */
background-repeat: no-repeat |repeat-x | repeat-y | space | round;

/* Background-Attachment */
background-attachment: scroll;

/* Background-Color */
background-color: fuchsia;

/* Background */
background: color image repeat attachment position;


```

## CSS Flexbox


```css
------------ 13: CSS Flexbox (Important) -----------
Flexbox is a layout of CSS that lets you format HTML easily. Flexbox makes it simple to align items vertically and horizontally using rows and columns. Items will "flex" to different sizes to fill the space. And overall, it makes the responsive design more manageable.

/* ---------------------- Parent Properties (flex container) ------------ */

/* display */
display: flex;

/* flex-direction => The flex-direction CSS property sets how flex items are placed in the flex container defining the main axis and the direction (normal or reversed).*/
flex-direction: row | row-reverse | column | column-reverse ;


/* flex-wrap => The flex-wrap CSS property sets whether flex items are forced onto one line or can wrap onto multiple lines. If wrapping is allowed, it sets the direction that lines are stacked.*/
flex-wrap: nowrap | wrap | wrap-reverse;


/* flex-flow => The flex-flow CSS shorthand property specifies the direction of a flex container, as well as its wrapping behavior. */
flex-flow: column wrap;


/* justify-content => The CSS justify-content property defines how the browser distributes space between and around content items along the main-axis of a flex container, and the inline axis of a grid container.*/
justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;


/* align-items => The CSS align-items property sets the align-self value on all direct children as a group. In Flexbox, it controls the alignment of items on the Cross Axis.*/
align-items: stretch | flex-start | flex-end | center | baseline;


/* align-content => The CSS align-content property sets the distribution of space between and around content items along a flexbox's cross-axis or a grid's block axis.*/
align-content: flex-start | flex-end | center | space-between | space-around; /* This property has no effect on single line flex containers (i.e. ones with flex-wrap: nowrap).*



/* ---------------------- Child Properties (flex items) ------------ */

/* order => The order CSS property sets the order to lay out an item in a flex or grid container. */
order: 5; /* default is 0 */

	
/* flex-grow => The flex-grow CSS property sets the flex grow factor of a flex item's main size */
flex-grow: 4; /* default 0 */


/* flex-shrink => The flex-shrink CSS property sets the flex shrink factor of a flex item.  */
flex-shrink: 3; /* default 1 */


/* flex-basis => The flex-basis CSS property sets the initial main size of a flex item. */
flex-basis: | auto | 200px; /* default auto */


/* flex shorthand */
flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]


/* align-self => The align-self CSS property overrides a grid or flex item's align-items value. */
align-self: auto | flex-start | flex-end | center | baseline | stretch;

```

### Justify Content

```css
/* Positional alignment */
justify-content: center;     /* Pack items around the center */
justify-content: start;      /* Pack items from the start */
justify-content: end;        /* Pack items from the end */
justify-content: flex-start; /* Pack flex items from the start */
justify-content: flex-end;   /* Pack flex items from the end */
justify-content: left;       /* Pack items from the left */
justify-content: right;      /* Pack items from the right */

/* Baseline alignment */
/* justify-content does not take baseline values */

/* Normal alignment */
justify-content: normal;

/* Distributed alignment */
justify-content: space-between; /* Distribute items evenly
                                   The first item is flush with the start,
                                   the last is flush with the end */
justify-content: space-around;  /* Distribute items evenly
                                   Items have a half-size space
                                   on either end */
justify-content: space-evenly;  /* Distribute items evenly
                                   Items have equal space around them */
justify-content: stretch;       /* Distribute items evenly
                                   Stretch 'auto'-sized items to fit
                                   the container */
```

### Align items

```css
/* Basic keywords */
align-items: normal;
align-items: stretch;

/* Positional alignment */
/* align-items does not take left and right values */
align-items: center; /* Pack items around the center */
align-items: start; /* Pack items from the start */
align-items: end; /* Pack items from the end */
align-items: flex-start; /* Pack flex items from the start */
align-items: flex-end; /* Pack flex items from the end */

/* Baseline alignment */
align-items: baseline;
align-items: first baseline;
align-items: last baseline; /* Overflow alignment (for positional alignment only) */
```

## Responsive Web Design 
Responsive web design is an approach that allows design across various devices (mobile, desktop, tablet, etc.) and suggests design should respond to the user’s behavior based on screen size, platform and orientation.

 **Responsive websites have three defining features:** flexible layouts, media queries and flexible media.
### Flexible layouts
Flexible layouts are the practice of building the layout of a website with a flexible grid. Flexible grids are created using CSS. Web layout consists of columns that automatically rearrange themselves to fit the size of the screen or browser window.

### Media queries
The flexible layout approach alone isn’t enough to optimize the design for various screens. When the layout gets too small, the layout may begin to break and create columns that will be too small to display content effectively. Media queries come to save the day.

### Flexible images and videos
As viewports begin to change the size, images, videos, and other media types should be scalable, adjusting their size as the size of the viewport changes.

## Media queries

```css
/***************************

------------ 15: MEDIA QUERIES -----------

Using media queries are a popular technique for delivering a tailored style sheet to

desktops, laptops, tablets, and mobile phones (such as iPhone and Android phones).

|----------------------------------------------------------|

| Responsive Grid Media Queries - 1280, 1024, 768, 480 |

| 1280-1024 - desktop (default grid) |

| 1024-768 - tablet landscape |

| 768-480 - tablet |

| 480-less - phone landscape & smaller |

|----------------------------------------------------------|

*******************************/

@media all and (min-width: 1024px) and (max-width: 1280px) { }

@media all and (min-width: 768px) and (max-width: 1024px) { }

@media all and (min-width: 480px) and (max-width: 768px) { }

@media all and (max-width: 480px) { }

/* Small screens - MOBILE */

@media only screen { } /* Define mobile styles - Mobile First */

@media only screen and (max-width: 40em) { } /* max-width 640px, mobile-only styles, use when QAing mobile issues */

/* Medium screens - TABLET */

@media only screen and (min-width: 40.063em) { } /* min-width 641px, medium screens */

@media only screen and (min-width: 40.063em) and (max-width: 64em) { } /* min-width 641px and max-width 1024px, use when QAing tablet-only issues */

/* Large screens - DESKTOP */

@media only screen and (min-width: 64.063em) { } /* min-width 1025px, large screens */

@media only screen and (min-width: 64.063em) and (max-width: 90em) { } /* min-width 1024px and max-width 1440px, use when QAing large screen-only issues */

/* XLarge screens */

@media only screen and (min-width: 90.063em) { } /* min-width 1441px, xlarge screens */

@media only screen and (min-width: 90.063em) and (max-width: 120em) { } /* min-width 1441px and max-width 1920px, use when QAing xlarge screen-only issues */

/* XXLarge screens */

@media only screen and (min-width: 120.063em) { } /* min-width 1921px, xlarge screens */

/*------------------------------------------*/

/* Portrait */

@media screen and (orientation:portrait) { /* Portrait styles here */ }

/* Landscape */

@media screen and (orientation:landscape) { /* Landscape styles here */ }

/* CSS for iPhone, iPad, and Retina Displays */

/* Non-Retina */

@media screen and (-webkit-max-device-pixel-ratio: 1) {

}

/* Retina */

@media only screen and (-webkit-min-device-pixel-ratio: 1.5),

only screen and (-o-min-device-pixel-ratio: 3/2),

only screen and (min--moz-device-pixel-ratio: 1.5),

only screen and (min-device-pixel-ratio: 1.5) {

}

/* iPhone Portrait */

@media screen and (max-device-width: 480px) and (orientation:portrait) {

}

/* iPhone Landscape */

@media screen and (max-device-width: 480px) and (orientation:landscape) {

}

/* iPad Portrait */

@media screen and (min-device-width: 481px) and (orientation:portrait) {

}

/* iPad Landscape */

@media screen and (min-device-width: 481px) and (orientation:landscape) {

}

/* Make Sure you don't forgot to add */

<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no" /> /* within <head> tag */
```