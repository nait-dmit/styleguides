## Tables

* Tables shouldn't be used for page layout.
* Make use of `<thead>`, `<tfoot>`, `<tbody>` and `<th>` tags (and Scope attribute) when appropriate and table markup with proper syntax (`<thead>`, `<tfoot>`, `<tbody>` and `<th> scope]` )

```html
<!-- This is a good example! -->
<table>
    <thead>
        <tr>
            <th scope="col">Table header 1</th>
            <th scope="col">Table header 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Table data 1</td>
            <td>Table data 2</td>
        </tr>
    </tbody>
    <tfoot>
            <tr>
                <td>Sum</td>
                <td>$180</td>
            </tr>
    </tfoot>
</table>
 ```
