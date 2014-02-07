CSS StyleGuide - Responsive Design
==================================

## Mobile-first

Mobile-first responsive coding practices are preferred. Media queries should be ordered so that styles are added as device widths increase. This trivial example simply changes the background colour at 4 breakpoints:

```css
/* smallest viewports, no media query needed */
html{ background: #f00; }

/* medium viewports */
@media all and (min-width: 600px) {
  html{ background: #0f0; }
}

@media all and (min-width: 960px) {
  html{ background: #00f; }
}

@media all and (min-width: 1400px) {
  html{ background: #f0f; }
}
```
