Execution Context [Scope]
=========================

JavaScript statements execute within a default context (or scope) known as the *global* context by default.  All variables and functions defined in this context become distinct properties of the *global object*.

The following is an example of variable declarations in the browser's global context:
```js
// declare global variable
var globalString = 'foo';

// window is the global object in the browser
// globalString is now a property of the window
// object in the browser
window.globalString; // yields 'foo'
```

Creating many variables and functions in the global context has the undesireable effect of polluting the global context with many new (often unimportant) properties.

For this reason, your code should never be executed in the global context directly.  The current solution is to use an Immediately-Invoked-Function-Expression ([IIFE](http://benalman.com/news/2010/11/immediately-invoked-function-expression/ "IFFE")) to enclose statements within a local context environment.

The following is an example of an IIFE:

```js
// IIFE
;(funciton () {
    var localString = 'foo';
}());

// the following will be undefined
window.localString; // yields undefined
```

An anonymous function has been declared and immediately called from the global context.    All functions in JavaScript execute in a local context, which prevents pollution of the global context (`window` in the browser) by trapping all declarations within the function… unless you do not explicitly declare variables with the reserved word `var`.

This would hoist the variable into the global context like the following illustrates:

```js
// improper variable declaration
;(funciton () {
    localString = 'foo';
}());

// stating variable names without preceding with var
// will automatically hoist them into the global context
window.localString; // yields 'foo'
```

For this reason, **it is extremely important to precede any and all variable declarations with `var` to explicitly define the variable's intended scope.**

Using and IIFE also helps to prevent namespace collisions in the global context.  Required global objects are still available within the IIFE, but they could be passed as arguments as well, which allows you to define them as parameters with whatever names you like.

The following demonstrates how to pass global arguments to an IIFE:

```js
// IIFE call with arguments
;(funciton (global, $) {
    // execute statements here...
}(this, jQuery));
```

In this example, the global object will be passed as `this` along with the `jQuery` function when the IIFE is called. Within the IIFE, the global object and jQuery can be referenced via the `global` and `$` parameters respectively.  This can help alleviate any concern over using the `$` shorthand for jQuery by explicitly passing it by its long name to the IIFE, where you can name it as anything you like.