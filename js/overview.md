JS StyleGuide
==============

Welcome to the NAIT DMIT JS Styleguide.

**This is a work in progress.**  *The style guide for DMIT will be based largely on the internal styleguide used at Google found here -> https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml*

## Script Placement

* Favour placing script tags at the end of the HTML body for performance reasons

## Statements
* One statement per line
* All single-line statements must end with a `;`

## Block Statements

* Statements between `{` and `}` should be indented
* `{` should appear on the same line as whatever precedes it and never on a line by itself
    * This is to help avoid errors with automatic semi-colon insertion [ASE](http://es5.github.io/#x7.9 "ASE") when minifying files
* `}` should always appear on a line by itself
    * Except when followed by `else` or `while`
* Braces must be present for all control statements, regardless of the number of statements required

## Indentation

Indentation should be done with 2 or 4 spaces (prefereaby 4 and avoid tabs whenever possible)

## Variables and Naming

* Always declare variables with `var` to avoid global context pollution
    * Good: `var foo;`
    * Bad: `bar;`
* Use meaningful names whenever possible
    * Good: `var firstName;`
    * Bad: `var fn;`
* Names for variables and normal functions should be camelCase
    * Good: `var firstName;`
    * Bad: `var firstname;`
    * Bad: `var first_name;`
* Names for constructor functions should be TitleCase
    * Good: `function Person() {…}`
    * Bad: `function person() {…}`
* Names for variables that should be treated as constants should be CAPITAL_CASE
    * Good: `var TAX_RATE = 0.05;`
    * Bad: `var taxRate = 0.05;`
	* Avoid the use of `const` for constants, it isn't supported in IE

## Spacing

* A space must be present on both sides of binary operators
    * Good: `2 + 2`
    * Bad: `2+2`
* Commas should be followed by a single space
    * Good: `function fn(a, b, c) {…}`
    * Bad: `function fn(a,b,c) {…}`
* No spaces should separate unary operators from their target operand
    * Good: `++i`
    * Bad: `++ i`
* Use blank lines to separate logical groups of statements

## Comments

* Inline comments should appear on a single line and never on the same line as code
* For block comments, consistency is important
    * One style of block comment should be used per file
* Multiple inline comments can be used in place of block comments
* All functions should be preceded by a comment, which lists any parameters and the purpose of the function
* Comment any complex sections of code to make clear its purpose
* [JSDoc](http://jsdoc.org "JSDoc") style is preferred for projects

## Control Statements

* A single blank line should precede all control statements
* Conditions should be preceded with a single space
* All control statements will use braces, regardless of length

### if-else

```js
if (condition) {
    // true condition statements
} else {
    // false condition statements
}
```

* A single space should separate the condition from the `{`
* A single space should be present on both sides of `else`

### Stacked if-else

* When stacking an if-else statement, subsequent `if (condition)` statements should follow immediately after `else`

```js
if (condition1) {
    // condition1 statements
} else if (condition2) {
    // condition2 statements
} else {
    // no match
}
```

### Nested if-else

```js
if (condition1) {

    if (condition2) {
        // condition2 statements
    } else {
        // false condition2 statements
    }
} else {
    // false condition1 statements
}
```

### switch

* Every `case` will end with `break`
    * Switch statement fall through is discouraged

```js
switch (variable) {
    case 1:
        // case 1 statements
        break;
    case 2:
        // case 2 statements
        break;
    …
    default:
        // default statements
        break;
}
```
### do-while

* do-while statements should be followed by a `;`

```js
do  {
    // true condition statements
} while (condition);
```

### while

```js
while (condition) {
    // true condition statements
}
```
### for

* A single space should follow `;` in a `for` statement

```js
for (initialize; condition; iteration) {
    // true condition statements
}
```

## Functions

* Declared functions and function expressions are acceptable
* Functions should be declared before they are used
* `return` statements should be preceded by a single blank line
* Declared functions should not be followed by `;`

```js
function funcName(param1, param2, ...) {
    // function statements

    // return statements only when required
    return value;
}
```

* A single space should follow `function` when using anonymous functions
* Function expressions should be followed with a `;`

```js
var funcName = function (param1, param2, ...) {
    // function statements
};
```