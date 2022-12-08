<!-- This is HTML Comment -->
## Difference between Html and Html5

| Features | Html | Html5 |
| --- | --- | --- |
| definition | A hypertext markup language (HTML) is the primary language for developing web pages. | HTML5 is a new version of HTML with new functionalities with markup language with Internet technologies. |
| Multimedia support | Language in **HTML** does not have support for video and audio. | **HTML5** supports both video and audio. |
| Storage | The HTML browser uses cache memory as temporary storage. | HTML5 has the storage options like:**application cache, SQL database,** and **web storage**. |
| Graphics support | In HTML, vector graphics are possible with tools Like**Silver light, Adobe Flash, VML,** etc. | In HTML5, vector graphics are supported by default. |
| Threading | In HTML, the browser interface and JavaScript running in the same thread. | The HTML5 has the JavaScript Web Worker API, which allows the browser interface to run in multiple threads. |

## Document Summary

```HTML
<!-- Document Summary -->

<!DOCTYPE html> <!-- Tells the browser that HTML5 version of HTML to be recognized by the browser -->

<html lang="en"></html> <!-- The HTML lang attribute is used to identify the language of text content on the web. This information helps search engines return language specific results, -->

<head></head> <!-- Contains Information specific to the page like title, styles and scripts -->

<title></title> <!-- Title for the page that shows up in the browser title bar -->

<body></body> <!-- Content that the user will see -->

```

---

## Document Information

```HTML
<!-- Document Information -->

<base/> <!-- Usefull for specifying relative links in a document -->

<style></style> <!-- Contains styles for the html document -->

<meta/> <!-- Contains additional information about the page, author, page description and other hidden page info -->

<script></script> <!-- Contains all scripts internal or external -->

<link/> <!-- Used to create relationships with external pages and stylesheets -->

```

---

## Document Structure

```HTML
<!-- Document Structure -->

<h1></h1> ... <h6></h6> <!-- All six levels of heading with 1 being the most promiment and 6 being the least prominent -->

<p></p> <!-- Used to organize paragraph text -->

<div></div> <!-- A generic container used to denote a page section -->

<span></span> <!-- Inline section or block container used for creating inline style elements -->

<br/> <!-- Creates a line-break -->

<hr> <!-- Creates a sectional break into HTML -->

```

**HTML5 New Tags**

```HTML
<header></header> <!-- Defines the header block for a document or a section -->

<footer></footer> <!-- Defines the footer block for a document or a section -->

<main></main> <!-- Describes the main content of a document -->

<article></article> <!-- Identifies an article inside a document -->

<aside></aside> <!-- Specifies content contained in a document sidebar -->

<section></section> <!-- Defines a section of a document -->

<figure></figure> <!-- An independent content block featuring images, diagrams or illustrations -->

<figcaption></figcaption> <!-- Caption that describe a figure -->

<nav></nav> <!-- Navigation links for the user in a document -->

```
---

## Text Formatting

```HTML
<!-- Text Formatting -->

<strong></strong> and <b></b> <!-- Makes text contained in the tag as bold -->

<em></em> and <i></i> <!-- Alternative way to make the text contained in the tag as italic -->

<del></del> <!-- Creates a strike through the text element -->

<pre></pre> <!-- Preformatted monospace text block with some spacing intact -->

<blockquote></blockquote> <!-- Contains long paragraphs of quotations often cited -->

<abbr></abbr> <!-- Contains abbreviations while also making the full form avaialable -->

<address></address> <!-- Used to display contact information -->

<code></code> <!-- Used to display inline code snippets -->

<q></q> <!-- Defines a short inline quotation -->

<sub></sub> <!-- Defines subscripted text -->

<sup></sup> <!-- Defines superscripted text -->

<kbd></kbd> <!-- Specifies text as keyboard input -->

<small></small> <!-- Specifies small text -->

<ins></ins> <!-- Defines a text that has been inserted into the document -->
```

**HTML5 New Tags**

```HTML
<mark></mark> <!-- Displays a portion of highlighted text with in a page content -->

<bdi></bdi> <!-- Helps you format parts of text in a different direction than other text -->

<time></time> <!-- Identifies the time and date -->

<wbr> <!-- A line break within the content -->

```

---

## Links Formatting

```HTML
<!-- Links Formatting -->

<a href="url"></a> <!-- Used to link to external or internal pages of a wbesite -->

<a href="mailto:email@example.com"></a> <!-- Used to link to an email address -->

<a href="name"></a> <!-- Used to link to a document element -->

<a href="#name"></a> <!-- Used to link to specific div element -->

<a href="tel://####-####-##"></a> <!-- Used to display phone numbers and make them clickable -->
```

---

## Image and Multimedia

```HTML
<img src="url" alt="text"> <!-- Used to display images in a webpage where src="url" contains the link to the image source and alt="" contains an alternative text to display when the image is not displayed -->

```

---

## List Formatting

```HTML
<!-- List Formatting -->

<ol></ol> <!-- Used to create ordered lists with numbers in the items -->

<ul></ul> <!-- Used to display unordered lists with numbers in the items -->

<li></li> <!-- Contains list items inside ordered and unordered lists -->

<dl></dl> <!-- Contains list item definitions -->

<dt></dt> <!-- Definition of single term inline with body content -->

<dd></dd> <!-- The descrpition of the defined term -->
```

---

## Table Formatting

```HTML
<table></table> <!-- Defines and contains all table related content -->

<caption></caption> <!-- A description of what table is and what it contains -->

<thead></thead> <!-- The table headers contain the type of information defined in each column underneath -->

<tbody></tbody> <!-- Contains the tables data or information -->

<tfoot></tfoot> <!-- Defines table footer -->

<tr></tr> <!-- Contains the information to be included in a table row -->

<th></th> <!-- Contains the information to be included in a single table header -->

<!---------------------------------------------------------------------------------->
<td></td> <!-- Contains actual information in a table cell -->

<!-- Supported attributes -->
rowspan="" <!--Specifies the number of rows a cell should span-->
colspan="" <!--Specifies the number of columns a cell should span-->

<colgroup></colgroup> <!-- Groups a single or multiple columns for formatting purposes -->

<col> <!-- Defines a single column of information inside a table -->
```

---

## Forms Formatting and Attributes

```HTML
<!-- Forms Formatting and Attributes -->

<!---------------------------------------------------------------------------------->
<form action="url"></form> <!-- Form element creates a form and action="" specifies where the data is to be sent to when the visitor submits the form -->

<!-- Supported attributes -->

method="somefunction()" <!-- Contains the type of request (GET, POST... etc) which dictates how to send the data of the form -->

enctype="" <!-- Dictates how the data is to be encoded when the data is sent to the web server. -->

autocomplete="" <!-- Specifies if the autocomplete functionality is enabled or not -->

novalidate <!-- Dictates if the form will be validated or not -->

accept-charset="" <!-- Identifies the character encoding upon form submission -->

target="" <!-- Tell where to display the information upon form submission. Possible values: '_blank', '_self', '_parent', '_top' -->
<!---------------------------------------------------------------------------------->


<fieldset disabled="disabled"></fieldset> <!-- Identifies the group of all fields in the form -->

<!---------------------------------------------------------------------------------->
<label for=""></label> <!-- A simple field label telling the user what to type in the field , to connect a label to an `input` we use id -->


 <label for="usr">Enter the username</label>
 <input id="usr" type="text" placeholder="username">

<!---------------------------------------------------------------------------------->

<button type="submit/button/reset"></button> <!-- A clickable button to submit the form -->

<legend></legend> <!-- The form legend acts as a caption for the fieldset element -->


<!---------------------------------------------------------------------------------->
<input type="text/email/number/color/date/time/file/button/checkbox/radio/range/" , placeholder=""> <!-- Input is the input field where the user can input various types of data -->

<!-- Supported attributes -->

name="" <!-- Describes the name of the form -->

width="" <!-- Specifies the width of an input field -->

value="" <!-- Describes the value of the input information field -->

size="" <!-- Specifies the input element width in characters -->

maxlength="" <!-- Specifies the maximum input character numbers -->

required="" <!-- Specifies if the input field is required to fill in before submitting the form -->

step="" <!-- Identifies the legal number intervals of the input field -->

placeholer="" <!-- Text that appears in the form control when it has no value set-->

pattern="" <!--Valid for text, search, url, tel, email, and password, the pattern attribute defines a regular expression -->
<!---------------------------------------------------------------------------------->


<textarea name="" id="" cols="30" rows="10"> <!-- Specifies a large input text field for longer messages --> </textarea>


<!---------------------------------------------------------------------------------->
<select name="" id=""></select> <!-- Describes a dropdown box for users to select from variety of choices -->

<!-- Supported attributes -->

name="" <!-- The name for a dropdown combination box -->

size="" <!-- Specifies the number of available options -->

multiple <!-- Allows for multiple option selections -->

required <!-- Requires that a value is selected before submitting the form -->

autofocus <!-- Specifies that the dropdown automatically comes to focus once the page loads -->
<!---------------------------------------------------------------------------------->


<optgroup></optgroup> <!-- Specifies the entire grouping of available options -->

<option value="" selected></option> <!-- Defines one of the avaialble option from the dropdown list -->

```

**HTML5 New Tags**

```HTML
<meter></meter> <!-- Describes the scalar measurement with in a known array -->

<progress></progress> <!-- Displays the progress of a task usually a progress bar -->

```
---

## Objects and iFrames

```HTML
<!-- Objects and iFrames -->

<object data=""></object> <!-- Describes and embed file type including audio, video, PDF's, images -->

<!-- Supported attributes -->

type="" <!-- Describes the type of media embedded -->

height="" <!-- Describes the height of the object in pixels -->

width="" <!-- Describes the width of the object in pixels -->

usemap="" <!-- This is the name of the client-side image map in the object -->


<iframe src="" frameborder="0"></iframe> <!-- Contains an inline frame that allows to embed external information -->


<embed src="" type=""> <!-- Acts as a container for external application or plug-in -->

src="" <!-- The source of the external file you're embedding -->

width="" <!-- Describes the width of the iframe in pixels -->
```

---

## Other Elements

```HTML
<dialog></dialog> <!-- A dialog box or a window -->

<details></details> <!-- Describes additonal information that user can view or hide -->

<summary></summary> <!-- Contains a visible heading for details element -->

<canvas></canvas> <!-- Allows to draw 2D shapes on the web page with the help of javascript -->

<map></map> <!-- Specifies an image map -->
```

## Inline vs Block Element

![](https://miro.medium.com/max/1400/1*AFeOAqXNJJdfYAjfXiJ9AQ.jpeg)




## HTML in VS Code
Shortcut of Boilerplate HTML  in VS Code : `!  + Tab`
Format Document : `Ctrl + Shift + P --> Format document` or  `Shift + Alt + F`
Copy line up/down : `Shift+Alt + ↓ / ↑`
[Emmet Cheatsheet](https://docs.emmet.io/cheat-sheet/)

## HTML Entities 
An HTML **entity** is a piece of text ("string") that begins with an ampersand (`&`) and ends with a semicolon (`;`). Entities are frequently used to display reserved characters (which would otherwise be interpreted as HTML code), and invisible characters (like non-breaking spaces).
use a [reference chart 1](https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references) or [reference chart 2](https://www.htmlquick.com/reference/character-entity-reference.html) or [decoder tool](https://mothereff.in/html-entities).


### Reserved characters
Some special characters are reserved for use in HTML, meaning that your browser will parse them as HTML code.

| Character | Entity | Note |
| --- | --- | --- |
| & | `&amp;` | Interpreted as the beginning of an entity or character reference. |
| < | `&lt;` | Interpreted as the beginning of a tag |
| > | `&gt;` | Interpreted as the ending of a tag |
| " | `&quot;` | Interpreted as the beginning and end of an attribute value. |


