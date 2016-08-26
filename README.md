# css-positioning-intro

- CSS divides HTML into two types: inline and block.
- After block elements, browsers render a new line.
- Inline elements: img, a, br, em, strong
- Block elements: p, h1, ul, li, almost everything else

### Box-Sizing:

- width + padding + border = actual visible/rendered width of an element's box
- height + padding + border = actual visible/rendered height of an element's box

```
*,
*:after,
*:before
  box-sizing: border-box
```
### Display Property

- The default value for all elements is inline. Most "User Agent stylesheets" (the default styles the browser applies to all sites) reset many elements to "block".
- **Inline:** ```<span>```, ```<em>``` Text wraps around me! I accept margin and padding, but only push things horizontally, not vertically. I am going to politely ignore your height and width instructions.
- **Inline-Block:** An element set to ```inline-block``` is very similar to inline in that it will set inline with the natural flow of text (on the "baseline"). The difference is that you are able to set a ```width``` and ```height``` which will be respected.
- **Block:**  A number of elements are set to block by UA stylesheets, usually container elements. ```<div>```, ```<ul>```, ```<section>```, and a bunch more. Also, text blocks like: ```<p>```, ```<h1>```. I do not sit inline! I will take up as much horizontal space as possible!

```
div {
  display: inline;        /* Default of all elements, unless UA stylesheet overrides */
  display: inline-block;  /* Characteristics of block, but sits on a line */
  display: block;         /* UA stylesheet makes things like <div> and <section> block */
  display: none;          /* Hide */
}
```

### Positioning Property

- ```relative```: A relatively or stickily positioned element preserves its space. The adjacent elements aren’t repositioned to occupy the reserved space for this element. However, the offsets of this element don’t occupy space. They’re completely ignored from the other elements, and hence that may causes elements to overlap each other.
- ```absolute```: An absolutely positioned element is completely removed from the normal flow. The adjacent sibling elements occupy its space.
- ```fixed```: A fixed positioned element (subcategory of the absolute positioning) is positioned relative to the viewport
- ```sticky```: A stickily positioned element is positioned relative to the nearest ancestor with a scrolling box (e.g. overflow:auto). If there isn’t such an ancestor, it is positioned relative to the viewport.
- You specify the position of your element via offset properties: ```auto``` (default), ```top```, ```bottom```, ```right```, ```left```
- An element whose position property is set to absolute or fixed is called an absolutely positioned element. 
- A positioned element can take advantage of the ```z-index``` property to specify its stack order. ```z-index``` only effects elements that have a position value other than static (the default). Without any z-index value, elements stack in the order that they appear in the DOM (the lowest one down at the same hierarchy level appears on top). Elements with non-static positioning will always appear on top of elements with default static positioning. Also note that nesting plays a big role. If an element B sits on top of element A, a child element of element A can never be higher than element B.
