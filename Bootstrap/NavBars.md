### Responsive Navbars

![Bootstrap Logo](https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg)

[Bootstrap Documentation](https://getbootstrap.com/)

## Index
1. [What is a Navbar?](#what-is-a-navbar)
2. [Basic Navbar Structure](#basic-navbar-structure)
3. [Responsive Navbar](#responsive-navbar)
4. [Toggling the Navbar](#toggling-the-navbar)
5. [Customizing the Navbar](#customizing-the-navbar)
6. [Example: Building a Responsive Navbar](#example-building-a-responsive-navbar)

## What is a Navbar?

A navbar (short for navigation bar) is a user interface element that provides easy access to different sections of a website. Bootstrap 5 offers a flexible, fully responsive, and customizable navigation bar component. It allows you to build navigation menus that adapt to various screen sizes.

## Basic Navbar Structure

To create a basic navbar in Bootstrap, you use the `navbar` class along with `navbar-expand-*` and `navbar-light` or `navbar-dark` depending on your design needs. The `navbar-expand-*` class ensures that the navbar is responsive.

### Example

```html
<nav class="navbar navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <form class="d-flex">
      <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success" type="submit">Search</button>
    </form>
  </div>
</nav>
```

### Explanation

- **`navbar`**: The main class that defines the element as a Bootstrap navbar.
- **`navbar-light` and `bg-light`**: The navbar is styled with a light background and dark text.
- **`form-control`** and **`btn`**: Bootstrap classes are used for form controls like the search input and button.

## Responsive Navbar

The `navbar-expand-*` class determines when the navbar should expand into its full layout. You can choose from different breakpoints such as `navbar-expand-sm`, `navbar-expand-md`, `navbar-expand-lg`, and `navbar-expand-xl` depending on when you want the navbar to collapse into a toggleable menu.

### Example

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Brand</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Features</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Pricing</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
```

### Explanation

- **`navbar-expand-lg`**: The navbar will collapse into a toggleable menu on screens smaller than large (`lg`), meaning it expands on large screens and above.
- **`navbar-toggler`**: The button that appears when the navbar collapses, allowing users to toggle the navigation menu.
- **`collapse navbar-collapse`**: The classes used to control the collapsing and expanding of the menu.

## Toggling the Navbar

The responsive behavior of the navbar is controlled using the `navbar-toggler` button, which uses Bootstrap's JavaScript functionality to toggle the visibility of the navbar links. When the screen size is below the specified breakpoint, the navbar items collapse into a toggleable menu.

### Example

```html
<button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
  <span class="navbar-toggler-icon"></span>
</button>
```

- **`data-bs-toggle="collapse"`**: Triggers the collapse behavior.
- **`data-bs-target="#navbarNavDropdown"`**: Specifies the target element that will collapse/expand.
- **`aria-expanded="false"`**: Accessibility attribute that indicates whether the element is expanded or collapsed.

## Customizing the Navbar

Bootstrap navbars can be customized with various color schemes, background utilities, and spacing. You can use `navbar-light` or `navbar-dark` for contrasting text colors and choose from a range of background utilities like `bg-dark`, `bg-light`, `bg-primary`, etc.

### Example

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand"