### Modals

![Bootstrap Logo](https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg)

[Bootstrap Documentation](https://getbootstrap.com/)

## Index
1. [What is a Modal?](#what-is-a-modal)
2. [Basic Structure of a Modal](#basic-structure-of-a-modal)
3. [Triggering a Modal](#triggering-a-modal)
4. [Customizing Modals](#customizing-modals)
5. [Example: Creating a Confirmation Modal](#example-creating-a-confirmation-modal)

## What is a Modal?

A modal in Bootstrap is a dialog box or popup that is displayed on top of the current page. Modals are a great way to get the user’s attention, confirm actions, or display additional information without navigating away from the current page. Bootstrap provides a built-in modal component that is fully responsive and customizable.

## Basic Structure of a Modal

The basic structure of a Bootstrap modal consists of several key elements:

- **Modal Wrapper (`<div class="modal">`)**: The outermost container that holds the entire modal.
- **Modal Dialog (`<div class="modal-dialog">`)**: Defines the dialog box and its content.
- **Modal Content (`<div class="modal-content">`)**: The actual content of the modal, including the header, body, and footer.
- **Modal Header (`<div class="modal-header">`)**: Contains the modal’s title and the close button.
- **Modal Body (`<div class="modal-body">`)**: The main content area of the modal.
- **Modal Footer (`<div class="modal-footer">`)**: Contains action buttons, like "Save" or "Close".

### Example Structure

```html
<div class="modal fade" id="myModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        This is the body of the modal.
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

### Explanation

- **`id="myModal"`**: This is the unique identifier for the modal, which is used to trigger it.
- **`tabindex="-1"`**: Ensures that the modal cannot be focused until it's triggered.
- **`aria-labelledby` and `aria-hidden`**: These attributes help with accessibility, indicating the modal's title and whether it's currently visible or hidden.

## Triggering a Modal

You can trigger a modal using a button or any other element with a data attribute. The `data-bs-toggle="modal"` and `data-bs-target="#myModal"` attributes are used to associate the trigger with the modal.

### Example Trigger

```html
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#myModal">
  Launch demo modal
</button>
```

When the user clicks this button, the modal with the `id="myModal"` will appear.

## Customizing Modals

Bootstrap allows you to customize modals in various ways, including changing their size, adding scrolling, and even stacking multiple modals.

### Changing Modal Size

You can adjust the size of the modal by adding the `.modal-sm`, `.modal-lg`, or `.modal-xl` class to the `.modal-dialog` element.

```html
<div class="modal-dialog modal-lg">
  <div class="modal-content">
    <!-- Modal content -->
  </div>
</div>
```

### Scrolling Modals

For content that exceeds the modal’s height, you can make the modal body scrollable by adding the `.modal-dialog-scrollable` class to the `.modal-dialog`.

```html
<div class="modal-dialog modal-dialog-scrollable">
  <div class="modal-content">
    <!-- Modal content -->
  </div>
</div>
```

## Example: Creating a Confirmation Modal

Let’s create a confirmation modal that asks the user to confirm or cancel an action.

### HTML

```html
<!-- Trigger Button -->
<button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#confirmModal">
  Delete Item
</button>

<!-- Confirmation Modal -->
<div class="modal fade" id="confirmModal" tabindex="-1" aria-labelledby="confirmModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="confirmModalLabel">Confirm Deletion</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        Are you sure you want to delete this item? This action cannot be undone.
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
        <button type="button" class="btn btn-danger">Confirm Delete</button>
      </div>
    </div>
  </div>
</div>
```

### Explanation

- **Trigger Button**: The button labeled "Delete Item" triggers the modal when clicked.
- **Confirmation Modal**: The modal asks the user to confirm their decision to delete an item. It includes "Cancel" and "Confirm Delete" buttons in the footer.
- **`btn-danger` Class**: This class styles the "Confirm Delete" button in red to indicate the seriousness of the action.

## Sources 📖
- [Bootstrap Documentation](https://getbootstrap.com/)
- [Bootstrap Modals Overview](https://getbootstrap.com/docs/5.3/components/modal/)