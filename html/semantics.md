# HTML5 Semantics

As often as possible, semantic tags should be used to markup content. It is difficult to encapsulate all of the rules on how this is done, as the context of the content that the HTML is being applied to is crucial. http://html5doctor.com/ provides a nice resource when faced with a challenging scenario. This document will only touch on a few of the more contentious areas.


## The `<main>` Element

This can be used, but only ever used once per page. HTML5 Doctor says:
  > The main element is an exact analogue of ARIA's role="main", and is designed to show screenreaders and assistive technologies exactly where main content begins, so it can be a target for a "skip links" keyboard command, for example. It could also be used for content syndication (Instapaper-ish things); mobile browsers could zoom in on main when encountering non-responsive websites.


## The `<hgroup>` Element

This has been deprecated from the HTML5 spec and should no longer be used.


## The `<h1> – <h6>` Elements

More research is needed. It seems these tags no longer effect SEO like they used to, and apparently it is appropriate to start your heirarchy over in each sectioning element of the page. (i.e., each new section starts with an `<h1>` tag)


## Presentational Elements Worth Noting

The bold `<b>` and italicize `<i>` tags refer to visual presentation and should be avoided; this should be handled by the CSS instead. However, to have a selection of text look bold and have emphasis use a `strong` and an `em` tag instead where appropriate.


## The `<br/>` Tag

This is largely presentational and should be avoided. There are, however, appropriate uses for this, such as breaking up an address into it's distinct parts. HTML5 Doctor says:
  > The br element represents a line break. br elements must be used only for line breaks that are actually part of the content, as in poems or addresses. br elements must not be used for separating thematic groups in a paragraph.
