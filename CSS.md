### 1\.  What is the CSS **Box model**

The CSS box model is used to define the design and layout of elements of CSS.

The elements are:

-   Margin - It removes the area around the border. It is transparent.
-   Border - It represents the area around the padding
-   Padding - It removes the area around the content. It is transparent.
-   Content - It represents the content like text, images, etc.

![CSS Box Model](https://static.javatpoint.com/interview/images/css-box-model.png)

### 2\. What are the **advantages** of using CSS?

The main advantages of CSS are given below:

-   **Separation of content from presentation -** CSS provides a way to present the same content in multiple presentation formats in mobile or desktop or laptop.
-   **Easy to maintain -** CSS, built effectively can be used to change the look and feel complete by making small changes. To make a global change, simply change the style, and all elements in all the web pages will be updated automatically.


### 3\. How to include CSS in the webpage?

1 - External Style Sheet: An external file linked to your HTML document: Using link tag, we can link the style sheet to the HTML page.

```
<link rel="stylesheet" type="text/css" href="mystyles.css" />
```

2 - Embed CSS with a style tag: A set of CSS styles included within your HTML page.

```
<style type="text/css">

/*Add style rules here*/

</style>
```

Add your CSS rules between the opening and closing style tags and write your CSS exactly the same way as you do in stand-alone stylesheet files.

3 - Add inline styles to HTML elements(CSS rules applied directly within an HTML tag.): Style can be added directly to the HTML element using a style tag.

```
<h2 style="color:red;background:black">Inline Style</h2>
```

### 4\. What are the different types of **Selectors** in CSS?

A CSS selector is the part of a CSS ruleset that actually selects the content you want to style. Different types of selectors are listed below.

**Universal Selector:** The universal selector works like a wildcard character, selecting all elements on a page. In the given example, the provided styles will get applied to all the elements on the page.

```
* {
  color: "green";
  font-size: 20px;
  line-height: 25px;
}
```

**Element Type Selector:** This selector matches one or more HTML elements of the same name. In the given example, the provided styles will get applied to all the ul elements on the page.

```
ul {
  line-style: none;
  border: solid 1px [[ccc]];
}
```

**ID Selector:** This selector matches any HTML element that has an ID attribute with the same value as that of the selector. In the given example, the provided styles will get applied to all the elements having ID as a container on the page.

```
[[container]] {
  width: 960px;
  margin: 0 auto;
}

<div id="container"></div>
```

**Class Selector:** The class selector also matches all elements on the page that have their class attribute set to the same value as the class.  In the given example, the provided styles will get applied to all the elements having ID as the box on the page.

```
.box {
  padding: 10px;
  margin: 10px;
  width: 240px;
}

<div class="box"></div>
```

**Attribute Selector:** The attribute selector targets elements based on the presence and/or value of HTML attributes, and is declared using square brackets.

```
input [type=”text”] {
background-color: #444;
width: 200px;
}

<input type="text">
```


### 5\. What is the difference between **inline, inline-block, and block**?

**Block Element:** The block elements always start on a new line. They will also take space for an entire row or width. List of block elements are `<div>, <p>.`

**Inline Elements:** Inline elements don't start on a new line, they appear on the same line as the content and tags beside them. Some examples of inline elements are `<a>, <span> , <strong>, and <img>` tags. 

**Inline Block Elements:** Inline-block elements are similar to inline elements, except they can have padding and margins and set height and width values.


### 6\. What are **Pseudo elements** and **Pseudo classes**?

**Pseudo-elements** allows us to create items that do not normally exist in the document tree, for example ::after.

-   ::before
-   ::after
-   ::first-letter
-   ::first-line
-   ::selection

In the below example, the color will appear only on the first line of the paragraph.

```
p: :first-line {
color: [[ffOOOO]];
font-variant: small-caps;
}
```

**Pseudo-classes** select regular elements but under certain conditions like when the user is hovering over the link.

-   :link
-   :visited
-   :hover
-   :active
-   :focus

Example of the pseudo-class, In the below example, the color applies to the anchor tag when it’s hovered.

```
/* mouse over link */
a:hover {
color: [[FFOOFF]];
}
```


### 7\. Explain the difference between visibility: hidden and display: none?

**visibility: hidden** hides the element, but it occupies space and affects the layout of the document.
**display: none** also hides the element but not occupy space. It will not affect the layout of the document.


 ### 8\. CSS **Selectors**

CSS selectors are used to "find" (or select) the HTML elements you want to style.

We can divide CSS selectors into five categories:

-   Simple selectors (select elements based on name, id, class)
-   [Combinator selectors](https://www.w3schools.com/css/css_combinators.asp) (select elements based on a specific relationship between them)
-   [Pseudo-class selectors](https://www.w3schools.com/css/css_pseudo_classes.asp) (select elements based on a certain state)
-   [Pseudo-elements selectors](https://www.w3schools.com/css/css_pseudo_elements.asp) (select and style a part of an element)
-   [Attribute selectors](https://www.w3schools.com/css/css_attribute_selectors.asp) (select elements based on an attribute or attribute value)
### 9\. How is border-box different from content-box?

`content-box` is the default value box-sizing property. The height and the width properties consist only of the content by excluding the border and padding. Consider an example as shown:

```
div{
    width:300px;
    height:200px;
    padding:15px;
    border: 5px solid grey;
    margin:30px;
    -moz-box-sizing:content-box;
    -webkit-box-sizing:content-box;
    box-sizing:content-box;
}
```

Here, the box-sizing for the div element is given as content-box. That means, the height and width considered for the div content exclude the padding and border. We will get full height and width parameters specified for the content as shown in the below image.

![](https://d3n0h9tb65y8q.cloudfront.net/public_assets/assets/000/001/632/original/content_box.png?1636640351)

The `border-box` property includes the content, padding and border in the height and width properties. Consider an example as shown:

```
div{
    width:300px;
    height:200px;
    padding:15px;
    border: 5px solid grey;
    margin:30px;
    -moz-box-sizing:border-box;
    -webkit-box-sizing:border-box;
    box-sizing:border-box;
}
```

Here, the box-sizing for the div element is given as border-box. That means the height and width considered for the div content will also include the padding and border. This means that the actual height of the div content will be:

```
actual height = height - 
                padding on top and bottom - 
                border on top and bottom
              = 200 - (15*2) - (5*2) 
              = 160 px
```

and the actual width of the div content would be:

```
actual width  = width - 
                padding on right and left - 
                border on right and left
              = 300 - (15*2) - (5*2) 
              = 260 px
```

This is represented in the image below:

![](https://d3n0h9tb65y8q.cloudfront.net/public_assets/assets/000/001/633/original/border_box.png?1636640401)



### 10\. Why should we use **float** property in CSS?

The float property is used for positioning the HTML elements horizontally either towards the left or right of the container. For instance,

```
 float-demo {
     float: right; 
}
```



### 11\. What are the properties of **flexbox**?

*It provides an efficient way to handle layouts, align elements within them and distribute spaces amongst the items in dynamic/responsive conditions.* It provides an enhanced ability to alter the dimensions of the items and make use of the available space in the container efficiently. In order to achieve this, CSS3 provides some properties.

The properties of flexbox are as follows:

-   **flex-direction**: This property helps in defining the direction the container should stack the items targetted for flex. The values of this property can be
    -   row: Stacks items horizontally from left to right in the flex container.
    -   column: Stacks items vertically from top to bottom in the flex container.
    -   row-reverse: Stacks items horizontally from right to left in the flex container.
    -   column-reverse: Stacks items vertically from bottom to top in the flex container.
-   **flex-wrap**: This property specifies of the flex items should be wrapped or not. Possible values are:
    -   wrap: The flex items would be wrapped if needed.
    -   nowrap: This is the default value that says the items won’t be wrapped.
    -   wrap-reverse: This specifies that the items will be wrapped if needed but in reverse order.
-   **flex-flow**: This property is used for setting both flex-direction and flex-wrap properties in one statement.
-   **justify-content**: Used for aligning the flex items. Possible values are:
    -   center: It means that all the flex items are present at the center of the container.
    -   flex-start: This value states that the items are aligned at the start of the container. This is the default value.
    -   flex-end: This value ensures the items are aligned at the end of the container.
    -   space-around: This value displays the items having space between, before, around the items.
    -   space-between: This value displays items with spaces between the lines.
-   **align-items**: This is used for aligning flex items.
-   **align-content**: This is used for aligning the flex lines.

### 12\. What is **cascading** in CSS?

“Cascading” refers to the process of going through the style declarations and defining weight or importance to the styling rules that help the browser to select what rules have to be applied in times of conflict. The conflict here refers to multiple rules that are applicable to a particular HTML element. In such cases, we need to let the browser know what style needs to be applied to the element. This is done by cascading down the list of style declarations elements.

For example, if we have the below style:

```
p{
    color:white;
}
```

and we also have the following declaration below it or in another stylesheet that has been linked to the page:

```
p{
    color: black;
}
```

We have a conflict in color property here for the paragraph elements. Here, the browser just cascades down to identify what is the most recent and most specific style and applies that. Since we have the `color:black;` as the most specific declaration, the color black is applied to the paragraph elements. Now if you want to ensure color white is applied to the paragraph, we can define weight to that style by adding `!important` as shown below:

```
p{
    color:white !important;
}
```

`!important` ensures that the property has the maximum weight in presence of other conflicting properties.


### 13\. Explain CSS **position property**?

-   **Absolute:** To place an element exactly where you want to place it. absolute position is actually set relative to the element's parent. if no parent is available then the relative place to the page itself (it will default all the way back up to the element).
-   **Relative:** "Relative to itself". Setting position: relative; on an element and no other positioning attributes, it will no effect on its positioning. It allows the use of z-index on the element and it limits the scope of absolutely positioned child elements. Any child element will be absolutely positioned within that block. 
-   **Fixed:** The element is positioned relative to the viewport or the browser window itself. viewport doesn't change if you scroll and hence the fixed element will stay right in the same position. 
-   **Static:** Static default for every single page element. The only reason you would ever set an element to position: static is to forcefully remove some positioning that got applied to an element outside of your control.
-   **Sticky:** Sticky positioning is a hybrid of relative and fixed positioning. The element is treated as relative positioned until it crosses a specified threshold, at which point it is treated as fixed positioned.

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/000/107/original/CSS_Position_Property.jpg?1615286481)


### 14\. Different Box Sizing Property?

The box-sizing CSS property sets how the total width and height of an element are calculated.

-   **Content-box:** The default width and height values apply to the element's content only. The padding and border are added to the outside of the box.
-   **Padding-box:** Width and height values apply to the element's content and its padding. The border is added to the outside of the box. Currently, only Firefox supports the padding-box value.
-   **Border-box:** Width and height values apply to the content, padding, and border.
