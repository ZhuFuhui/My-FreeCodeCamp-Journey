# Front end library - Bootstrap {ignore=true}

## Content {ignore=true}
<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

* [Taste the Bootstrap button color rainbow](#taste-the-bootstrap-button-color-rainbow)
* [Call out optional actions with btn-info](#call-out-optional-actions-with-btn-info)
* [Warn your users of a danderous action with btn-danger](#warn-your-users-of-a-danderous-action-with-btn-danger)
* [Use the Bootstrap grid to put elements side by side](#use-the-bootstrap-grid-to-put-elements-side-by-side)
* [Ditch custom CSS for Bootstrap](#ditch-custom-css-for-bootstrap)
* [Use a span to target inline elements](#use-a-span-to-target-inline-elements)
* [Create a custom heading](#create-a-custom-heading)
* [Add Font Awesome icons to our buttons](#add-font-awesome-icons-to-our-buttons)
* [Add Font Awesome icons to all of our buttons](#add-font-awesome-icons-to-all-of-our-buttons)
* [Responsively style radio buttons](#responsively-style-radio-buttons)
* [Responsively style checkboxes](#responsively-style-checkboxes)
* [Style text inputs as form controls](#style-text-inputs-as-form-controls)
* [Line up form elements responsively with Bootstrap](#line-up-form-elements-responsively-with-bootstrap)
* [Create a Bootstrap headline](#create-a-bootstrap-headline)
* [House our page within a Bootstrap container-fluid div](#house-our-page-within-a-bootstrap-container-fluid-div)
* [Create a Bootstrap row](#create-a-bootstrap-row)
* [Split your Bootstrap row](#split-your-bootstrap-row)
* [Create Bootstrap wells](#create-bootstrap-wells)
* [Add elements within your Bootstrap wells](#add-elements-within-your-bootstrap-wells)
* [Apply the default Bootstrap button style](#apply-the-default-bootstrap-button-style)
* [Create a class to target with jQuery selectors](#create-a-class-to-target-with-jquery-selectors)
* [Add id attributes to Bootstrap elements](#add-id-attributes-to-bootstrap-elements)
* [Label Bootstrap wells](#label-bootstrap-wells)
* [Give each element a unique id](#give-each-element-a-unique-id)
* [Label Bootstrap Buttons](#label-bootstrap-buttons)
* [Use comments to clarify code](#use-comments-to-clarify-code)

<!-- /code_chunk_output -->


## Taste the Bootstrap button color rainbow

The `btn-primary` class is the main color used for highligthing button. `btn` and `btn-block` are still needed classes.<br/>

`<button class="btn btn-block btn-primary">Like</button>` creates a button with deep blue background color and white context in it.

## Call out optional actions with btn-info

The `btn-info` class is used to call attention to optional actions that the user can take. `btn` and `btn-block` are still needed classes.<br/>

`<button class="btn btn-block btn-info">Info</button>` creates a button with sky blue background color and white context in it.

## Warn your users of a danderous action with btn-danger

The `btn-danger` class is the button color you'll use to notify users that the button performs a destructive action, such as deleting. `btn` and `btn-block` are still needed classes.<br/>

`<button class="btn btn-block btn-danger">Delete</button>` creates a button with red background color and white context in it.

## Use the Bootstrap grid to put elements side by side

Bootstrap uses a responsive 12-column grid sys. Most of Bootstrap's classes can be applied to a `div` element.<br/>

The col width depends on the user's screen width. In `col-xs-*` and `col-md-*`, `xs` means extra small suitble for a phone screen, `md` means medium, and `*` means the num of cols the element use.<br/>

`<div class="col-xs-4"><button class="btn btn-block btn-info>Info</button></div>` creates a button which occupies 4 cols.

## Ditch custom CSS for Bootstrap

Use Bootstrap's built-in styles, such as `text-primary` and `img-responsive` classes which can be applied to `h2`-like elements and `img` element, respectively.<br/>

Class `text-primary` results in a deep blue color to the text.

Class `img-responsive` makes the image to change its size automatically according to the viewport.

## Use a span to target inline elements

`<p>Things cats <span class="text-danger">love</span>:</p>`

Here, the `span` element with a class of `text-danger` enables a red text color of the word 'love'.

## Create a custom heading

```
<div class="row">
    <div class="col-xs-8">
        <h2>title</h2>
    </div>
    <div class="col-xs-8">
        <img src="..." alt="">
    </div>
</div>
```
To use `col-xs-*`, here the `h2` and `img` element occupy the total 12-cols, causing them to lay horizontally.

## Add Font Awesome icons to our buttons

Font Awesome is a convenient library of icons (in `.svg` format). To import:
```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css" integrity="sha384-XdYbMnZ/QjLh6iI4ogqCTaIjrFk87ip+ekIjefZch0Y+PvJ8CDYtEs1ipDmPorQ+" crossorigin="anonymous">
```

By importing this CSS, the `i` element is now for icons. The `span` elem. is also acceptable for use with icons.

`<button class="btn btn-block btn-primary"><i class="fa fa-thumbs-up"></i>Like</button>` creates a button, a thumbs-up icon is shown next to "Like", note that class `fa` in `i` is requirred.

## Add Font Awesome icons to all of our buttons

`fa-info-circle` is related to the info-circle icons;

`fa-trash` is ralted to the trash icons.

## Responsively style radio buttons

Bootstrap's `col-xs-*` classed can also be used on `form` elements.

```
<form>
  <div class="row">
    <div class="col-xs-6">
      <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    </div>
    <div class="col-xs-6">
      <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    </div>
  </div>
</form>
```
Above snippet makes 2 radio buttons lay horizontally, and each occupies same wide of the viewport.

## Responsively style checkboxes

Do the same thing to checkboxes as to radio buttons as in previous lesson.

## Style text inputs as form controls

You can add the `fa-paper-plane` Font Awesome icon by adding `<i class="fa fa-paper-plane"><i>` within in your submit `button` elem.

The `fa-paper-plane` is related to the sending icon in the shape of a paper plane.

`<input type="text" class="form-control">` gives this text input a good looking.

## Line up form elements responsively with Bootstrap

Lay text input and submit button horizontally also using classes `col-xs-*`.

## Create a Bootstrap headline

`<h3 class="text-primary text-center">jQuery Playground</h3>` creates and colors (`text-primary`) and centers (`text-center`) the text.

## House our page within a Bootstrap container-fluid div

Nest your `h3` elem. within a `div` elem. with the class `container-fluid` to make it mobile-responsive.

## Create a Bootstrap row

```
<div class="row">
</div>
```

## Split your Bootstrap row

Create 2 `div` elements within your row, both with the class `col-xs-6`.

```
  <div class="row">
    <div class="col-xs-6">
    </div>
    <div class="col-xs-6">
    </div>
  </div>
```

## Create Bootstrap wells

Bootstrap has a class called `well` that can create a visual sense of depth for ur cols.

Nest 1 `div` element with the class `well` within each of ur `col-xs-6 div` elems. 

```
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
      </div>
    </div>
  </div>
```
With snippet above, u will see 2 empty block waitting to be filled with other elems., such as buttons.

## Add elements within your Bootstrap wells

Now we're several `div` elems. deep on each col of our row. This is as deep as we'll need to go. Now we can add our `button` elems.

Nest 3 `button` elems. within each of ur `well div` elems.

```
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button></button>
        <button></button>
        <button></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button></button>
        <button></button>
        <button></button>
      </div>
    </div>
  </div>
```

## Apply the default Bootstrap button style

Bootstrap has another button class called `btn-default`.

Apply both the `btn` and `btn-default` classes to each of ur `button` elems.

```
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
      </div>
    </div>
  </div>
```

## Create a class to target with jQuery selectors

Not every class needs to have corresponding CSS. Sometimes we create classes just for the purpose of selecting these elems more easily using jQuery.

Give each of ur `button` elems. the class `target`.

```
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
  </div>
```

## Add id attributes to Bootstrap elements

Recall that in addition to class attributes, you can give each of ur elems. and `id` attribute.

Each id must be unique to a specific elem and used only once per page.

Let's give a unique id to each of our `div` elems. of class `well`.

Give the well on the left the id of `left-well`. Give the well on the right the id of `right-well`.

```
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well" id="left-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well" id="right-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
  </div>
</div>
```

## Label Bootstrap wells

For the sake of clarity, let's label both of our wells with their ids.

Above ur left-well. inside its `col-xs-6 div` elem, add a `h4` elem. with the text `#left-well`.

Do the similar thing to the right-well.

```
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
  </div>
</div>
```

## Give each element a unique id

We will also want to be able to use jQuery to target each button by its unique id.

Give each of ur btns a unique id, starting with `target1` and ending with `target6`.

```
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target" id="target1"></button>
        <button class="btn btn-default target" id="target2"></button>
        <button class="btn btn-default target" id="target3"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target" id="target4"></button>
        <button class="btn btn-default target" id="target5"></button>
        <button class="btn btn-default target" id="target6"></button>
      </div>
    </div>
  </div>
</div>
```

## Label Bootstrap Buttons

Just like we labeled our wells, we want to label our buttons.

Give each of ur `button` elems. text that corresponding to its `id`'s selector.

```
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

## Use comments to clarify code

When we start using jQuery, we will modify HTML elems. without needing to actually change them in HTML.

Let's make sure that everyone knows they shouldn't actually modify and of this code directly.

Remember that u can start a comment with `<!--` and end a comment with `-->`.

Add commment at the top of ur HTML that says `Only change code above this line`.