CSS StyleGuide
==============

Welcome to the NAIT DMIT CSS Styleguide.

*This is a very early first draft, and it is based largely on the internal styleguide used at Github https://github.com/styleguide/css*


## Coding Style

* Use soft-tabs with a two or four space indent.
* Put spaces after `:` in property declarations.
* Put spaces before `{` in rule declarations.
* Use hex color codes `#000` unless using rgba.
* Use **hyphens** to separate words in class and id names, not underscores, camelCase, or other methods
* Zero values should not be given units when possible

Here is good example syntax:
```css
/* This is a good example! */
.styleguide-format {
  border: 1px solid #0f0;
  color: #000;
  background: rgba(0,0,0,0.5);
}
```


## CSS File Naming

Websites with single style sheets should have that stylesheet named `style.css`, and should be found in a directory named `stylesheets`


## Pixels vs. Ems

Use percentage value to set font size initially at the document level, use the `html {...}` tag selector. Font sizes for individual elements should then be set using em units, calculated by the browser as a multiplier of the parent element font size.

Set the line-height at the document level by using a unitless value, use the `html {...}` tag selector. This acts as a multiplier of the computed font size. Line heights for individual text elements can be set either with a unitless value (better for inheritance), or with `em` values (better for rounding accuracy).

Other values, such as elements widths, margins, padding, etc can use `em` or `px` values.

Here is an example:

```css
html {
  font-size: 100%; /* Yields a 16px font size in most browsers */
  line-height: 1.5; /* Yields a 24px line height, based on font size */
}

.container {
  width: 960px;
  margin: 0 auto;
}

h1 {
  font-size: 3em; /* Yields a 48px font size, based on setting above */
  margin: 20px 0;
}
```

## Class naming conventions

Never reference `js-` prefixed class names from CSS files. `js-` are used exclusively from JS files.

Use the `is-` prefix for state rules that are shared between CSS and JS.

## Specificity (classes vs. ids)

Heavily favour using classes over ids. Elements that occur exactly once inside a page can use ids, otherwise, use classes. When in doubt, use a class name.

* Good candidates for ids: modal popups, forms.
* Bad candidates for ids: navigation, item listings, grid structures.

When styling a component, start with an `element.class` namespace (prefer class names over ids), prefer descendant selectors by default, and use as little specificity as possible.

Here is a good example, given the following HTML:


```html
<ul class="category-list">
  <li class="item">Category 1</li>
  <li class="item">Category 2</li>
  <li class="item">Category 3</li>
</ul>
```

We could style it as such:

```css
/* element + class namespace */
ul.category-list {
  margin: 20px 0 20px 20px;
}

/* descendant selector for list items, no need to use the .item class selector in this case */
ul.category-list li {
  list-style-type: disc;
}

/* minimal specificity for all links */
ul.category-list a {
    color: #ff0000;
}
```

### CSS Specificity Guidelines

* If you must use an id selector (`#selector`) make sure that you have no more than one in your rule declaration. A rule like `#header .search #quicksearch { ... }` is considered harmful.
* When modifying an existing element for a specific use, try to use specific class names. Instead of `.listings-layout.bigger` use rules like `.listings-layout.listings-bigger`.
