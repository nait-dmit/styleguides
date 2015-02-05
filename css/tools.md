CSS StyleGuide - Tools
======================

## Text Editor / IDE

The text editor or IDE you use is your choice, but consider using [Sublime Text](http://www.sublimetext.com/3), a cross-platform, extensible plain text editor. Favour text editors which have a small learning curve, get out of the way, and have a rich set of languages for syntax highlighting.

Never use Dreamweaver in design mode, or any other WYSIWYG-style editor which writes code for you. Never use an IDE which has an integrated web browser with an unknown or uncommon rendering engine (usually called a "preview" mode), testing should be done in a real browser.


## Development Browser

Favor using Google Chrome for development. The implementation of the CSS spec varies widely among various rendering engines, but Webkit has wide adoption and is in constant development.

When conducting cross-browser compatibility tests use Chrome, Firefox, Internet Explorer (going back 3 versions, so at the time of this writing, IE9, 10, & 11), and Safari (when access to Mac labs is available).


## Responsive Design

An easy way to simulate device widths for testing is to dock the developer tools in Chrome to the side and resize left/right to create the desired width restriction. This has the added benefit of having Web Inspector open and ready to use. This example simulates the size of an iPhone-like device:

![Responsive Testing Example](https://raw.github.com/nait-dmit/styleguides/master/assets/images/responsive-testing-example-01.png)

## Frameworks

Rapid prototyping should be done with [Bootstrap](http://getbootstrap.com/)


## Preprocessors

Favour [Sass](http://sass-lang.com/) over [Less](http://lesscss.org/)
