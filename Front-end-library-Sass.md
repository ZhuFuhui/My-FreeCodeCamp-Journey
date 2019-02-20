# Front end library: Sass {ignore=true}

## Content {ignore=true}


<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

* [Store data with Sass variables](#store-data-with-sass-variables)
* [Nest CSS with Sass](#nest-css-with-sass)
* [Create reuseable CSS with mixins](#create-reuseable-css-with-mixins)
* [Use @if and @else to add logic to ur style](#use-if-and-else-to-add-logic-to-ur-style)
* [Use @for to create a Sass loop](#use-for-to-create-a-sass-loop)
* [Use @each to map over items in a list](#use-each-to-map-over-items-in-a-list)
* [Apply a style until a condition is met with @while](#apply-a-style-until-a-condition-is-met-with-while)
* [Split ur styles into smaller chunks with partials](#split-ur-styles-into-smaller-chunks-with-partials)
* [Extend one set of CSS styles to another elem](#extend-one-set-of-css-styles-to-another-elem)

<!-- /code_chunk_output -->


## Store data with Sass variables

Sass use variables, which start with a `$` and followed by its name.

For example, `$main-fonts: Arial, sans-serif`, this enables the reuse of values.

## Nest CSS with Sass

## Create reuseable CSS with mixins

In Sass, a `mixin` is a group of CSS declarations that can be reused throughout the style sheet.

Consider "box-shadow",

```
@mixin box-shadow($x, $y, $blur, $c) {
    -webkit-box-shadow: $x, $y, $blur, $c;
    -moz-box-shadow: $x, $y, $blur, $c;
    -ms-box-shadow: $x, $y, $blur, $c;
    box-shadow: $x, $y, $blur, $c;
}
```

**Note**: `-webkit-`, `-moz-` and `-ms-` are [vendor prefix](https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix).

Now any time a `box-shadow` rule is needed, only a single line calling the `mixin` replaces having to type all the vendor prefixs. A `mixin` is called with the `@include` directive:

```
div {
    @include box-shadow(0px, 0px, 4px, #fff);
}
```

## Use @if and @else to add logic to ur style

The0 `@if` directive in Sass is useful to test for a specific case - it works just like the `if` statement in JavaScript.

```
@mixin text-effect($val) {
  @if $val == danger {
    color: red;
  }
  @else if $val == alert {
    color: yellow;
  }
  @else if $val == success {
    color: green;
  }
  @else {
    color: black;
  }
}
```

## Use @for to create a Sass loop

The `@for` directive adds styles in a loop, very similar to a `for` loop in JS.

`@for` is used in two ways: "start through end" or "start to end". The main difference is that "start to end" excludes the end number, and "start through end" includes the end number.

```
<style type='text/sass'>
  @for $j from 1 to 6 {
    .text-#{$j} {font-size: 10px * $j}
  }  
</style>
```
It should create 5 classes called `.text-1` to `.text-5` where each has a `font-size` set to 10px multiplied by the index.

## Use @each to map over items in a list

Sass also offers the `@each` directive which loops over each item in a list or map.

On each iteration, the variable gets assigned to the current value from the list or map.

```
@each $color in blue, red, green {
  .#{$color}-text {color: $color;}
}
```

A map has slightly different syntax. Here's an example:

```
$colors: (color1: blue, color2: red, color3: green);

@each $key, $color in $colors {
  .#{$color}-text {color: $color;}
}
```

Note that the `$key` variable is needed to reference the keys in the map. Otherwise, the compiled CSS would have `color1`, `color2`... in it.

## Apply a style until a condition is met with @while

The `@while` directive is an option with similar functionality to the JS `while` loop. It creates CSS rules until a condition is met.

The `@for` challenge gave an example to create a simple grid sys. This can also work with `@while`.

```
$x: 1;
@while $x < 13 {
  .col-#{$x} { width: 100%/12 * $x;}
  $x: $x + 1;
}
```

First, define a variable `$x` and set it to 1. Next, use the `@while` directive to create the grid system while `$x` is less than 13.

After setting the CSS rule for `width`, `$x` is incremented by 1 to avoid an infinite loop.

## Split ur styles into smaller chunks with partials

`Partials` in Sass are separeate files that hold segments of CSS code. These are imported and used in other Sass files. This is a great way to group similar code into a module to keep it organized.

Names for `partials` start with the underscore (`_`) char, which tells Sass it is a small seg of CSS and not to convert it into a CSS file. Also, Sass files end with the `.scss` file extension. To bring the code in the `partial` into another Sass file, use the `@import` directive.

For example, if all ur `mixin`s are saved in a `partial` named "_mixins.scss", and they are needed in the "main.scss" file, this is how to use them in the main file:

```
// in the main.scss file
@import "mixins"
```

Note that the underscore is not needed in the `import` statement-Sass understands it is a `partial`. Once a `partial` is imported into a file, all variables, `mixins`, and other code are available to use.
`.scss` is also not needed.

## Extend one set of CSS styles to another elem

Sass has a feature called `extend` that makes it easy to borrow the CSS rules from one elem and build upon them in another.

For example, the below block of CSS rules style a `.panel` class. It has a `background-color`, `height` and `border`.

```
.panel {
    background-color: red;
    height: 70px;
    border: 2px solid green;
}
```

Now u want another panel called `.big-panel`. It has the same base prop as `.panel`, but also needs a `width` and `font-size`.

It's possible to copy and paste the initial CSS from `.panel`, but the code becomes reprtitive as u add more styles of panels.

The `extend` directive is a simple way to reuse the rules written for one elem, then add more for another:

```
.big-panel {
    @extend .panel;
    width: 150px;
    font-size: 2em;
}
```

The `.big-panel` will have the same prop as `.panel` in addition to the new styles.