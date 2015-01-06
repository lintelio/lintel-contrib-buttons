lintel-contrib-buttons
======================

> Buttons for lintel.

[![npm](https://img.shields.io/npm/v/lintel-contrib-buttons.svg)](https://www.npmjs.com/package/lintel-contrib-buttons)
[![Bower](https://img.shields.io/bower/v/lintel-contrib-buttons.svg)](https://github.com/lintelio/lintel-contrib-buttons)


## Getting Started
This module requires Lintel.

If you haven't used [Lintel](http://lintel.io/) before, be sure to check out the [Getting Started](http://lintel.io/getting-started) guide, as it explains how to install and use this module. Once you're familiar with that process, you may install this module with this command:

```shell
bower install lintel-contrib-buttons --save
```

Once the module has been installed, you will have to load it in your main SASS file:

```scss
@import "bower_components/lintel-contrib-buttons/sass/buttons.scss"
```

You can use [wiredep](https://github.com/taptapship/wiredep) or [grunt-wiredep](https://github.com/stephenplusplus/grunt-wiredep) to automatically inject files in your build process.


## Variables
Check the vars file in the `sass` folder to see the full list of variables you can customize.

#### $btn-include-inverse
Type: `Boolean`  
Default value: `true`  

Include styles for inverse buttons (light background)?

#### $btn-include-block-all
Type: `Boolean`  
Default value: `true`  

Include `.btn-block-*-max` where `*` is the prefix for each breakpoint max-resolution? (ex. `.btn-block-sm-max`)

#### $btn-include-block-all
Type: `Boolean`  
Default value: `true`  

Include `.btn-block-sm-max`? Assumed true if `$btn-include-block-all` is true.


## Mixins
Check the mixins file in the `sass` folder to see how you can extend this module.

#### make-btn($bg[, $border, $text, $bg-inverse, $border-inverse, $text-inverse])
Default $border: `darken($bg, 10%)`  
Default $text: `#fff`  
Default $bg-inverse: `$bg`  
Default $border-inverse: `$border`  
Default $text-inverse: `$text`  

Provide at least:  
`$bg`

If using inverse styles, also include:  
`$bg-inverse`  
`$border-inverse`  
`$text-inverse`  

```scss
.btn-primary {
  @include make-btn(
    $bg: $btn-primary,
    $bg-inverse: $btn-primary-bg,
    $border-inverse: $btn-primary-border,
    $text-inverse: $btn-primary-text
  );
}
```

#### make-btn-block($screen-size, $class)

Create a btn-block-*-max class for a new max-resolution.

```scss
@include make-btn-block($screen-sm-max, "sm");
```


## Example Buttons

#### Default
```html
<button class="btn" type="button">Hello World</button>
```

#### Link
Be sure to include `role="button"` for accessibility if the button does not link to a page.
```html
<a href="#" class="btn" role="button">Hello World</a>
```

#### Primary
```html
<button class="btn btn-primary" type="button">Hello World</button>
```

#### Inverse Primary
```html
<button class="btn btn-primary inverse" type="button">Hello World</button>
```

#### Disabled Button
```html
<button class="btn btn-primary" type="button" disabled>Hello World</button>
```

#### Active Button
```html
<button class="btn btn-primary active" type="button">Hello World</button>
```

#### Always Block
```html
<button class="btn btn-block" type="button">Hello World</button>
```

#### Block on $screen-sm-max and below
```html
<button class="btn btn-block-sm-max" type="button">Hello World</button>
```

#### Smaller Button
```html
<button class="btn btn-sm" type="button">Hello World</button>
```


## Example Button Groups

#### Button Group
```html
<div class="btn-group">
  <button class="btn" type="button">1</button>
  <button class="btn" type="button">2</button>
  <button class="btn" type="button">3</button>
</div>
```

#### With Hidden Buttons
Use the `.first` and `.last` classes to fix the border-radius where appropriate. 

- `.first` - first visually visible button that's not `:first-child`
- `.last`  - last visually visible button that's not `:last-child`.

```html
<div class="btn-group">
  <button class="btn" type="button" style="display: none;">1</button>
  <button class="btn first last" type="button">2</button>
  <button class="btn" type="button" style="display: none;">3</button>
</div>
```


## Example Dropdowns

#### Single Dropdown
```html
<div class="btn-group">
  <button class="btn btn-dropdown-toggle" type="button">
    Dropdown
    <span class="btn-caret" aria-hidden="true"></span>
  </button>
</div>
```

#### Open Dropdown
```html
<div class="btn-group open">
  ...
</div>
```

#### Split Dropdown
```html
<div class="btn-group">
  <button class="btn" type="button">Split Dropdown</button>
  <button class="btn btn-dropdown-toggle" type="button" aria-label="More Options"><span class="btn-caret" aria-hidden="true"></span></button>
</div>
```

#### Nested Button Groups
```html
<div class="btn-group">
  <div class="btn-group">
    <button class="btn" type="button">Split Dropdown</button>
    <button class="btn btn-dropdown-toggle" type="button" aria-label="More Options"><span class="btn-caret" aria-hidden="true"></span></button>
  </div>
  <button class="btn" type="button">Button</button>
  <button class="btn" type="button">Button</button>
</div>
```


## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).


## License
Copyright (c) 2014 Marius Craciunoiu. Licensed under the MIT license.
