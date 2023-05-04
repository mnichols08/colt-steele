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

| Attribute | Type or Types | Description |
|------ | ------ | ------ |
| accept | file | Hint for expected file type in file upload controls |
| alt | image | alt attribute for the image type. Required for accessibility |
| autocomplete | all except checkbox, radio, and buttons | Hint for form autofill feature |
| capture | file | Media capture input method in file upload controls |
| checked | checkbox, radio | Whether the command or control is checked |
| dirname | search, text | Name of form field to use for sending the element's directionality in form submission |
| disabled | all | Whether the form control is disabled |
| form | all | Associates the control with a form element |
| formaction | image, submit | URL to use for form submission |
| formenctype | image, submit | Form data set encoding type to use for form submission |
| formmethod | image, submit | HTTP method to use for form submission |
| formnovalidate | image, submit | Bypass form control validation for form submission |
| formtarget | image, submit | Browsing context for form submission |
|  height | image | Same as height attribute for `<img>`; vertical dimension |
|  list | all except hidden, password, checkbox, radio, and buttons | Value of the id attribute of the `<datalist>` of autocomplete options |
| max | date, month, week, time, datetime-local, number, range | Maximum value |
|  maxlength | text, search, url, tel, email, password | Maximum length (number of characters) of value |
|  min | date, month, week, time, datetime-local, number, range | Minimum value |
|  minlength | text, search, url, tel, email, password | Minimum length (number of characters) of value |
|  multiple | email, file | Boolean. Whether to allow multiple values |
|  name | all | Name of the form control. Submitted with the form as part of a name/value pair |
|  pattern | text, search, url, tel, email, password | Pattern the value must match to be valid |
|  placeholder | text, search, url, tel, email, password, number | Text that appears in the form control when it has no value set |
|  popovertarget | button | Designates an `<input type="button">` as a control for a popover element |
|  popovertargetaction | button | Specifies the action that a popover control should perform |
|  readonly | all except hidden, range, color, checkbox, radio, and buttons | Boolean. The value is not editable |
|  required | all except hidden, range, color, and buttons | Boolean. A value is required or must be check for the form to be submittable |
|  size | text, search, url, tel, email, password | Size of the control |
|  src | image | Same as src attribute for `<img>`; address of image resource |
|  step | date, month, week, time, datetime-local, number, range | Incremental values that are valid |
|  type | all | Type of form control |
|  value | all except image | The initial value of the control |
|  width | image | Same as width attribute for `<img>` |

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
- Use `<textarea>` tags to create a multi-line text input. For example if we wanted to allow users to submit an essay or bio.
