# Front end library: jQuery {ignore=true}

## Content {ignore=true}


<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

* [Learn how script tags and document ready work](#learn-how-script-tags-and-document-ready-work)
* [Target HTML elems. with selectors using jQuery](#target-html-elems-with-selectors-using-jquery)
* [Target elements by class using jQuery](#target-elements-by-class-using-jquery)
* [Target elems by id using jQuery](#target-elems-by-id-using-jquery)
* [Del ur jQuery funs](#del-ur-jquery-funs)
* [Target the same elem with multiple jQuery selectors](#target-the-same-elem-with-multiple-jquery-selectors)
* [Remove classes from an elem with jQuery](#remove-classes-from-an-elem-with-jquery)
* [Change the CSS of an elem using jQuery](#change-the-css-of-an-elem-using-jquery)
* [Disable an elem using jQuery](#disable-an-elem-using-jquery)
* [Change text inside an elem using jeQuery](#change-text-inside-an-elem-using-jequery)
* [Remove an elem using jQuery](#remove-an-elem-using-jquery)
* [Use appendTo to move elems with jQuery](#use-appendto-to-move-elems-with-jquery)
* [Clone an elem using JQuery](#clone-an-elem-using-jquery)
* [Target the parent of an elem using jQuery](#target-the-parent-of-an-elem-using-jquery)
* [Target the children of an elem using jQuery](#target-the-children-of-an-elem-using-jquery)
* [Target a specific child of an elem using jQuery](#target-a-specific-child-of-an-elem-using-jquery)
* [Target even elems using jQuery](#target-even-elems-using-jquery)
* [Use jQuery to modify the entire page](#use-jquery-to-modify-the-entire-page)

<!-- /code_chunk_output -->


## Learn how script tags and document ready work

jQuery is the most popular JS tool.

At first you have add

```
  $(document).ready(function() {
    
  });
```
into ur `<script></script>` or `.js` file, this make sure that all the functions run after document ready or avoid bugs.

## Target HTML elems. with selectors using jQuery

All jQuery funs start with a `$`, usually referred to as a `dollor sign operator`, or as `bling`.

jQuery often selects an HTML elem. with a `selector`, then does sth to that elem.

For example, let's make all of ur `button` elems. bounce. Just add this code inside ur doc ready function:

```
$("button").addClass("animated bounce");
```

Note that we've already included both the jQuery library and the Animate.css library in the background so that u can use them in the editor. So u are using jQuery to apply the Animate.css `bounce` class to your `button` elems.

## Target elements by class using jQuery

U see how we made all of ur `button` elems bounce? We selected them with `$("button")`, then we add some CSS classes to them with `.addClass("animated bounce");`.

U just used jQuery's `.addClass()` fun, which allows u to add classes to elems.

1st, target ur `div` elems with the class `well` by using the `$(".well")` selector.

Note that, just like with CSS declarations, u type a `.` before the class's name.

Then use jQuery's `.addClass()` fun to add the classes `animated` and `shake`.

`$(".well").addClass("animated shake");` make all the `.well` elems (with class name of `well`) shake.

```
<script>
  $(document).ready(function() {
    $("button").addClass("animated bounce");
    $(".well").addClass("animated shake");
  });
</script>

<!-- Only change code above this line. -->

<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target" id="target1">#target1</button>
        <button class="btn btn-default target" id="target2">#target2</button>
        <button class="btn btn-default target" id="target3">#target3</button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target" id="target4">#target4</button>
        <button class="btn btn-default target" id="target5">#target5</button>
        <button class="btn btn-default target" id="target6">#target6</button>
      </div>
    </div>
  </div>
</div>
```

**Note**: only the snippt inside the `<script></script>` will be recorded in the following lessons until the snippt of HTML changed.

## Target elems by id using jQuery

`$("#target3").addClass("animated fadeOut");` make the elem with `id` of `target3` fade out.

Sum, the selector rule of jQuery is the same as CSS.

## Del ur jQuery funs

## Target the same elem with multiple jQuery selectors

Using `.addClass()`, add only one class at a time to the same elem.

```
<script>
  $(document).ready(function() {
    $("button").addClass("animated");
    $(".btn").addClass("shake");
    $("#target1").addClass("btn-primary");
  });
</script>
```

As a result, the `#target1` elem will have all 3 attributes because it is the child.

## Remove classes from an elem with jQuery

In the same way u can add classes to an elem with `addClass()` fun, u can remove them with jQuery's `removeClass()` fun.

```
<script>
  $(document).ready(function() {
    $("button").removeClass("btn-default");
  });
</script>
```
will remove the buttons' class `btn-default` which was set previously.

## Change the CSS of an elem using jQuery

We can also cahnge the CSS of an HTML elem directly with jQuery.

jQuery has a fun called `.css()` that allows u to change the the CSS of an elem.

```
<script>
  $(document).ready(function() {
    $("#target1").css("color", "red");
  });
</script>
```
changes the color of elem with `id` of `target1` to red.

## Disable an elem using jQuery

U can change the non-CSS props of HTML elems with jQuery. For example, u can disable buttons.

When disabled the btn become grayed-out and can no longer be clicked.

jQuery has a fun called `.prop()` that allows u to adjust the props of elems.

```
<script>
  $(document).ready(function() {
    $("#target1").prop("disabled", true);
  });
</script>
```

will disable the `#target1` elem.

## Change text inside an elem using jeQuery

jQuery has a fun called `.html()` that lets u add HTML tags and text within an elem. Any content previously within the elem will be completely replaced with the content u provide using this fun.

jQuery also has a similar fun called `.text()` that only alters text without adding tags. In other words, this fun will not evaluate any HTML tags passed to it, but will instead treat it as he text u want to replace the existing content with.

```
<script>
  $(document).ready(function() {
    $("#target4").html("<em>#target4</em>")
  });
</script>
```
reset the text on button `#target4` to be emphasized.

## Remove an elem using jQuery

jQuery has a fun called `.remove()` that will remove an HTML elem entirely.

```
<script>
  $(document).ready(function() {
    $("#target4").remove();
  });
</script>
```

will remove the elem `#target4`.

## Use appendTo to move elems with jQuery

jQuery has a fun called `.appendTO()` that allows u to select HTML elems and append them to another elem.

```
<script>
  $(document).ready(function() {
    $("#target2").appendTo("#right-well")
  });
</script>
```
move elem `#target2` to the div `#right-well`.

## Clone an elem using JQuery

`.clone()` can make a copy of an elem.
It should be combined to other funs when using, and this is called `function chaining`.

```
<script>
  $(document).ready(function() {
    $("#target5").clone().appendTo("#left-well");
  });
</script>
```
clone `#target5` and move it to `#left-well`.

## Target the parent of an elem using jQuery

`.parent()` allows to access the parent of whichever elem selected.

```
<script>
  $(document).ready(function() {
    $("#target1").parent().css("background-color", "red");
  });
</script>
```
change the elem `#target1`'s parent elem's background color to red.

## Target the children of an elem using jQuery

```
<script>
  $(document).ready(function() {
    $("#right-well").children().css("color", "orange");
  });
</script>
```
change the elem `#right-well`'s children's color to orange.

## Target a specific child of an elem using jQuery

```
<script>
  $(document).ready(function() {
    $(".target:nth-child(2)").addClass("animated bounce");
  });
</script>
```
The `target:nth-child(n)` CSS selector allows you to select all the nth elements with the target class or element type.

## Target even elems using jQuery

```
<script>
  $(document).ready(function() {
    $(".target:even").addClass("animated shake");
  });
</script>
```

## Use jQuery to modify the entire page

jQuery can target the `body` elem as well.

```
<script>
  $(document).ready(function() {
    $("body").addClass("animated hinge");
  });
</script>
```
make the whole page to rotate like a hinge.
