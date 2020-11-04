---
title: "SCSS Animation Mixin"
description: "How to create an Scss/Sass animation mixin. We do this to follow DRY software development principle, and make our code more easily readable."
date: 2020-05-05T17:15:02-07:00
draft: false
tags: ['css', 'scss']
categories: ['programming']
references: ['https://stackoverflow.com/a/40186624/7974948']
---

## Problem

The slightest change in CSS animations (`@keyframes`) requires a creation of a new animation.

#### Problem Example
```SCSS
@keyframes to-yellow {
  50% { background-color: yellow; }
}

@keyframes to-skyblue {
  50% { background-color: skyblue; }
}
```

Both of the animations pretty much do the same thing, but we had to create two of them.
We had to create two of them because their property (`background-color`) had different values (i.e. `yellow` and `skyblue`). 

This doesn't follow the [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) software development principle.

To fix this, we're going to use an SCSS [mixin](https://sass-lang.com/documentation/at-rules/mixin).

## Solution
Looking at the problem example above, we'd replace it with something like this:
```SCSS
@mixin animation-mixin($name, $color-var) {
  @keyframes #{$name} {
    50% { background-color: $color-var; }
  }
}

@include animation-mixin(to-yellow, yellow);

@include animation-mixin(to-skyblue, skyblue);
```

Then you could call the `to-yellow` and `to-skyblue` animations in your selectors as needed:
```SCSS
div {
  height: 100px;
  width: 100px;
  background-color: whitesmoke;
  animation: to-yellow 4s ease infinite;
}
```

Live example:
<!-- CodePen -->
{{< rawhtml >}}
  <p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="css,result" data-user="Hakeemmidan" data-slug-hash="OJPaezR" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="SCSS Animation Mixin">
    <span>See the Pen <a href="https://codepen.io/Hakeemmidan/pen/OJPaezR">
    SCSS Animation Mixin</a> by Abdulhakeem Almidan (<a href="https://codepen.io/Hakeemmidan">@Hakeemmidan</a>)
    on <a href="https://codepen.io">CodePen</a>.</span>
  </p>
  <script async src="https://static.codepen.io/assets/embed/ei.js"></script>
{{</ rawhtml >}}