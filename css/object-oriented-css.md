CSS StyleGuide - Object Oriented CSS (OOCSS)
============================================

Favour using OOCSS practices when creating in class examples and demoing techniques.

The basic idea is to break up CSS into modular classes, which can be applied in combination to elements to create desired results. In CSS we'll build components and then use them on the page (like building with Lego).

For example, given this CSS:

```css
.notice {
  padding: 1em 3em;
  margin: 20px 0;
}

.button {
  display: inline-block;
  padding: 0.5em 1em;
  color: #000;
  background-color: #ccc;
  border: 1px solid #aaa;
}

.larger {
  font-size: 2em;
}

.smaller {
  font-size: 0.75em;
}

.primary {
  background-color: #66f;
  border-color: #00f;
}

.success {
  background-color: #6f6;
  border-color: #0f0;
}

.danger {
  background-color: #f66;
  border-color: #f00;
}
```

The designer can use these classes in combination on a few choice elements:

```html
<p class="notice primary larger">You have new mail!</p>
```

```html
<a class="button primary" href="...">View</a>
<a class="button" href="...">Edit</a>
<button class="button danger">Delete</button>
```

```html
<form action="..." method="...">
  ...
  <input type="submit" class="button success" name="Save" />
</form>
```
