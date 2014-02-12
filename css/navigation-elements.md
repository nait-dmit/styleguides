CSS StyleGuide - Styling Navigation Elements
============================================

When creating a horizontal navigation system, and given the following html markup:

```html
<nav class="primary-nav">
  <ul>
    <li><a href="...">Home<a/></li>
    <li><a href="...">About<a/></li>
    <li><a href="...">Blog<a/></li>
    <li><a href="...">Contact<a/></li>
  </ul>
</nav>
```

Consider the following:

## Inline-block Method

* uses `inline-block` to position button-like anchor tags horizontally
* better for equally distributed links (equal space between)
* subject to normal character spaces between elements (see: http://joshnh.com/2012/02/07/why-you-should-use-inline-block-when-positioning-elements/)

```css
nav.primary-nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav.primary-nav li {
  display: inline; /* removes element from the 'document flow', since these are for semantics and not for style */
}

nav.primary-nav a {
  display: inline-block;
  padding: 6px 12px; /* the numbers here are not important, just the concept of providing extra clickable space */
  background: #ccc;
}
```

### The result

![Inline-block Nav Example](https://raw.github.com/nait-dmit/styleguides/master/assets/images/inline-block-nav-example-01.png)



## Floated Method

* uses `float` and `width` to position block elements horizontally.
* better for equally sized links
* subject to clearfix problem

```css
nav.primary-nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav.primary-nav li {
  display: inline;
}

nav.primary-nav a {
  display: block;
  float: left;
  padding: 6px 12px; /* the numbers here are not important, just the concept of providing extra clickable space */
  width: 200px; /* creating equally-sized links */
}
```

### The result

![Floated Nav Example](https://raw.github.com/nait-dmit/styleguides/master/assets/images/floated-nav-example-01.png)

