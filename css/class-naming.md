CSS StyleGuide - Class Naming
=============================

## Semantic Naming

CSS class naming is a tricky subject. The general rule-of-thumb to follow is that you should aim to **name your objects so that the name *describes* the content enclosed within**; not so that it *specifies* that content, especially in terms of visual style.

**Poor naming:**
```css
button.red {
  background-color: #f00;
}

button.green {
  background-color: #0f0;
}

button.blue {
  background-color: #00f;
}
```

Above is an example of a poor way to name an element. What happens if the designer decides later that the red buttons should be orange. Now she is stuck with not only changing the line of CSS which controls the backgorund colour, but also has to update the class name both in the stylesheet and the HTML document; or live with a `<button class="red">...</button>` which is now orange.

**Better naming:**
```css
button.danger {
  background-color: #f00;
}

button.success {
  background-color: #0f0;
}

button.primary {
  background-color: #00f;
}
```

Here our designer has named the element in a way that *describes* the content of the element – and can now style this "danger" element with whatever design decision she chooses.


## Unavoidable Unsemantic Names

It's not always plausible to use entirely semantic naming conventions in all scenarios. Sometimes you need to describe a purely visual style and not the content an element contains. Here are a few examples of unavoidable unsemantic class names:

Clearing floats:
```css
.clearfix { ... }
```

Grid Structures:
```css
.row { ... }
.column { ... }
.span-1, .span-2, .span-3 { ... }
```

## Multiple Class Names

Favour using multiple class names when it's feasible to break redundant code out into a separate class. For example:

```css
.button { /* could be applied to <button> or <a> tags */
  display: inline-block;
  padding: 0.5em 1em;
  color: #000;
  background-color: #ccc;
  border: none;
}

.button.danger {
  color: #fff;
  background-color: #f00;
}

.button.success {
  background-color: #0f0;
}

.button.primary {
  color: #fff;
  background-color: #00f;
}
```

Since the styles from `.button` are separated out into a separate class, our code stays DRY; changing the padding for all of the buttons, for example, can be done in one place.
