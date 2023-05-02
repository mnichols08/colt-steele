# More HTML

## Working With HTML Lists
In HTML we can nest elements within elements and some elements such as lists actually expect us to do just that.
A simple list can be created by first creating an unordered list element [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul). On it's own nothing will render but if we add a list item `<li>` within then we create a single item within a bulleted list.
A numbered list can be created by instead of using the unordered list element we instead use the ordered list element [`[<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) then follow the same pattern.

## The Em, Strong, B, and I elements
### Emphasis
- Use the [`<em>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em) element for text that has a stressed emphasis relative to the surrounding text. Most browsers will render it in italics, but you can change this CSS. Use it because we have a meaning - for it. This is crucial for semantic html.
- Use the [`<i>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/i) element for text that is set off from the normal text for some reason (latin terms, technical words, etc.) Use it for text that is traditionally italicized, only when there is not a more suitable element.
### Strong
Use the[ `<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) element for text that has specific significance. Browsers will display it as bold, but you can change this via CSS, but it keeps things semantic that this is more important or stronger than the other text.
Use the [`<b>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b) element to bring attention to text. Use it for text that is traditionally bolded, only when there is not a more suitable element.

This is the general pattern and mindset. HTML lets you do all sorts of wild and crazy stuff but the standards of the web suggest that we do things this way.

## Nesting Elements
Every element within html is capable of being nested. Technically every single element on an page is nested within the parent `<html>` tag.

## Superscript and Subscript
Use the [`<sup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup) tags to designate text as superscript (raised baseline with smaller text)
Use the [`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub) tags to designate text as subscript (lowered baseline with smaller text)