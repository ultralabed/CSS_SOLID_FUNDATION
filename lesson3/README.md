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
