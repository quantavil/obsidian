
### Introduction


The latest version of HTML is HTML5. There are two main components in HTML language, Tags and Attributes. The below image shows some basic HTML tags and attributes.

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/000/585/original/html-intro.png?1625063534)

### 1\. What is the difference between HTML **elements** and **tags**?
HTML elements communicate to the browser to render text. When the elements are enclosed by brackets <>, they form HTML tags. Most of the time, tags come in a pair and surround content

### 2\. What are **tags** and **attributes** in HTML?

Tags are the primary component of the HTML that defines how the content will be structured/ formatted, whereas Attributes are used along with the HTML tags to define the characteristics of the element. For example,1 `<p align=” center”>Interview questions</p>`, in this the ‘align’ is the attribute using which we will align the paragraph to show in the center of the view.

### 3\. What are **void elements** in HTML?

HTML elements which do not have closing tags or do not need to be closed are Void elements. For Example `<br />, <img />, <hr />,` etc.

### 4\. What are HTML **Entities**?

In HTML some characters are reserved like ‘<’, ‘>’, ‘/’, etc. To use these characters in our webpage we need to use the character entities called HTML Entities. Below are a few mapping between the reserved character and its respective entity character to be used.

| Character | Entity Name | Entity Number |
| --- | --- | --- |
| < | &lt; | &#60; |
| \> | &gt; | &#62; |
| & | &amp; | &#38; |
| (non-breaking space) Eg. 10  PM | &nbsp; Eg. <p>10&nbsp&nbspPM</p> | &#160; |

### 5\. What are different types of **list** in HTML?

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/000/558/original/Image_24%281%29.png?1625041509)

### 6\. What is the ‘**class**’ attribute in HTML?

The class attribute is used to specify the class name for an HTML element. Multiple elements in HTML can have the same class value. 

### 7\. What is the difference between the ‘**id**’ attribute and the ‘**class**’ attribute of HTML elements?
Multiple elements in HTML can have the same class value, whereas a value of id attribute of one element cannot be associated with another HTML element.

### 8\. Describe HTML **layout** structure.

Every web page has different components to display the intended content and a specific UI. But still, there are few things which are templated and are globally accepted way to structure the web page, such as:

```
-   **<header>**: Stores the starting information about the web page.
-   **<footer>**: Represents the last section of the page.
-   **<nav>**: The navigation menu of the HTML page.
-   **<article>**: It is a set of information.
-   **<section>**: It is used inside the article block to define the basic structure of a page.
-   **<aside>**: Sidebar content of the page.
```


### 9\. What are the various **formatting tags** in HTML?

 HTML has various formatting tags:

```
-   **<b>** - makes text bold
-   **<i>** - makes text italic
-   **<em>** - makes text italic but with added semantics importance
-   **<big>** - increases the font size of the text by one unit
-   **<small>** - decreases the font size of the text by one unit
-   **<sub>** - makes the text a subscript
-   **<sup>** - makes the text a superscript
-   **<del>** - displays as strike out text
-   **<strong>** - marks the text as important
-   **<mark>** - highlights the text
-   **<ins>** - displays as added text
```


### 10\. Please explain how to indicate the **character set** being used by a document in HTML?

The character set is defined in `<meta>` tag inside `<head>`element.


```
<!DOCTYPE html>
`<html>`
 `<head>`
   <meta charset="UTF-8">
   ...
   ...
 </head>
 ...
</html>
```


### 11\. What is the significance of `<head>` and `<body>`tag in HTML?

`<head> `tag provides the information about the document. It should always be enclosed in the `<html>` tag. This tag contains the metadata about the webpage and the tags which are enclosed by head tag like `<link>`, `<meta>`, `<style>`, `<script>`, etc. are not displayed on the web page. Also, there can be only 1 `<head>` tag in the entire Html document and will always be before the `<body>` tag.

`<body>` tag defines the body of the HTML document. It should always be enclosed in the `<html>` tag. All the contents which needs to be displayed on the web page like images, text, audio, video, contents, using elements like `<p>, <img>, <audio>, <heading>, <video>, <div>`, etc. will always be enclosed by the `<body>` tag. Also, there can be only 1 body element in an HTML document and will always be after the `<head>` tag.

### 12\. **Iframe**?

Yes, we can display a web page inside another HTML web page. HTML provides a tag `<iframe> `using which we can achieve this functionality.

```
<iframe src=”url of the web page to embed” />
```

### 13\. How is **Cell Padding** different from **Cell Spacing**?

- Cell Spacing is the space or gap between two consecutive cells.
- Cell Padding is the space or gap between the text/ content of the cell and the edge/ border of the cell.

### 14\. How can we club two or more rows or columns into a single row or column in an HTML table?
HTML provides two table attributes “rowspan” and “colspan” to make a cell span to multiple rows and columns respectively.

### 15\. Is it possible to change an **inline element into a block level** element?
Yes, it is possible using the “*display*” property with its value as “block”, to change the inline element into a block-level element.

### 16\. In how many ways can we **position** an HTML element? Or what are the permissible values of the **position attribute**?

There are mainly 7 values of position attribute that can be used to position an HTML element:

1.  **static**: Default value. Here the element is positioned according to the normal flow of the document.
2.  **absolute**: Here the element is positioned relative to its parent element. The final position is determined by the values of left, right, top, bottom.
3.  **fixed**: This is similar to absolute except here the elements are positioned relative to the `<html>` element.
4.  **relative**: Here the element is positioned according to the normal flow of the document and positioned relative to its original/ normal position.
5.  **initial**: This resets the property to its default value.
6.  **inherit**: Here the element inherits or takes the property of its parent.

### 22\. In how many ways you can **display** HTML elements?

1.  **inline**: Using this we can display any block-level element as an inline element. The height and width attribute values of the element will not affect.
2.  **block**: using this, we can display any inline element as a block-level element. 
3.  **inline-block**: This property is similar to inline, except by using the display as inline-block, we can actually format the element using height and width values.
4.  **flex**: It displays the container and element as a flexible structure. It follows flexbox property.
5.  **inline-flex**: It displays the flex container as an inline element while its content follows the flexbox properties.
6.  **grid**: It displays the HTML elements as a grid container.
7.  **none**: Using this property we can hide the HTML element.

### 23\. What is the difference between “**display: none” and “visibility: hidden**”, when used as attributes to the HTML element.

When we use the attribute “visibility: hidden” for an HTML element then that element will be hidden from the webpage but still takes up space. 
Whereas, if we use the “display: none” attribute for an HTML element then the element will be hidden, and also it won’t take up any space on the webpage.


### 17\. In how many ways can we specify the **CSS styles** for the HTML element?

There are three ways in which we can specify the styles for HTML elements:

-   **Inline**: Here we use the ‘style’ attribute inside the HTML element.
-   **Internal:** Here we use the `<style>` tag inside the `<head>` tag. To apply the style we bind the elements using ‘id’ or ‘class’ attributes.
-   **External**: Here we use the `<link>` tag inside `<head>` tag to reference the CSS file into our HTML code. Again the binding between elements and styles is done using ‘id’ or ‘class’ attributes.

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/000/591/original/css-styles-for-html5-element.png?1625064724)

### 18\. Difference between **link** tag `<link>` and **anchor** tag `<a>`?

- The anchor tag `<a>` is used to create a hyperlink to another webpage or to a certain part of the webpage and these links are clickable
-  link tag `<link>` defines a link between a document and an external resource and these are not clickable.



### 19\. What are **forms** and how to create forms in HTML?

The HTML form is used to collect the user inputs. HTML provides a` <form>` tag to create forms. To take input from the user we use the `<input>` tag inside the form so that all collected user data can be sent to the server for processing. There are different input types like ‘button’, ‘checkbox’, ‘number’, ‘text’, ‘password’, ‘submit’ etc.

```
<form action="/submit_data.php">
   <label>Enter your name: </label>
   <input type="text" name="name" /> 
   <label>Enter Mobile number </label>
   <input type="number" name="mobile_no"/>
   <input type="submit" value="Submit">
</form>
```

### 20\. How to handle **events** in HTML?

HTML allows event trigger actions in browsers using javascript or JQuery. There are a lot of events like ‘onclick’, ‘ondrag’, ‘onchange’, etc.



### 21\. **Inline** and **block** elements in HTML5?
 Inline elements just take up the space that is absolutely necessary for the content and does not start from a new line.  
```Example:- <span>, `<a>`, <strong>, <img>, <button>, <em>, <select>, <abbr>, <label>, <sub>, <cite>, <abbr>, `<script>`, <label>, <i>, `<input>`, <output>, <q>, etc. ```
Block elements start on a new line and consume the full width of the page available.  
```Example:- <div>, <p>, <header>, <footer>, <h1>...<h6>,` <form>`, <table>, <canvas>, <video>, <blockquote>, <pre>, <ul>, <ol>, <figcaption>, <figure>, <hr>, <article>, <section>, etc. ```

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/000/588/original/Inline_and_block_elements_in_HTML5.png?1625064015)

### 22\. What is the difference between `<figure> tag and <img> tag`?

The `<figure>` tag specifies the self-contained content, like diagrams, images, code snippets, etc. `<figure>` tag is used to semantically organize the contents of an image like image, image caption, etc., whereas the `<img>` tag is used to embed the picture in the HTML5 document.

### 23 **Tables** in HTML
The HTML table tag is used to display data in tabular form (row * column). It also manages the layout of the page, e.g., header section, navigation bar, body content, footer section. Here is the list of tags used while displaying the data in the tabular form:

Tag	Description
```
<table>	It defines a table.
<tr>	It defines a row in a table.
<th>	It defines a header cell in a table.
<td>	It defines a cell in a table.
<caption>	It defines the table caption.
<colgroup>	It specifies a group of one or more columns in a table for formatting.
<col>	It is used with <colgroup> element to specify column properties for each column.
<tbody>	It is used to group the body content in a table.
<thead>	It is used to group the header content in a table.
<tfooter>	It is used to group the footer content in a table.
```

### 24\. What is the **canvas** element in HTML5?

The `<canvas> `element is a container that is used to draw graphics on the web page using scripting language like JavaScript. It allows for dynamic and scriptable rendering of 2D shapes and bitmap images. There are several methods in canvas to draw paths, boxes, circles, text and add images. For Example:

```
1.  <canvas id="myCanvas1" width="300" height="100" style="border:2px solid;">    
2.  Your browser does not support the HTML5 canvas tag.    
3.  </canvas>
```
### 25) What is the use of a **span** tag?

The span tag is used for following things:
-   For adding color on text
-   For adding background on text
-   Highlight any color text

