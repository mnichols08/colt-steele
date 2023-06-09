# The Complete Guide To HTML

## The Web

* The World Wide Web is an information system where documents are available over the Internet. These documents are transferred over HTTP (Hyper Text Transport Protocol)

## HTTP

HTTP is a formerly defined set of rules for communication between a client (requestor) and a server (responder) That is really all we need to know.

## HTTP Response

A typical webpage consists of code written in HTML, CSS, and JavaScript, but it is not a rule that all three must be used!

## Working With HTML Lists

In HTML we can nest elements within elements and some elements such as lists actually expect us to do just that.
A simple list can be created by first creating an unordered list element [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul). On it's own nothing will render but if we add a list item `<li>` within then we create a single item within a bulleted list.
A numbered list can be created by instead of using the unordered list element we instead use the ordered list element [`[<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) then follow the same pattern.

## The Em, Strong, B, and I elements

### Emphasis

* Use the [`<em>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em) element for text that has a stressed emphasis relative to the surrounding text. Most browsers will render it in italics, but you can change this CSS. Use it because we have a meaning - for it. This is crucial for semantic html.
* Use the [`<i>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/i) element for text that is set off from the normal text for some reason (latin terms, technical words, etc.) Use it for text that is traditionally italicized, only when there is not a more suitable element.

### Strong

Use the[ `<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) element for text that has specific significance. Browsers will display it as bold, but you can change this via CSS, but it keeps things semantic that this is more important or stronger than the other text.
Use the [`<b>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b) element to bring attention to text. Use it for text that is traditionally bolded, only when there is not a more suitable element.

This is the general pattern and mindset. HTML lets you do all sorts of wild and crazy stuff but the standards of the web suggest that we do things this way.

## Nesting Elements

Every element within html is capable of being nested. Technically every single element on an page is nested within the parent `<html>` tag.

### Superscript and Subscript

Use the [`<sup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup) tags to designate text as superscript (raised baseline with smaller text)
Use the [`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub) tags to designate text as subscript (lowered baseline with smaller text)

### Inline vs. Block Elements

Certain elements like paragraphs `<p>`, headings `<h1>`, etc wil be displayed as block by default whereas other elements like `<em>` or `<span>`, or `<sub>`, etc. will be displayed inline instead.

### Creating Links

A link is created by providing a `href` property to an anchor [`<a>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a).
A relative link is a link that is assumed to be on the current server. It may not have a full URL, but just a `/path-to-file.html`

## Creating Images

Create image elements using the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) tag. Note that it does not have a closing tag! The src attribute specifies the location of the image to be displayed. Every image should have an `alt` attribute which describes the image for a screen reader or if the image cannot be rendered

## HTML Tables

* Should only be used to display tabular data - not for styling.
* `<table>`: The Table element
* The `<table>` HTML element represents tabular data — that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data.

<!---->

* `<th>`: The Table Header element
* The `<th>` HTML element defines a cell as the header of a group of table cells. The exact nature of this group is defined by the scope and headers attributes.

<!---->

* `<tr>`: The Table Row element
* The `<tr>` HTML element defines a row of cells in a table. The row's cells can then be established using a mix of <td> (data cell) and <th> (header cell) elements.

<!---->

* `<td>`: The Table Data Cell element
* The `<td>` HTML element defines a cell of a table that contains data. It participates in the table model.

```
<table>
    <thead>
        <tr>
            <th colspan="2">The table header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
        </tr>
    </tbody>
</table>
```

`colspan` and `rowspan` both allow us to have a cell take up more than one row or column

## Forms

# Working With Forms

Before we can discuss the `<form>` element, we need to discuss some elements that go inside of one.
HTML provides all sorts of form controls from buttons.

Forms are literally everywhere on the web, so we need to learn about them. But as mentioned before we must learn about elements that we will place inside of a form since forms behave a particular way.

## Text Inputs

The input element is extremely versatile. `set type="text"` to create a standard text input. Like `<a>`, it has no closing tag!

## [Input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)

`<input>`: The Input (Form Input) element
The `<input>` HTML element is used to create interactive controls for web-based forms in order to accept data from the user; a wide variety of types of input data and control widgets are available, depending on the device and user agent. The `<input> `element is one of the most powerful and complex in all of HTML due to the sheer number of combinations of input types and attributes.

## [Form](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

The `<form>` HTML element represents a document section containing interactive controls for submitting information.
Learn more about creating your first form [here](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form)
Forms typically do one of two things

1. Group Form Controls

* What inputs are part of the form?

2. Send the Data Somewhere

* Where does the form data go when submitted?
  The action attribute of a form is what tells the browser what to do with the data from a form by default.

## [Name](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#name) and Placeholder Attributes

A string specifying a name for the input control. This name is submitted along with the control's value when the form data is submitted.

| Attribute           | Type or Types                                                 | Description                                                                           |
| ------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| accept              | file                                                          | Hint for expected file type in file upload controls                                   |
| alt                 | image                                                         | alt attribute for the image type. Required for accessibility                          |
| autocomplete        | all except checkbox, radio, and buttons                       | Hint for form autofill feature                                                        |
| capture             | file                                                          | Media capture input method in file upload controls                                    |
| checked             | checkbox, radio                                               | Whether the command or control is checked                                             |
| dirname             | search, text                                                  | Name of form field to use for sending the element's directionality in form submission |
| disabled            | all                                                           | Whether the form control is disabled                                                  |
| form                | all                                                           | Associates the control with a form element                                            |
| formaction          | image, submit                                                 | URL to use for form submission                                                        |
| formenctype         | image, submit                                                 | Form data set encoding type to use for form submission                                |
| formmethod          | image, submit                                                 | HTTP method to use for form submission                                                |
| formnovalidate      | image, submit                                                 | Bypass form control validation for form submission                                    |
| formtarget          | image, submit                                                 | Browsing context for form submission                                                  |
| height              | image                                                         | Same as height attribute for `<img>`; vertical dimension                              |
| list                | all except hidden, password, checkbox, radio, and buttons     | Value of the id attribute of the `<datalist>` of autocomplete options                 |
| max                 | date, month, week, time, datetime-local, number, range        | Maximum value                                                                         |
| maxlength           | text, search, url, tel, email, password                       | Maximum length (number of characters) of value                                        |
| min                 | date, month, week, time, datetime-local, number, range        | Minimum value                                                                         |
| minlength           | text, search, url, tel, email, password                       | Minimum length (number of characters) of value                                        |
| multiple            | email, file                                                   | Boolean. Whether to allow multiple values                                             |
| name                | all                                                           | Name of the form control. Submitted with the form as part of a name/value pair        |
| pattern             | text, search, url, tel, email, password                       | Pattern the value must match to be valid                                              |
| placeholder         | text, search, url, tel, email, password, number               | Text that appears in the form control when it has no value set                        |
| popovertarget       | button                                                        | Designates an `<input type="button">` as a control for a popover element              |
| popovertargetaction | button                                                        | Specifies the action that a popover control should perform                            |
| readonly            | all except hidden, range, color, checkbox, radio, and buttons | Boolean. The value is not editable                                                    |
| required            | all except hidden, range, color, and buttons                  | Boolean. A value is required or must be check for the form to be submittable          |
| size                | text, search, url, tel, email, password                       | Size of the control                                                                   |
| src                 | image                                                         | Same as src attribute for `<img>`; address of image resource                          |
| step                | date, month, week, time, datetime-local, number, range        | Incremental values that are valid                                                     |
| type                | all                                                           | Type of form control                                                                  |
| value               | all except image                                              | The initial value of the control                                                      |
| width               | image                                                         | Same as width attribute for `<img>`                                                   |

## [Label](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)s

`<label>`: The Label element
The `<label>` HTML element represents a caption for an item in a user interface.

```
<label for="username">Enter Your Username</label>
<input type="text" id="username">
```

Always match a label element to a a form control using the `for` attribute. It must match the id attribute on an input.

## [Text Areas](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

`<textarea>`: The Textarea element
The `<textarea>` HTML element represents a multi-line plain-text editing control, useful when you want to allow users to enter a sizeable amount of free-form text, for example a comment on a review or feedback form.

* Use `<textarea>` tags to create a multi-line text input. For example if we wanted to allow users to submit an essay or bio.

## [Range Input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range)

`<input>` elements of type range let the user specify a numeric value which must be no less than a given value, and no more than another given value. The precise value, however, is not considered important. This is typically represented using a slider or dial control rather than a text entry box like the number input type.

```
<input type="range" min="0" max="11">
```

* Use `type='range'` to create a range input (slider)

## [Checkbox](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)

`<input type="checkbox">`
`<input>` elements of type checkbox are rendered by default as boxes that are checked (ticked) when activated, like you might see in an official government paper form. The exact appearance depends upon the operating system configuration under which the browser is running. Generally this is a square but it may have rounded corners. A checkbox allows you to select single values for submission in a form (or not).

```
<input type="checkbox" name="subscribe" />
```

* Use `type='checkbox'` to create a checkbox element

## Selects and Radio Button Groupings

* [Select](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)s
  `<select>`: The HTML Select element
  The `<select>` HTML element represents a control that provides a menu of options.

```
<select name="pets> id="pet-select">
    <option value="dog">Dog</option>
    <option value="cat">Cat</option>
    <option value="hamster">Hamster</option>
    <option value="parrot">Pattot</option>
    <option value="spider">Spider</option>
    <option value="goldfish">Goldfish</option>
</select>
```

* Populate a `<select>` element with `<option>` elements.
* The value is not visual to the user and is only sent through the form as data to identify which option the user has picked.

## [Radio](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio)

* `<input type="radio">`
* `<input>` elements of type radio are generally used in radio groups—collections of radio buttons describing a set of related options.
  Only one radio button in a given group can be selected at the same time. Radio buttons are typically rendered as small circles, which are filled or highlighted when selected.
  \==============================================================================================================================================================================

Match a label element to a a form control using the `for` attribute. It must match the id attribute on an input.

### Required Attribute

* By putting `required` on an input we tell the form that this value must be filled in.

### Span Elements

Spans are generic inline elements. They have no special meaning but can be styled later using CSS
Divs are also generic elements but they are block elements

### Audio

* Very simple in nature.
* `<audio>`: The Embed Audio element
* The `<audio>` HTML element is used to embed sound content in documents. It may contain one or more audio sources, represented using the src attribute or the <source> element: the browser will choose the most suitable one. It can also be the destination for streamed media, using a MediaStream.

```
<figure>
    <figcaption>Listen to the T-Rex:</figcaption>
    <audio
        controls
        src="/media/cc0-audio/t-rex-roar.mp3">
            <a href="/media/cc0-audio/t-rex-roar.mp3">
                Download audio
            </a>
    </audio>
</figure>

```

### Audio Events

| Event name     | Fired when                                                                                                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| audioprocess   | The input buffer of a ScriptProcessorNode is ready to be processed.                                                                                                                  |
| canplay        | The browser can play the media, but estimates that not enough data has been loaded to play the media up to its end without having to stop for further buffering of content.          |
| canplaythrough | The browser estimates it can play the media up to its end without stopping for content buffering.                                                                                    |
| complete       | The rendering of an OfflineAudioContext is terminated.                                                                                                                               |
| durationchange | The duration attribute has been updated.                                                                                                                                             |
| emptied        | The media has become empty; for example, this event is sent if the media has already been loaded (or partially loaded), and the HTMLMediaElement.load method is called to reload it. |
| ended          | Playback has stopped because the end of the media was reached.                                                                                                                       |
| loadeddata     | The first frame of the media has finished loading.                                                                                                                                   |
| loadedmetadata | The metadata has been loaded.                                                                                                                                                        |
| pause          | Playback has been paused.                                                                                                                                                            |
| play           | Playback has begun.                                                                                                                                                                  |
| playing        | Playback is ready to start after having been paused or delayed due to lack of data.                                                                                                  |
| ratechange     | The playback rate has changed.                                                                                                                                                       |
| seeked         | A seek operation completed.                                                                                                                                                          |
| seeking        | A seek operation began.                                                                                                                                                              |
| stalled        | The user agent is trying to fetch media data, but data is unexpectedly not forthcoming.                                                                                              |
| suspend        | Media data loading has been suspended.                                                                                                                                               |
| timeupdate     | The time indicated by the currentTime attribute has been updated.                                                                                                                    |
| volumechange   | The volume has changed.                                                                                                                                                              |
| waiting        | Playback has stopped because of a temporary lack of data                                                                                                                             |

## Video Element

`<video>`: The Video Embed element
The `<video>` HTML element embeds a media player which supports video playback into the document. You can use `<video>` for audio content as well, but the `<audio>` element may provide a more appropriate user experience.

```
<video controls width="250">
    <source src="/media/cc0-videos/flower.webm" type="video/webm">

    <source src="/media/cc0-videos/flower.mp4" type="video/mp4">

    Download the
    <a href="/media/cc0-videos/flower.webm">WEBM</a>
    or
    <a href="/media/cc0-videos/flower.mp4">MP4</a>
    video.
</video>
```

The above example shows simple usage of the <video> element. In a similar manner to the <img> element, we include a path to the media we want to display inside the src attribute; we can include other attributes to specify information such as video width and height, whether we want it to autoplay and loop, whether we want to show the browser's default video controls, etc.

The content inside the opening and closing <video></video> tags is shown as a fallback in browsers that don't support the element.

### Attributes

Like all other HTML elements, this element supports the global attributes.

* `autoplay`: A Boolean attribute; if specified, the video automatically begins to play back as soon as it can do so without stopping to finish loading the data.

<!---->

* To disable video autoplay, autoplay="false" will not work; the video will autoplay if the attribute is there in the <video> tag at all. To remove autoplay, the attribute needs to be removed altogether.

![Certificate](./certificate.jpg)
