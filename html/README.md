


# HTML 5 Coding Best Practices

**Note:** This is a very early first draft, and it is based largely on the internal style-guide used at Github https://github.com/code-standards. A printer friendly version of this document can be found [here](http://sweb2.dmit.nait.ca/mday/html/coding-practice.html)

## Markup

The first component of any web page is the tag-based markup language of HTML. The Hyper Text Markup Language (HTML) has a sordid history but has come into its own in the last few years. After a lengthy experimentation with the XML-based XHTML variant the industry has accepted that HTML is the future of the web.

Markup defines the structure and outline of a document and offers a structured content. Markup is not intended to define the look and feel of the content on the page beyond rudimentary concepts such as headers, paragraphs, and lists. The presentation attributes of HTML have all been deprecated and style should be contained in Cascading Style Sheet.

HTML is used for **meaning**, changing the tags behaviour or core design is counterproductive.

## Validation

We will test our markup against the **W3C validator (validator.w3.org)**, to ensure that the markup is well formed. 100% valid code is not a goal, but validation certainly helps to write more maintainable sites as well as debugging code. **Our goal is not to guarantee code that is 100% valid, but instead assures the cross-browser experience is loosely consistent.**

## Doctype

A proper Doctype which triggers standards mode in your browser should always be used. Quirks mode should always be avoided.

A nice aspect of HTML5 is that it streamlines the amount of code that is required. Meaningless attributes have been dropped, and the ``<DOCTYPE>`` declaration has been simplified significantly. Additionally, there is no need to use ``<CDATA>`` to escape inline JavaScript, formerly a requirement to meet XML strictness in XHTML.

```
<!DOCTYPE html> 
```

## Character Encoding

All markup should be delivered as UTF-8, as it is the friendliest for internationalization. It should be designated in head of the document.

Setting the character set using ``meta`` tags.

```
<head>
    <meta charset="utf-8">
</head>
```

## Indentation

For all code languages, we require indentation to be done via soft tabs (using the space character). Use soft-tabs with a two or four space indent.

## Readability vs Compression

We prefer readability over file-size savings when it comes to maintaining existing files. Plenty of whitespace is encouraged.

## Quoting Attributes

The HTML5 specification defines quotes around attributes as optional. For consistency with attributes that accept whitespace, all attributes should be quoted. Additionally, each attribute of a tag must be separated from the preceding attribute by a space between them.

```
<p class="line note" data-attribute="106">This is my paragraph of special text.</p> 
```

## General Markup Guidelines

The following are general guidelines for structuring your HTML markup. Authors are reminded to always use markup which represents the semantics of the content in the document being created.

* The ``<title>`` tag must be an accurate and concise description of a page's content.
* A class is applied to the ``<body>`` to allow for unique page styling without any additional markup.
* All HTML5 elements must be properly nested.
* All HTML5 elements must be closed, either with the self-closing format or with a corresponding closing tag ( ``</section>`` ).
* All HTML5 elements must be in lowercase.
* Use actual ``<p>`` elements for paragraph delimiters as opposed to multiple ``<br>`` tags.
* Use hyphens to separate words in class and id names, not underscores, camel Case, or other methods.
* Make use of ``<dl>`` (definition lists) and ``<blockquote>``, when appropriate.
* Items in list form should always be housed in a ``<ul>`` , ``<ol>`` , or ``<dl>`` never a set of ``<div>`` or ``<p>`` tags.
* The height and width attributes of image tags are not applied to aid in responsiveness.
* Place an html comment on some closing ``<div>`` tags to indicate what element you're closing. It will help when there is lots of nesting and indentation.

```
</div>  <!-- This is the end of the wrapper --> 
```

* File Paths - Site resources use relative file paths for efficiency. Content file paths are absolute, assuming content is syndicated.
* The best location for JavaScript is at the bottom of the HTML document, right before the closing ``</body>`` tag. This allows every other external component on the page to download as quickly as possible before the scripts are loaded.
* Always use title-case for headers and titles. Do not use all caps or all lowercase titles in markup, instead apply the CSS property ``text-transform: uppercase/lowercase`` .

## Forms

* Use ``label`` fields to label each form field, the ``for`` attribute should associate itself with the input field, so users can click the labels. ``cursor:pointer;`` on the label is wise. Browsers using HTML5 require an ID set for form elements, so that the labels' FOR attribute can reference them. However; you still need NAME, as otherwise the form submission won't work on some browsers. so: you need both ID (which needs to be unique) *and* NAME (which does not necessarily have to be unique: for instance, with radio buttons that are mutually exclusive, you'd have the same NAME, but different unique IDs for each , as well.
* Do not use the size attribute on your input fields. The size attribute is relative to the font-size of the text inside the input. Instead use css width.

## Tables

* Tables shouldn't be used for page layout.
* Make use of ``<thead>``, ``<tfoot>``, ``<tbody>`` and ``<th>`` tags (and Scope attribute) when appropriate and table markup with proper syntax (``<thead>``, ``<tfoot>``, ``<tbody>`` and ``<th> scope]`` )

```
<table summary="This is a chart of year-end returns for 2005.">
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
    
## Accessibility

* All images must include alternate text (alt attribute), mostly for visually impaired uses but also for validation.
* All anchors must include title attributes, the title is not meant to be a duplication of the anchor text but is to provide additional / advisory information.
* The bold ``<b>`` and italicize ``<i>`` tags refer to visual presentation. This should be handled by the CSS. However, to have a selection of text look bold and have emphasis use a ``strong`` and an ``em`` tag.

## References:

"Markup &amp; Templates Styleguide." . Github, n.d. Web. 13 May 2014. https://github.com/styleguide/templates.


  