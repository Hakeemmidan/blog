---
title: "How to Prevent CSS Hover State From Getting stuck on Mobile Browsers"
description: "How to make the CSS hover state not get stuck on mobile browsers using CSS or SCSS mixins"
date: 2020-04-16T21:58:27-07:00
draft: false
tags: ['css', 'scss']
categories: ['programming']
references: ['https://stackoverflow.com/a/28058919/7974948']
---

## Problem

The CSS hover state often gets stuck on mobile (touch screen) browsers. It would be something like this:

{{< figure
src="example-sticky-hover.gif"
link="example-sticky-hover.gif"
alt="GIF of clicking on link and css hover state getting stuck"
attr="Hover state getting stuck on-click on mobile"
class="center"
>}}

## How to Fix It

Using the ['hover' CSS media query](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/hover), which could be applied either through SCSS or CSS. In the case of SCSS, we're going to use a [mixin](https://sass-lang.com/documentation/at-rules/mixin).

Here is each solution respectively:

### Solution 1: SCSS Mixin

The mixin:
```SCSS
@mixin hover-supported {    
    @media (hover: hover) { 
      @content;
    }
}
```


Example use:
```SCSS
  .example {
    @include hover-supported() {
      &:hover {
        background-color: black;
      }
    }
  }
```

### Solution 2: CSS

Example use:
```CSS
  @media (hover: hover) {
    .example:hover {
      background-color: black;
    }
  }
```

### Explanation

Both examples change the `background-color` of HTML elements with class `example` only when they're hovered-over on non-touch screen devices (or any [hover](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/hover) supported device). In other words, *this applies hover styling on only non-touch screen devices*.

PS: I'm not sure how this would act on touch-screen laptops.