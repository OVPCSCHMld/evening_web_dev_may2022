# Week 2 Day1

- positioning
  - fixed
  - absolute
  - relative
- begin the project for this week

# Positioning

Positioning is a property in CSS. By default, the value is "static". The other options we'll talk about today are "relative", "fixed", and "absolute".

Positioning determines whether an element can be moved one the page to be somewhere else.

## Static

A static element stays in the place on the page that it lands in, as determined by margin and the order it is in the document.

To move it on the page we can use flex and margin, but that will affect other elements on the page. Other positioning allows us to move the element without necessarily affecting everything else on the page.

## Relative

Position relative does what it says on the tin. It allows us to move an element, RELATIVE to it's ORIGINAL POSITION.

To decide how/where to move it to, we use some new CSS properties:

- left
- right
- top
- and bottom

These properties will determine how much distance they are moved away from their original position, away from the edge you specify.

For example, if I write `top: 10px;` the element will move DOWN (away from the top edge) 10 pixels.

```css
.relative-box {
    background-color: brown;
    position: relative;
    top: -40px;
    left: 40px;
}
```

In the example above, the element takes a negative top value. That will move it up. `top: -40px;` is the same as `bottom: 40px;`.

When you move a relative element, it will not affect the positioning of the elements around it. It will sit on top of static elements.

# Exercise 1: Using position relative

Option 1:

Create a box on your page with a fixed height and width, and a background or a border. Move it 150px to the right and 200px down.

Option 2:

Make three boxes. Make the middle box move down 70 pixels.
Optionally, put them into a flex container so that they're all in one row.


# Position: Fixed

Position fixed allows you to move an element relative to the page. By default, your element will be where it was before; but the elements around it will ignore it.

```html
    <div class="box"></div>
    <div class="box fixed-box"></div>
    <div class="box"></div>
```

```css
.fixed-box {
    position: fixed;
    background-color: seagreen;
}
```

In the example above, our position fixed box will visually appear in the same place on the page as if it were `static` (i.e. where it would naturally load).

However, the boxes above and below it in the HTML, will act as if it doesn't exist. So, the fixed element will overlap with the box below it in the HTML.

You can use `top`,`left`, `bottom`, `right` to move the element a number of pixels away from the edge of the page.

```css
.fixed-box {
    position: fixed;
    background-color: seagreen;
    top: 0;
    left: 0;
}
```

The example above will move the element to the top left hand corner of the page (regardless of where it was before we applied the position fixed).

Because its position is always relative to the browser window itself, a fixed element will stay on the page, in the same place on the page, as you scroll.

This is how we get fixed "navbars" (menu at the top of the page).

A `fixed` element NEEDS to have a width set.

Normally, you only need a height and a background color/content/border. For fixed elements, you need that PLUS a width.

## VH/VW

Viewheight or viewport height, is a unit of measurement based on the size of the browser window. It works like a percentage:

`100vh` is the height of the page. `50vh` is half the height of the page.

Viewport width is the same, using the width of the page. `25vw would be a quarter wide of the page.

If you use these values then your elements will resize if the page resizes.

You can use them anywhere that you can use a pixel (`px`) value.

# Exercise 2: Using position fixed

**Option 1:**
Add several big boxes to your page, so that you have to scroll down the page.

Make one of your boxes fixed to the top right hand corner, so that when you scroll down, that box does not disappear.

**Option 2:**
Instead of pixel values, use the `vh` unit.

You will have three elements:
- the first is a fixed element that is 15vh tall, and has a background colour. When you scroll the page, it will stay at the top of the page, like a navigation bar.
- the next two elements are static elements. They have a height of 85vh, and they have different colours each.

Use margin to that the first static element is not overlapped by the fixed/navbar element.

# Position: Absolute

- Position relative moves an item relative to its original position in the page (bottom is bottom of the element)
- Position fixed moves it relative to the window/page itself (bottom is the bottom of the page)

Position absolute moves an element relative to a containing/parent element that has a position of relative (or fixed or also absolute).

A good example, is having a "Sale!" sticker on the corner of a box or listing on a e-commerce website.

```html
<div class="relative-container">
  <div class="absolute-item">
    Sale!
  </div>
</div>
```

To make this item sit somewhere specific in our container, we need to have some basic CSS:

```css
.relative-container {
  /* the container needs this for the absolute item to work */
  position: relative; 
  /* general styles */
  border: solid black 3px;
  height: 500px;
  width: 250px;
}

.absolute-item {
  position: absolute;
  border: solid red 3px;
  padding: 10px;
}
```

The same as `position: fixed;` elements; by default it does not have a width unless you apply one, or put content inside.

(Let me know if you want an optional exercise on this.)


