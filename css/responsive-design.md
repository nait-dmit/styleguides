CSS StyleGuide - Responsive Design
==================================

## Mobile-first

Mobile-first responsive coding practices are preferred. Media queries should be ordered so that styles are added as device widths increase. This trivial example simply changes the background colour at 4 breakpoints:

```css
/* tiny viewports, no media query needed */
html{ background: #f00; }

/* small viewports */
@media all and (min-width: 600px) {
  html{ background: #0f0; }
}

/* medium viewports */
@media all and (min-width: 960px) {
  html{ background: #00f; }
}

/* large viewports */
@media all and (min-width: 1400px) {
  html{ background: #ff0; }
}

/* huge viewports */
@media all and (min-width: 2000px) {
  html{ background: #0ff; }
}
```

## Breakpoint Sizes

Breakpoints should be specified in `px` values. The general idea is to aim for spots *between* common device sizes. As a general guideline, defer to the following breakpoints, unless your example situation dictates otherwise:

|        Device        | Breakpoint |
| :------------------- | :--------: |
| iPhone-ish           |    0px     |
| iPad-ish (portrait)  |   600px    |
| iPad-ish (landscape) |   960px    |
| Laptop-ish           |   1400px   |
| 27" Display-ish      |   2000px   |
