# HTML Attributes

## Format

Attributes should be written as such: the attribute name, followed by an equals sign, followed by the double-quoted value. Spaces should not be used to separate any of these parts. In the case of `data-` attributes, multi-word identifiers should be separated by a hyphen.

Additionally, each attribute of a tag must be separated from the preceding attribute by a single space between them.

## Quoted Values

The HTML5 specification defines quotes around attributes as optional. For consistency with attributes that accept whitespace, all attributes should be quoted using double quotes.

```html
<!-- This is a good example! -->
<p class="line note" data-charater-count="106">My paragraph of special text.</p>
```

## Unnecessary Attributes

In HTML5, some of the previously necessary attributes have become part of the browser defaults and can be omitted.
* `<style>` tags no longer require a `type="text/css"` attribute, as this is default
* `<script>` tags no longer require a `type="text/javascript"` attribute, as this is default
* `<link>` tags no longer require a `type="text/css"` attribute, as this is default
