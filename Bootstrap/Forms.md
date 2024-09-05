### Forms

![Bootstrap Logo](https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg)

[Bootstrap Documentation](https://getbootstrap.com/)

## Index
1. [Introduction to Forms in Bootstrap](#introduction-to-forms-in-bootstrap)
2. [Basic Form Structure](#basic-form-structure)
3. [Form Controls](#form-controls)
4. [Form Validation](#form-validation)
5. [Example: Building a Registration Form](#example-building-a-registration-form)

## Introduction to Forms in Bootstrap

Forms are an essential part of web development, allowing users to interact with your website by submitting data. Bootstrap provides a wide variety of components, styles, and utilities that make it easy to build responsive, accessible, and well-designed forms.

## Basic Form Structure

A basic form in Bootstrap follows the standard HTML form structure but can easily be enhanced with Bootstrap's form-related classes. Bootstrap provides grid-based layouts for forms, inline forms, and horizontal forms.

### Example

```html
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

### Explanation

- **`form-control`**: Applies Bootstrap's default styles to input fields.
- **`mb-3`**: Adds bottom margin to create spacing between form groups.
- **`form-label`**: Provides the appropriate styling for form labels.
- **`btn btn-primary`**: Styles the submit button with Bootstrap's primary button styling.

## Form Controls

Bootstrap provides a wide range of form controls including text inputs, checkboxes, radios, dropdowns, and more.

### Example: Different Form Controls

```html
<form>
  <!-- Text Input -->
  <div class="mb-3">
    <label for="name" class="form-label">Name</label>
    <input type="text" class="form-control" id="name" placeholder="Enter your name">
  </div>

  <!-- Checkbox -->
  <div class="form-check">
    <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
    <label class="form-check-label" for="flexCheckDefault">
      Accept terms and conditions
    </label>
  </div>

  <!-- Radio Buttons -->
  <div class="form-check">
    <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1" checked>
    <label class="form-check-label" for="flexRadioDefault1">
      Option 1
    </label>
  </div>
  <div class="form-check">
    <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault2">
    <label class="form-check-label" for="flexRadioDefault2">
      Option 2
    </label>
  </div>

  <!-- Select Dropdown -->
  <div class="mb-3">
    <label for="exampleSelect" class="form-label">Choose your option</label>
    <select class="form-select" id="exampleSelect">
      <option>Option 1</option>
      <option>Option 2</option>
      <option>Option 3</option>
    </select>
  </div>
  
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

### Explanation

- **Text Input**: The `.form-control` class styles a simple text input.
- **Checkbox and Radio**: `.form-check-input` and `.form-check-label` are used to style checkboxes and radio buttons.
- **Select Dropdown**: The `.form-select` class is used to style the dropdown list.

## Form Validation

Bootstrap provides custom validation styles for forms, allowing you to provide visual feedback to users based on their input. You can use HTML5 validation along with Bootstrap's built-in validation styles.

### Example: Validation

```html
<form class="needs-validation" novalidate>
  <div class="mb-3">
    <label for="validationCustom01" class="form-label">First name</label>
    <input type="text" class="form-control" id="validationCustom01" required>
    <div class="valid-feedback">
      Looks good!
    </div>
    <div class="invalid-feedback">
      Please enter your first name.
    </div>
  </div>
  <div class="mb-3">
    <label for="validationCustom02" class="form-label">Last name</label>
    <input type="text" class="form-control" id="validationCustom02" required>
    <div class="valid-feedback">
      Looks good!
    </div>
    <div class="invalid-feedback">
      Please enter your last name.
    </div>
  </div>
  <div class="mb-3">
    <label for="validationCustomUsername" class="form-label">Username</label>
    <div class="input-group">
      <span class="input-group-text" id="inputGroupPrepend">@</span>
      <input type="text" class="form-control" id="validationCustomUsername" aria-describedby="inputGroupPrepend" required>
      <div class="invalid-feedback">
        Please choose a username.
      </div>
    </div>
  </div>
  <button class="btn btn-primary" type="submit">Submit form</button>
</form>
```

### Explanation

- **Validation Feedback**: `valid-feedback` and `invalid-feedback` provide custom feedback when the form is successfully validated or has errors.
- **HTML5 Validation**: Bootstrap uses the browser’s built-in validation system to check for required fields.

## Example: Building a Registration Form

Below is an example of a complete registration form with various form controls and validation.

```html
<form class="row g-3 needs-validation" novalidate>
  <div class="col-md-6">
    <label for="validationCustom01" class="form-label">First name</label>
    <input type="text" class="form-control" id="validationCustom01" value="Mark" required>
    <div class="valid-feedback">
      Looks good!
    </div>
  </div>
  <div class="col-md-6">
    <label for="validationCustom02" class="form-label">Last name</label>
    <input type="text" class="form-control" id="validationCustom02" value="Otto" required>
    <div class="valid-feedback">
      Looks good!
    </div>
  </div>
  <div class="col-md-6">
    <label for="validationCustomUsername" class="form-label">Username</label>
    <div class="input-group has-validation">
      <span class="input-group-text" id="inputGroupPrepend">@</span>
      <input type="text" class="form-control" id="validationCustomUsername" aria-describedby="inputGroupPrepend" required>
      <div class="invalid-feedback">
        Please choose a username.
      </div>
    </div>
  </div>
  <div class="col-md-6">
    <label for="validationCustom03" class="form-label">City</label>
    <input type="text" class="form-control" id="validationCustom03" required>
    <div class="invalid-feedback">
      Please provide a valid city.
    </div>
  </div>
  <div class="col-md-6">
    <label for="validationCustom04" class="form-label">State</label>
    <select class="form-select" id="validationCustom04" required>
      <option selected disabled value="">Choose...</option>
      <option>...</option>
    </select>
    <div class="invalid-feedback">
      Please select a valid state.
    </div>
  </div>
  <div class="col-md-6">
    <label for="validationCustom05" class="form-label">Zip</label>
    <input type="text" class="form-control" id="validationCustom05" required>
    <div class="invalid-feedback">
      Please provide a valid zip.
    </div>
  </div>
  <div class="col-12">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="" id="invalidCheck" required>
      <label class="form-check-label" for="invalidCheck">
        Agree to terms and conditions
      </label>
      <div class="invalid-feedback">
        You must agree before submitting.
      </div>
    </div>
  </div>
  <div class="col-12">
    <button class="btn btn-primary" type="submit">Submit form</button>
  </div>
</form>
```

### Explanation

- **Grid Layout**: The `.row` and `.col-md-*` classes are used to create a responsive form layout.
- **Validation**: The form uses Bootstrap's validation feedback system to guide the user in filling out the form correctly.
- **Multiple Controls**: The form includes text inputs, a dropdown, a checkbox, and a submit button to simulate a full registration process.

## Sources 📖
- [Bootstrap Documentation](https://getbootstrap.com/)
- [Bootstrap Forms Overview](https://getbootstrap.com/docs/5.3/forms/overview/)