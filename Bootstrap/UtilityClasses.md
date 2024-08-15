### Utility Classes

![Bootstrap Logo](https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg)

[Bootstrap Documentation](https://getbootstrap.com/)

## Index
1. [What are Utility Classes?](#what-are-utility-classes)
2. [Commonly Used Utilities](#commonly-used-utilities)
3. [Spacing Utilities](#spacing-utilities)
4. [Text Utilities](#text-utilities)
5. [Background and Border Utilities](#background-and-border-utilities)
6. [Example: Using Utility Classes in a Layout](#example-using-utility-classes-in-a-layout)

## What are Utility Classes?

Utility classes in Bootstrap are single-purpose classes designed to control specific elements' styling without needing to write custom CSS. These classes provide a quick and efficient way to modify the appearance of elements directly in the HTML, ensuring consistency and reducing the need for custom styles.

Utility classes are typically very small and focused, such as setting margin, padding, text alignment, colors, or visibility. By using these predefined classes, you can rapidly prototype or adjust the design of your project without adding extra CSS.

## Commonly Used Utilities

Bootstrap provides a wide range of utility classes that cover most of the common styling needs. Some of the most commonly used utility classes include:

- **Spacing Utilities**: Control margins and padding.
- **Text Utilities**: Adjust text alignment, wrapping, and font weight.
- **Background and Border Utilities**: Set background colors, borders, and border-radius.
- **Display Utilities**: Manage the visibility of elements.

## Spacing Utilities

Spacing utilities are among the most frequently used utilities in Bootstrap. They allow you to add or remove margins and padding from elements.

### Margin Utilities

Margin utilities control the space outside an element.

- `.m-0` – No margin
- `.m-1` to `.m-5` – Increasing margin sizes
- `.mt-3` – Top margin
- `.mb-3` – Bottom margin
- `.mx-auto` – Horizontal margin set to auto

### Padding Utilities

Padding utilities control the space inside an element.

- `.p-0` – No padding
- `.p-1` to `.p-5` – Increasing padding sizes
- `.pt-3` – Top padding
- `.pb-3` – Bottom padding
- `.px-3` – Horizontal padding

### Example

```html
<div class="p-3 mb-2 bg-light text-dark">This is a padded box with a bottom margin.</div>
```

In this example, the box has padding all around (`p-3`) and a bottom margin (`mb-2`).

## Text Utilities

Text utilities in Bootstrap allow you to control text alignment, color, wrapping, and font weight.

### Alignment

- `.text-start` – Align text to the left
- `.text-center` – Center the text
- `.text-end` – Align text to the right

### Color

- `.text-primary` – Primary text color
- `.text-secondary` – Secondary text color
- `.text-danger` – Red text (often used for error messages)

### Font Weight

- `.fw-bold` – Bold text
- `.fw-normal` – Normal text weight
- `.fw-light` – Light text weight

### Example

```html
<p class="text-center text-primary fw-bold">This is a centered, bold, primary-colored paragraph.</p>
```

## Background and Border Utilities

Background and border utilities help you manage element backgrounds and borders with ease.

### Background Color

- `.bg-primary` – Blue background
- `.bg-success` – Green background
- `.bg-danger` – Red background

### Borders

- `.border` – Adds a border around the element
- `.border-0` – Removes all borders
- `.border-top` – Adds a border at the top
- `.rounded` – Adds a border-radius
- `.rounded-circle` – Makes the element circular

### Example

```html
<div class="bg-success text-white p-3 rounded">This is a success box with rounded corners.</div>
```

## Example: Using Utility Classes in a Layout

Let's create a simple card component using utility classes.

```html
<div class="card" style="width: 18rem;">
  <img src="https://via.placeholder.com/150" class="card-img-top" alt="Placeholder Image">
  <div class="card-body">
    <h5 class="card-title text-center text-primary">Card Title</h5>
    <p class="card-text text-muted">This is a simple card example using Bootstrap utility classes for styling.</p>
    <a href="#" class="btn btn-primary d-block mt-3">Go somewhere</a>
  </div>
</div>
```

### Explanation

- **Card Component**: The card is styled with utility classes such as `text-center`, `text-primary`, and `text-muted` for easy customization.
- **Button**: The button uses `.d-block` to make it full-width and `.mt-3` to add a top margin.

## Sources 📖
- [Bootstrap Documentation](https://getbootstrap.com/)
- [Utility API Documentation](https://getbootstrap.com/docs/5.3/utilities/api/)