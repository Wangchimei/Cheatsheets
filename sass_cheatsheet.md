# Sass Cheat Sheet

## Syntax

```scss
section {
  h1 {
    ...
  }

  #features {
    ...
  }

  .feature-links {
    ...
  }
}
```

### Direct descendant (>)

Only classes that are immediate children of the container div will get the style

```scss
.container{
  > .left-area{
   ...
 }
}
```

### Parent selector ( & )

If we wanted to modify a class by adding a class to it, we could make use of the parent selector, it is mostly used in situations where adding a secondary style changes the style of the element. Which would also play the role of modifiers.

```scss
.container {
  &.target {
    background-color : #000;
     }
  &:hover {
    ...
  }
  &::before {
    ...
  }
}
```

🔑 background color applies to the `.container` class with a `.target` class.

use the parent selector to scope roles to another class

```scss
button {
  color: #131313;
  .theme-dark & {
    color: #fff;
  }
}
```

🔑 color #fff only applies to the `.theme-dark` class because of the parent selector.

## Variables

```scss
$color-dark: #131313;

.color {
  $text-color: #fafafa;
  background-color: $color-dark;
  color: $text_color;
  text-shadow: 0 0 2px darken($text_color, 40%);
}
```

🔑 `$color-dark` is a global variables, whereas `$text_color` can only be accessed within the block of code.

## Mixins

### Declaration

- name only

  ```scss
  @mixin <name> {
    ...
  }

  //import
  .nav {
    @include <name>
  }
  ```

- name with params

  ```scss
  @mixin <name>($color) {
    background-color: $color;
    color: #000;
  }

  //import
  .background {
    @include <name>(white);
  }
  ```

- name with params and a default value

  ```scss
  @mixin <name>($color: #fff) {
    background-color: $color;
    color: #000;
  }

  //import
  .background {
    @include <name>($color: lightgreen);
  }
  ```

  A default value can also be `null`.

  ```scss
  @mixin <name>($color: null) {
    background-color: $color;
    color: #000;
  }

  //import
  .title {
    @include <name>();
  }
  .background {
    @include <name>(#fff);
  }
  ```

### Content Block

This allows you to pass in a deceleration block.

```scss
@mixin <name>($color) {
  color: $color;
  .extra {
    @content;
  }
}

//import
.title {
  @include text-color(#fff) {
    color: blue;
  }
}
```

## Functions

Functions allow you to define complex operations that are re-usable throughout your style sheet, which returns a single value.

### Common inbuilt Sass functions:

- `lighten($color, $amount)` : Makes a color lighter
- `darken($color, $amount)` : Makes a color darker
- `adjust-hue($color, $degrees)` : Changes the hue of a color
- `mix($color1, $color2, $weight)` : Mixes colors + weight of first/ also below return values of a color to use for conditionals
- `hue($color)` : Gets the hue component of a color
- `saturation($color)` : Gets the saturation component of a color
- `lightness($color)`: Gets the lightness component of a color

[For More](https://sass-lang.com/documentation/at-rules/function)

### Create your own function

## Flow Control Rules

- `@if` / `@else` / `@else if` controls whether or not a block is evaluated.

  ```
  @if <expression> { ... }
  ```

  ```scss
  @mixin triangle($size, $color, $direction) {
    height: 0;
    width: 0;

    border-color: transparent;
    border-style: solid;
    border-width: $size / 2;

    @if $direction == up {
      border-bottom-color: $color;
    } @else if $direction == right {
      border-left-color: $color;
    } @else if $direction == down {
      border-top-color: $color;
    } @else if $direction == left {
      border-right-color: $color;
    } @else {
      @error "Unknown direction #{$direction}.";
    }
  }

  .next {
    @include triangle(5px, black, right);
  }
  ```

- `@each` evaluates a block for each element in a list or each pair in a map.

  ```
  @each <variable> in <expression> { ... }

  @each <variable>, <variable> in <expression> { ... }
  ```

  ```scss
  // Example 1
  $sizes: 40px, 50px, 80px;

  @each $size in $sizes {
    .icon-#{$size} {
      font-size: $size;
      height: $size;
      width: $size;
    }
  }

  // Example 2 - with maps
  $icons: (
    'eye': '\f112',
    'start': '\f12e',
    'stop': '\f12f',
  );
  @each $name, $glyph in $icons {
    .icon-#{$name}:before {
      display: inline-block;
      font-family: 'Icon Font';
      content: $glyph;
    }
  }
  ```

- `@for` evaluates a block a certain number of times.

  ```
  @for <variable> from <expression> to <expression> { ... }

  @for <variable> from <expression> through <expression> { ... }
  ```

  If `to` is used, the final number is excluded.  
  If`through` is used, it's included.

  ```scss
  @for $i from 1 through 3 {
    ul:nth-child(3n + #{$i}) {
      background-color: lighten($base-color, $i * 5%);
    }
  }
  ```

- [`@while`](https://sass-lang.com/documentation/at-rules/control/while) evaluates a block until a certain condition is met.
