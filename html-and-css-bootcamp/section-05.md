# Other Elements

## [Span](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)s
`<span>:` The Content Span element
The `<span>` HTML element is a generic inline container for phrasing content, which does not inherently represent anything. It can be used to group elements for styling purposes (using the class or id attributes), or because they share attribute values, such as lang. It should be used only when no other semantic element is appropriate. `<span>` is very much like a `<div>` element, but `<div>` is a block-level element whereas a `<span>` is an inline element.
- Spans are generic **inline** elements. They have no special meaning but can be styled later using CSS.

## [Div](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s
`<div>`: The Content Division element
The `<div>` HTML element is the generic container for flow content. It has no effect on the content or layout until styled in some way using CSS (e.g. styling is directly applied to it, or some kind of layout model like Flexbox is applied to its parent element).
- Divs are generic containers that have no inherent meaning. They are used to group content together for styling.

## [Table](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)s
`<table>`: The Table element
The `<table>` HTML element represents tabular data — that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data.
- A useful resource for learning how to make cables can be found at [https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics)

## Semantic Markup
- In programming, Semantics refers to the meaning of a piece of code — for example "what effect does running that line of JavaScript have?", or "what purpose or role does that HTML element have" (rather than "what does it look like?".)
### [Semantics in HTML](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantics_in_html)
In HTML, for example, the h1 element is a semantic element, which gives the text it wraps around the role (or meaning) of "a top level heading on your page."
```
<h1>This is a top level heading</h1>
```
By default, most browser's user agent stylesheet will style an h1 with a large font size to make it look like a heading (although you could style it to look like anything you wanted).
On the other hand, you could make any element look like a top level heading. Consider the following:
```
<span style="font-size: 32px; margin: 21px 0;">Not a top-level heading!</span>
```
This will render it to look like a top level heading, but it has no semantic value, so it will not get any extra benefits as described above. It is therefore a good idea to use the right HTML element for the right job.
HTML should be coded to represent the data that will be populated and not based on its default presentation styling. Presentation (how it should look), is the sole responsibility of CSS.
Some of the benefits from writing semantic markup are as follows:
- Search engines will consider its contents as important keywords to influence the page's search rankings (see SEO)
- Screen readers can use it as a signpost to help visually impaired users navigate a page
- Finding blocks of meaningful code is significantly easier than searching through endless divs with or without semantic or namespaced classes
- Suggests to the developer the type of data that will be populated
- Semantic naming mirrors proper custom element/component naming
When approaching which markup to use, ask yourself, "What element(s) best describe/represent the data that I'm going to populate?" For example, is it a list of data?; ordered, unordered?; is it an article with sections and an aside of related information?; does it list out definitions?; is it a figure or image that needs a caption?; should it have a header and a footer in addition to the global site-wide header and footer?; etc.

### [Semantic elements](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantic_elements)
These are some of the roughly 100 semantic [elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) available:
- `<article>`
- `<aside>`
- `<details>`
- `<figcaption>`
- `<figure>`
- `<form>`
- `<footer>`
- `<header>`
- `<main>`
- `<mark>`
- `<nav>`
- `<section>`
- `<summary>`
- `<time>`

Why should we bother?
1. Accessibility
2. Search Engines
3. Developer Sanity