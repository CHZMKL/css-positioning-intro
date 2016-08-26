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
- Inline: ```<span>```, ```<em>``` Text wraps around me! I accept margin and padding, but only push things horizontally, not vertically. I am going to politely ignore your height and width instructions.
- Inline-Block: An element set to ```inline-block``` is very similar to inline in that it will set inline with the natural flow of text (on the "baseline"). The difference is that you are able to set a ```width``` and ```height``` which will be respected.
- Block:  A number of elements are set to block by UA stylesheets, usually container elements. ```<div>```, ```<ul>```, ```<section>```, and a bunch more. Also, text blocks like: ```<p>```, ```<h1>```. I do not sit inline! I will take up as much horizontal space as possible!

```
div {
  display: inline;        /* Default of all elements, unless UA stylesheet overrides */
  display: inline-block;  /* Characteristics of block, but sits on a line */
  display: block;         /* UA stylesheet makes things like <div> and <section> block */
  display: none;          /* Hide */
}
```
