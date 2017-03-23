 /* this is for IE6 */ /* This is a comment, for telling what the css is for. */


body { /* Element Type Selector */
  font-family: Arial, sans-serif; /* this line is a declaration */
  /* Property */ /* Values */
}

/* Class Type Selector, matches HTML element with class="navigation" */
.navigation {
  width: 1000px;
  margin: 0 auto;
}

/* ID Selector, matches HTML element with id="navigation"  */
#navigation { /* Slow */
  width: 1000px;
  margin: 0 auto;
}

/* Universal Selector, the asterisk character is the universal selector */
.navigation ul * { /* Slow */
  width: 100px;
  float: left;
}

/* Attribute Selector, match element with style="[anything]" */
p[style] {
  color: #1e1e1e;
}

/* Attribute Selector, matches input elements with type="text" */
input[type="text"] {
  border: solid 1px #ccc;
}

/* Pseudo-Class, the word "hover" along with the preceding colon is the pseudo-class */
/* Match elements that actually exist */
a:hover { /* More example, :visited, :focus, and :first-child :last-child :nth-child(even) */
  text-decoration: none;
}

/* Pseudo-Element, CSS2 "first-letter" including the preceding colon is the pseudo-element */
/* Target elements that can change depending on the actual html. */
p:first-letter {
  display: block;
  float: left;
  margin: 0 5px 5px 0;
}

/* Pseudo-Element, CSS3 pseudo-elements have double colons */
::selection {
  background: green;
}

/* Combinator, In all 4 examples */
/* whatever appears between "div" and "p" is a combinator */
/* in the first example, the combinator is a space character */
div p { /* descendant selectors (with a space character) */
  color: #222;
}

div>p { /* child selectors (with the “>” character) */
  color: #333;
}

div+p { /* adjacent sibling selectors (with the “+” character) */
  color: #444;
}

div~p { /* general sibling selectors (with the “~” character). */
  color: #555;
}

/* At-Rule, an instruction given in a CSS document using the @ character */
@import url(secondary.css);

@media print {
  #container {
    width: 500px;
  }
}

<h1>Heading Level 1</h1>
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>

<p>Steve Jobs was a co-founder and longtime chief executive officer at Apple. On June 12, 2005, Steve gave the commencement address at Stanford University.</p>

<p>In his address Steve urged graduates to follow their dreams and, despite any setbacks, to never give up&ndash;advice which he sincerely took to heart.</p>

<!-- Strong importance -->
<p><strong>Caution:</strong> Falling rocks.</p>

<!-- Stylistically offset -->
<p>This recipe calls for <b>bacon</b> and <b>baconnaise</b>.</p>

<!-- Stressed emphasis -->
<p>I <em>love</em> Chicago!</p>

<!-- Alternative voice or tone -->
<p>The name <i>Shay</i> means a gift.</p>

<br>

<header> header is used to identify the top of a page, article, section, or other segment of a page </header>
<br>
<nav> Navigation is reserved for primary navigation sections.</nav>
<br>
<a> a is for Miscellaneous one-off links </a>
<br>
<article>The article element is used to identify a section of independent, self-contained content that may be independently distributed or reused.</article>
<br>

<section>section element is used to identify a thematic grouping of content, which generally, but not always, includes a heading.</section>
Deciding Between "article", "section", or "div"" Elements
div- solely for styling purpose
article-content adds to document outline and can be independently
section-content adds to document outline represents a thematic group of content
<br>

<aside> aside sidebars, inserts, or brief explanations, that is tangentially related to the content surrounding it</aside>
<br>
<footer> footer identifies the closing or end of a page, article, section, or other segment of a page</footer>






#### Calculating Specificity ####

The type selector has the lowest specificity weight and holds a point value of 0-0-1.


The class selector has a medium specificity weight and holds a point value of 0-1-0.


Lastly, the ID selector has a high specificity weight and holds a point value of 1-0-0. 

<!-- ID selector over Type selector Example -->
<p id="food">...</p>  color will be green rather than orange.

#food {
  background: green;
}
p {
  background: orange;
}
<!-- END Example -->


#### Combining Selectors ####

<!-- ID selector over Type selector Example -->
<div class="hotdog">
  <p>...</p> background-color brown
  <p>...</p> background-color brown
  <p class="mustard">...</p> background-color yellow
</div>

.hotdog p {
  background: brown;
}
.hotdog p.mustard {
  background: yellow;
}

<!-- END Example -->


<!-- Color Example -->

color name
.task {
  background: red;
}
.count {
  background: maroon;
}

hex
.task {
  background: #800000;
}
.count {
  background: #ff0;
}

rgb and rgba(opaque percent 0 is transparent, 100 is 100% opaque)
.task {
  background: rgba(128, 0, 0);
}
.count {
  background: rgba(255, 255, 0, .25);
}


hsl and hsla
.task {
  background: hsl(0, 100%, 25%);
}
.count {
  background: hsla(60, 100%, 50%, .25);
}

<!-- END Example -->

<!-- Length Example -->

Lengths
absolute length


pixel -> px
1/96th inch

Relative Lengths

.col {
  width: 50%; parents 50%;
}

.banner {
  font-size: 14px;
  width: 5em; number times closest font-size, or closest parent font-size
}
<!-- END Example -->


#### Display ####
<!-- Display Example -->

display: inline; <!-- Inline-level elements occupy only the width their content requires and line up on the same line  -->

display: block; <!-- block-level elements occupy any available width, regardless of their content, and begin on a new line -->

display: inline-block; <!-- allow an element to behave as a block-level element, accepting all box model properties, and the element will be displayed in line with other elements, and it will not begin on a new line by default. -->

display: none; <!-- completely hide an element and render the page as if that element doesn’t exist, Any elements nested within this element will also be hidden. -->

<!-- END Example -->


#### Box Model ####
<!-- Length Example -->
##### Every element on a page is a rectangular box. #####
box model
width -> margin-right + border-right + padding-right + width + padding-left + border-left + margin-left
height -> margin-top + border-top + padding-top + height + padding-bottom + border-bottom + margin-bottom

div {
  margin: 20px; <!-- block: all attribute, inline: left & right -->
  border: 6px solid #949599;
  padding: 20px;  <!-- block: all attribute, inline: all attribute -->
                  <!-- vertical padding may blend into the line above or below the given element, but it will be displayed. -->
  width: 400px; <!--  non-inline element -->
  height: 100px; <!--  non-inline element -->
}

Width: 492px = 20px + 6px + 20px + 400px + 20px + 6px + 20px
Height: 192px = 20px + 6px + 20px + 100px + 20px + 6px + 20px

##### Margin and Padding #####

div {
  margin: 20px; <!-- All four, top right bottom left -->
  margin: 10px 20px; <!-- (top, bottom), (right, left)  -->
  margin: 10px 20px 0 15px; <!-- top, right, bottom, left  -->
  margin-top: 10px;
  margin-bottom: 0px;
  margin-right: 20px;
  margin-left: 15px;
}

##### Border #####

div {
  border: 6px solid #949599;
        width style color

  border-width: 12px;

  border-bottom: 6px solid #949599;
               width style color

  border-bottom-width: 12px;
}

div {
  border-radius: 5px;

  border-radius: 50%;  circle

  border-radius: 15px 75px;
              (top-left/bottom-right,  top-right/bottom-left)

  border-radius: 15px 75px 15px 75px;
         (top-left, top-right, bottom-right, bottom-left)

  border-top-right-radius: 5px;
}

##### css3 box-sizing #####
1. content-box
2. padding-box
3. border-box

###### content-box ######

div {
  -webkit-box-sizing: content-box;
     -moz-box-sizing: content-box;
          box-sizing: content-box;
}

###### padding-box ######
div {
  box-sizing: padding-box;
  width: 400px;
  margin: 5px;
  border: 10px;
  padding: 20px;
}
Actual width is 430px = 5+10+400+10+5;

###### border-box ######
div {
  box-sizing: border-box;
  width: 400px;
  margin: 5px;
  border: 10px;
  padding: 20px;
}
Actual width is 410px = 5+400+5;


<!-- END Example -->

##### float #####

img {
  float: left; <!-- take an element, remove it from the normal flow of a page, and position it to the left or right of its parent element -->
  
  clear: left; <!-- Clear left, right and both -->
}


/*
  ========================================
  Clearfix
  ========================================
*/
.group:before,
.group:after {
  content: "";
  display: table;
}
.group:after {
  clear: both;
}
.group {
  clear: both;
  *zoom: 1;
}

##### inline-block #####

section {
  display: inline-block;
  width: 30%;
}

###### inlin-block white spaces issue ######
The first solution is to put each new <section> element’s opening tag on the same line as the previous <section> element’s closing tag. Rather than using a new line for each element, we’ll end and begin elements on the same line. 
<header>...</header>
<section>
  ...
</section><section>
  ...
</section><section>
  ...
</section>
<footer>...</footer>

<header>...</header>
<section>
  ...
</section><!--
--><section>
  ...
</section><!--
--><section>
  ...
 </section>
 <footer>...</footer>


#### Uniquely Positioning Elements ####
Default is static

<div>...</div>
<div class="offset">...</div>
<div>...</div>


Relative
div {
  height: 100px;
  width: 100px;
}
.offset {
  left: 20px;
  position: relative;
  top: 20px;
}

Absolute Positioning
f absolute will not appear within the normal flow of a document, and the original space and position of the absolutely positioned element will not be preserved.

Additionally, absolutely positioned elements are moved in relation to their closest relatively positioned parent element. Should a relatively positioned parent element not exist, the absolutely positioned element will be positioned in relation to the <body> element. That’s quite a bit of information; let’s take a look at how this works inside some code:


##### Typeface vs Font #####
A typeface is what we see. It is the artistic impression of how text looks, feels, and reads.

A font is a file that contains a typeface. Using a font on a computer allows the computer to access the typeface.

In short, font include typeface.

###### Color ######

html {
  color: #555;
}

###### Font Family ######

body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
                (primary font choice, secondary, thirdly ...)
}

###### Font Size ######
body {
  font-size: 14px;
}

###### Font Style #######
.special {
  font-style: italic;
  (normal, italic, oblique, and inherit)
}

###### Font Variant #######
.firm {
  font-variant: small-caps;
}

###### Font Weight #######
.daring {
  font-weight: bold/700;
}

###### Line Height #######
Best practice
line-height to around one and a half times our font-size property value.

body {
  line-height: 22px;
}

vertically center the text
.btn {
  height: 22px;
  line-height: 22px; 
}

###### Shorthand Font Properties ######
html {
  font: italic small-caps bold 14px/22px "Helvetica Neue", Helvetica, Arial, sans-serif;
        (font-style, font-variant, font-weight, font-size, line-height, and font-family)
}

###### Text Align ######
left, right, center, justify, and inherit.
p {
  text-align: center;
}

###### Text Decoration ######
none, underline, overline, line-through, and inherit
.note {
  text-decoration: underline;
}

###### Text Indent ######
none, underline, overline, line-through, and inherit
p {
  text-indent: 20px;
}


###### Text Shadow ######
p {
  text-shadow: 3px 6px 2px rgba(0, 0, 0, .3);
  (shadow’s horizontal offset, vertical offset, blur radius and color)
}

##### box-shadow #####
p {
  box-shadow: 3px 6px 2px (optional 1px) rgba(0, 0, 0, .3);
  (shadow’s horizontal offset, vertical offset, blur radius, spread of shadow color)
}

##### Text Transform #####
none, capitalize, uppercase, lowercase, and inherit.
p {
  text-transform: uppercase;
}

##### Letter Spacing #####
p {
  letter-spacing: -.5em;
}

##### Word Spacing #####
p {
  word-spacing: .25em;
}

#### Web-Safe Fonts ####
Arial
Courier New, Courier
Garamond
Georgia
Lucida Sans, Lucida Grande, Lucida
Palatino Linotype
Tahoma
Times New Roman, Times
Trebuchet
Verdana

##### Embedding Web Fonts #####

@font-face {
  font-family: "Lobster";
  src: local("Lobster"), url("lobster.woff") format("woff");
}
body {
  font-family: "Lobster", "Comic Sans", cursive;
}

##### Including Citations & Quotes #####
<cite>: Used to reference a creative work, author, or resource
<q>: Used for short, inline quotations
<blockquote>: Used for longer external quotations



##### Background Color #####
div {
  background-color: #b2b2b2;
  background-color: rgba(0, 0, 0, .3); <!-- IE 8 not support transparent-->
}

##### Background Image #####
div {
  background-image: url("alert.png");
}

##### Background Repeat #####
repeat, repeat-x, repeat-y, and no-repeat
div {
  background-repeat: no-repeat;
}

##### Background Position #####

div {
  background-image: url("alert.png");
  background-position: 20px 10px;  // 0 0 (left top) 100% 0 (right top) 100% 100% (right bottom) 0 100% (left bottom)
  background-repeat: no-repeat;

  // shor hand value
  background: #b2b2b2 url("alert.png") 20px 10px no-repeat;
}

##### Linear Gradient Background #####
div {
  background: #466368;
  background: -webkit-linear-gradient(#648880, #293f50);
  background:    -moz-linear-gradient(#648880, #293f50);
  background:         linear-gradient(#648880, #293f50);
}

div {
  background: #466368;
  background: linear-gradient(to right bottom, #648880, #293f50);
}

##### Radial Gradient Background #####
div {
  background: #466368;
  background: radial-gradient(#648880, #293f50);
}

##### Gradient Color Stops #####
div {
  background: #648880;
  background: linear-gradient(to right, #f6f1d3, #648880, #293f50);
}

##### CSS3 Background Size #####


##### Unordered Lists #####
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>

##### Ordered Lists #####
<ol>
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>

<ol start="30">
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>

<ol reversed>
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>

##### Description Lists #####
<dl>
  <dt>study</dt>
  <dd>The devotion of time and attention to acquiring knowledge on an academic subject, especially by means of books</dd>
  <dt>design</dt>
  <dd>A plan or drawing produced to show the look and function or workings of a building, garment, or other object before it is built or made</dd>
  <dd>Purpose, planning, or intention that exists or is thought to exist behind an action, fact, or material object</dd>
  <dt>business</dt>
  <dt>work</dt>
  <dd>A person's regular occupation, profession, or trade</dd>
</dl>

##### Nesting Lists #####
*** The only element we can place as a direct child of the <ul> and <ol> elements is the <li> element.

<ol>
  <li>Walk the dog</li>
  <li>Fold laundry</li>
  <li>
    Go to the grocery and buy:
    <ul>
      <li>Milk</li>
      <li>Bread</li>
      <li>Cheese</li>
    </ul>
  </li>
  <li>Mow the lawn</li>
  <li>Make dinner</li>
</ol>

#####  List Style Type Values #####
list-style-type
none
disc
circle
square
decimal
decimal-leading-zero
lower-roman
upper-roman
lower-greek
lower-alpha / lower-latin
uppper-alpha / upper-latin
armenian
georgian

##### Image as List Item Marker #####
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>

li {
  background: url("arrow.png") 0 50% no-repeat;
  padding-left: 12px;

  list-style-type: none;

  list-style-position: inside;
  list-style: none inside;
}

##### Horizontal List with scroll #####

ul { 
  width: 160px;
  display: block;
  white-space: nowrap;
  overflow: auto; 
}
li {
  display: inline-block;
  width: 80px;
  margin: 0 10px;
}

##### img #####
<img src="dog.jpg" alt="A black, brown, and white dog wearing a kerchief">
src support gif, jpg and png
alt shows in place when image is missing
jpg provides quality images with high color counts while maintaing a decent file size, ideal for faster load times.

img {
  height: 200px;
  width: 200px;
}

##### img vs background-image #####
img for semantics value
background-image for design purpose.

##### audio #####
<audio src="jazz.ogg" autoplay></audio>
<audio src="jazz.ogg" controls></audio>
ogg, mp3, wav

##### Audio Fallbacks #####
<audio controls>
  <source src="jazz.ogg" type="audio/ogg">
  <source src="jazz.mp3" type="audio/mpeg">
  <source src="jazz.wav" type="audio/wav">
  Please <a href="jazz.mp3" download>download</a> the audio file.
</audio>

##### video #####
<video src="earth.ogv" controls></video>
<video src="earth.ogv" controls poster="earth-video-screenshot.jpg"></video>

##### Video Fallbacks #####
<video controls>
  <source src="earth.ogv" type="video/ogg">
  <source src="earth.mp4" type="video/mp4">
  Please <a href="earth.mp4" download>download</a> the video.
</video>

##### iframe #####
<iframe src="https://www.google.com/maps/embed"></iframe>
border, width, height

##### Text Fields #####
<input type="text" name="username">

<input type="date" name="birthday">
<input type="time" name="game-time">
<input type="email" name="email-address">
<input type="url" name="website">
<input type="number" name="cost">
<input type="tel" name="phone-number">

##### Text Area #####
<textarea name="comment" rows="1">Add your comment here</textarea>

##### Radio Buttons #####
<input type="radio" name="day" value="Friday" checked> Friday
<input type="radio" name="day" value="Saturday"> Saturday
<input type="radio" name="day" value="Sunday"> Sunday

##### Check Boxes #####
<input type="checkbox" name="day" value="Friday" checked> Friday
<input type="checkbox" name="day" value="Saturday"> Saturday
<input type="checkbox" name="day" value="Sunday"> Sunday

##### Options #####
<select name="day">
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>

##### Multiple Options #####

<select name="day" multiple>
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>

##### Form Buttons #####
<input type="submit" name="submit" value="Send">

<button name="submit">
  <strong>Send Us</strong> a Message
</button>

##### Hidden Input #####
<input type="hidden" name="tracking-code" value="abc-123">

##### File Input #####
<input type="file" name="file">

##### Table #####
<table>
  <caption>Design and Front-End Development Books</caption>
  <thead>
    <tr>
      <th scope="col" >Item</th>
      <th scope="col">Availability</th>
      <th scope="col">Qty</th>
      <th scope="col">Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Don&#8217;t Make Me Think by Steve Krug</td>
      <td>In Stock</td>
      <td>1</td>
      <td>$30.02</td>
    </tr>
    <tr>
      <td>A Project Guide to UX Design by Russ Unger &#38; Carolyn Chandler</td>
      <td>In Stock</td>
      <td>2</td>
      <td>$52.94 ($26.47 &#215; 2)</td>
    </tr>
    <tr>
      <td>Introducing HTML5 by Bruce Lawson &#38; Remy Sharp</td>
      <td>Out of Stock</td>
      <td>1</td>
      <td>$22.23</td>
    </tr>
    <tr>
      <td>Bulletproof Web Design by Dan Cederholm</td>
      <td>In Stock</td>
      <td>1</td>
      <td>$30.17</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">Subtotal</td>
      <td>$135.36</td>
    </tr>
    <tr>
      <td colspan="3">Tax</td>
      <td>$13.54</td>
    </tr>
    <tr>
      <td colspan="3">Total</td>
      <td>$148.90</td>
    </tr>
  </tfoot>
</table>

table head
  table row
  table header
table body
  table row
  table data
table footer
  table row
  table data
caption - for heading of the table

##### Table Border Collapse #####
table {
  border-collapse: collapse; // prevent border to stack up
  
  border-collapse: separate; // allow border to stack up
  border-spacing: 4px or 5px 10px; // with spacing of 4px, horizontal then vertical
}
th,
td {
  border: 1px solid #cecfd5;
  padding: 10px 15px;
}

##### Table coloumn span #####
  <thead>
    <tr>
      <th scope="col" colspan="2">Item</th>
      <th scope="col">Qty</th>
      <th scope="col">Price</th>
    </tr>
  </thead>
  vertical-align work on inline, table-cell only
  vertical-align don't work on block, inline-block or element 
  

  ## Advanced Html ##

  Start thinking of websites as systems

### Performance Driven Selectors ###
Keep Selectors Short

/* Bad */
header nav ul li a {...}

/* Good */
.primary-link {...}  // No need to identify parent elements.

/* Bad */
button strong span {...}
button strong span .callout {...}

/* Good */
button span {...}  // Reduce overly specific selector
button .callout {...} // Give strenght to all selectors

### Key Selector ###
selectors are rendered from right to left

/* Bad */
#container header nav {...}

/* Good */
.primary-nav {...}

/* Bad */
article.feat-post {...}

/* Good */
.feat-post {...}

### Reusable Code ###
/* Bad */
.news {
  background: #eee;
  border-radius: 5px;
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, .25);
}
.social {
  background: #eee;
  border-radius: 5px;
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, .25);
}

/* Good */
.news,
.social {
  background: #eee;
  border-radius: 5px;
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, .25);
}

/* Even Better */
.modal {
  background: #eee;
  border-radius: 5px;
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, .25);
}

### gzip Compression ###
.htaccess file needs to be added to the root directory of the web server, labeling the specific files to be gzipped. 
only work on Apache web servers, nginx can be set up, too.

### Image Compression ###
Mac ImageOptim
Windows PNGGauntlet

Width and Height decide how images should be compressed.

### Reduce HTTP Requests ###
<!-- Bad -->
<link href="css/reset.css" rel="stylesheet">
<link href="css/base.css" rel="stylesheet">
<link href="css/site.css" rel="stylesheet">

<!-- Good -->
<link href="css/styles.css" rel="stylesheet">

css and body can be loaded synchronously, js can load one at a time only and stop other things.


### Image Sprites ###
li span {
  background: url("sprite.png") 0 0 no-repeat;
  color: transparent;
  display: block;
  font: 0/0 a;
  height: 16px;
  width: 16px;
}
.italic {
  background-position: -16px 0; //left top
}
.underline {
  background-position: -32px 0;
}
.size {
  background-position: -48px 0;
}

### Image Data URI ###
div {
  background: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAoAAAAICAYAAADA+m62AAAAPUlEQVQYV2NkQAO6m73+X/bdxogujiIAU4RNMVwhuiQ6H6wQl3XI4oy4FMHcCJPHcDS6J2A2EqUQpJhohQAyIyYy0nBAGgAAAABJRU5ErkJggg==") repeat;
}

### Cache Common Files ###
ExpiresByType text/css "access plus 1 year"
ExpiresByType application/javascript "access plus 1 year"
versioning frequently changed css/js files.

### Containing Floats ###
Document Object Mode - an API for HTML and XML documents which provides their structural representation.
parent and child relationship or sibling relationship for elements

<div class="box-set">
  <figure class="box">Box 1</figure>
  <figure class="box">Box 2</figure>
  <figure class="box">Box 3</figure>
  <br>
</div>

.box-set,
.box {
  border-radius: 6px;
}
.box-set {
  background: #eaeaed;
  overflow: auto/hidden;  // This can fix parent height 0
}
.box {
  background: #2db34a;
  float: left;
  margin: 1.858736059%;
  padding: 20px 0;
  text-align: center;
  width: 29.615861214%;
}
br {
  clear: both; // This can fix parent height 0
}

### The Clearfix Technique ###
fix overflow: auto/hidden pitfall
pseudo-element

.box-set:before,
.box-set:after {
  content: "";
  display: table;
}
.box-set:after {
  clear: both;
}
.box-set {
  *zoom: 1;
}

### Position ###

<div class="box-set">
  <figure class="box box-1">Box 1</figure>
  <figure class="box box-2">Box 2</figure>
  <figure class="box box-3">Box 3</figure>
  <figure class="box box-4">Box 4</figure>
</div>

.box-set {
  background: #eaeaed;
}
.box {
  background: #2db34a;
  height: 80px;
  width: 80px;
}
static position: default

relative position: 
  keep static position while setting box-offset: top left right bottom
  if left, right given, priority is given in the direction in which the language is written.

absolute position:
  removed from normal flow
  position related to parent relative, absolute position or body if none parents are found.
  if no width/height specified, use left and top for width or width-left-right, height-top-bottom

fixed position:
<div class="box-set">
  <figure class="box box-1">Box 1</figure>
  <figure class="box box-2">Box 2</figure>
  <figure class="box box-3">Box 3</figure>
  <figure class="box box-4">Box 4</figure>
</div>

.box {
  background: #2db34a;
  height: 80px;
  position: fixed;
  width: 80px;
}
.box-1 {
  top: 6%;
  left: 2%;
}
.box-2 {
  top: 0;
  right: -40px;
}
.box-3 {
  bottom: -10px;
  right: 20px;
}
.box-4 {
  bottom: 0;
}

### Z-Index Property ###
.box-set {
  background: #eaeaed;
  height: 160px;
  position: relative;
}
.box {
  background: #2db34a;
  border: 2px solid #ff7b29;
  position: absolute;
}
.box-1 {
  left: 10px;
  top: 10px;
}
.box-2 {
  bottom: 10px;
  left: 70px;
  z-index: 3;
}
.box-3 {
  left: 130px;
  top: 10px;
  z-index: 2;
}
.box-4 {
  bottom: 10px;
  left: 190px;
  z-index: 1;
}

### Complex selectors ###

#### Descendant Selector ####
article h2 {...}

#### Direct selector ####
article > p { color: red; }
<article>
  <p>
    p1(red)
  </p>
  <div>
    <p>
      p2(black)
    </p>
  </div>
</article>

#### General Sibling Selector ####
h2 ~ p {...}

<p>...</p>
<section>
  <p>...</p>
  <h2>...</h2>
  <p>This paragraph will be selected</p>
  <div>
    <p>...</p>
  </div>
  <p>This paragraph will be selected</p>
</section>

#### Adjacent Sibling Selector ####
h2 + p {...}

<p>...</p>
<section>
  <p>...</p>
  <h2>...</h2>
  <p>This paragraph will be selected</p>
  <div>
    <p>...</p>
  </div>
  <p>...</p>
</section>

### Attribute Selectors ###
#### Attribute Present Selector ####
a[target] {...}
<a href="#" target="_blank">...</a>

#### Attribute Equals Selector ####
a[href="http://google.com/"] {...}
<a href="http://google.com/">...</a>

#### Attribute Contains Selector ####
a[href*="login"] {...}
<a href="/login.php">...</a>

#### Attribute Begins With Selector ####
a[href^="login"] {...}
<a href="/login.php">...</a>

#### Attribute Ends With Selector ####
a[href$=".pdf"] {...}
<a href="/docs/menu.pdf">...</a>

#### Attribute Spaced Selector ####
a[rel~="tag"] {...}
<a href="#" rel="tag nofollow">...</a>

#### Attribute Hyphenated Selector ####
a[lang|="en"] {...}
<a href="#" lang="en-US">...</a>

### Pseudo-classes ###

#### Link Pseudo-classes ####
   a:link link has been visited
a:visited link hasn't been visited

#### User Action Pseudo-classes ####
 a:hover {...} // hovered
a:active {...} // engaging such as clicking
 a:focus {...} // make the element focus page

#### User Interface State Pseudo-classes ####
 input:enabled {...}  // default
 input:disabled {...} // disabled

  input:checked {...} // checkbox checked
  input:indeterminate {...} // nor check or checked

#### Structural & Position Pseudo-classes ####
li:first-child {...}
li:last-child {...}
div:only-child {...}

<ul>
  <li>This list item will be selected</li>
  <li>
    <div>This div will be selected</div>
  </li>
  <li>
    <div>...</div>
    <div>...</div>
  </li>
  <li>This list item will be selected</li>
</ul>

#### :first-of-type, :last-of-type, & :only-of-type ####
p:first-of-type {...}
p:last-of-type {...}
img:only-of-type {...}

<article>
  <h1>...</h1>
  <p>This paragraph will be selected</p>
  <p>...</p>
  <img src="#"><!-- This image will be selected -->
  <p>This paragraph will be selected</p>
  <h6>...</h6>
</article>

#### :nth-child(n) & :nth-last-child(n) ####
li:nth-child(3n) {...}

<ul>
  <li>...</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>...</li>
  <li>This list item will be selected</li>
</ul>

li:nth-child(2n+3) {...}
<ul>
  <li>...</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
</ul>

li:nth-child(-n+4) {...}

<ul>
  <li>This list item will be selected</li>
  <li>This list item will be selected</li>
  <li>This list item will be selected</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>...</li>
</ul>

p:nth-of-type(3n) {...}

<article>
  <h1>...</h1>
  <p>...</p>
  <p>...</p>
  <p>This paragraph will be selected</p>
  <h2>...</h2>
  <p>...</p>
  <p>...</p>
  <p>This paragraph will be selected</p>
</article>

http://example.com/index.html#hello  stackoverflow
section:target {...}
<section id="hello">...</section>

div:empty {...}

<div>Hello</div>
<div><!-- Coming soon --></div><!-- This div will be selected -->
<div></div><!-- This div will be selected -->
<div> </div>
<div><strong></strong></div>

div:not(.awesome) {...}
:not(div) {...}

<div>This div will be selected</div>
<div class="awesome">...</div>
<section>This section will be selected</section>
<section class="awesome">This section will be selected</section>


.alpha:first-letter,
.bravo:first-line {
  color: #ff7b29;
  font-size: 18px;
}
<p class="alpha">Lorem ipsum dolor...</p>
<p class="bravo">Integer eget enim...</p>


a:after {
  color: #9799a7;
  content: " (" attr(href) ")";
  font-size: 11px;
}
<a href="http://google.com/">Search the Web</a>
<a href="http://learn.shayhowe.com/">Learn How to Build Websites</a>

::-moz-selection {
    background: #ff7b29;
}
::selection {  // pseudo-elements in css must start with ::
  background: #ff7b29;
}

Flexible Grid
target ÷ context = result
section,
aside {
  margin: 1.858736059%; /*  10px ÷ 538px = .018587361 */
}
section {
  float: left;
  width: 63.197026%;    /* 340px ÷ 538px = .63197026 */   
}
aside {
  float: right;
  width: 29.3680297%;  /* 158px ÷ 538px = .293680297 */
}

#### Media Queries ####
/* @media Rule */
@media all and (max-width: 1024px) {...}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...}

@media all and (min-width: 800px) and (max-width: 1024px) {...}

@media not screen and (color) {...}

@media only screen and (orientation: portrait) {...}

@media all and (min-width: 320px) and (max-width: 780px) {...}

@media all and (min-device-aspect-ratio: 16/9) {...}

@media all and (max-width: 420px) { // When width smaller than 420px
  section, aside {
    float: none;
    width: auto;
  }
}

@media screen and (min-width: 400px)  {...}
@media screen and (min-width: 600px)  {...}
@media screen and (min-width: 1000px) {...}
@media screen and (min-width: 1400px) {...}

<meta name="viewport" content="width=device-width">
<meta name="viewport" content="initial-scale=2">
<meta name="viewport" content="minimum-scale=0">
<meta name="viewport" content="user-scalable=yes">

@extend .alert


$();
jQuery();

$(document).ready(function(event){ 
  // jQuery code 
});

$('.feature');           // Class selector
$('li strong');          // Descendant selector
$('em, i');              // Multiple selector
$('a[target="_blank"]'); // Attribute selector
$('p:nth-child(2)');     // Pseudo-class selector

$('div').click(function(event){ 
  $(this);
});

$('div:has(strong)');

$('div').not('.type, .collection').parent();

// Gets the value of the alt attribute
$('img').attr('alt');

// Sets the value of the alt attribute
$('img').attr('alt', 'Wild kangaroo');


$('li:even').addClass('even-item');
$('p').removeClass();
$('abbr').attr('title', 'Hello World');

$('h1 span').css('font-size', 'normal');
$('div').css({
  fontSize: '13px', 
  background: '#f60'
});
$('header').height(200);
$('.extend').height(30 + 'em');

$('section').prepend('<h3>Featured</h3>');
$('a[target="_blank"]').after('<em>New window.</em>');
$('h1').text('Hello World');

$('li').click(function(event){
  $(this).addClass('saved-item');
});


$('li').on('click', function(event){
  $(this).addClass('saved-item');
});


$('.pagination').on('hover', function(event){
  $('a#up').click();
});

