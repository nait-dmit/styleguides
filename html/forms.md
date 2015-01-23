# Forms

## Labels

Use `<label>` elements to label each form field, the `for` attribute should associate itself with the input field via the input element's id, so users can click the labels. `cursor:pointer;` on the label is wise.

Browsers using HTML5 require an ID set for form elements, so that the labels' FOR attribute can reference them. However; you still need NAME, as otherwise the form submission won't work on some browsers. so: you need both ID (which needs to be unique) *and* NAME (which does not necessarily have to be unique: for instance, with radio buttons that are mutually exclusive, you'd have the same NAME, but different unique IDs for each , as well.


## Sizing Attributes

Do not use the `size` attribute on your `<input>` elements, or the `cols` or `rows` attributes on `<textarea>` elements. Use CSS instead.

```html
<!-- this is a good example! -->
<form id="app-login" action="process.php">
  <fieldset>
    <legend>Login Details</legend>
    <div>
      <label for="user-name">Username</label>
      <input id="user-name" name="user-name" type="email" placeholder="Your username is your email address" required autofocus>
    </div>
    <div>
      <label for="password">Password</label>
      <input id="password" name="password" type="password" placeholder="6 digits, a combination of numbers and letters" required>
    </div>
    <div>
      <input name="login" type="submit" value="Login">
    </div>
  </fieldset>
</form>
```
