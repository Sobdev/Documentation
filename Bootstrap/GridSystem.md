### Getting Started with the Grid System

![Bootstrap Logo](https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg)

[Bootstrap Documentation](https://getbootstrap.com/)

## Index
1. [Introduction to the Grid System](#introduction-to-the-grid-system)
2. [Basic Structure](#basic-structure)
3. [Grid Breakpoints](#grid-breakpoints)
4. [Responsive Columns](#responsive-columns)
5. [Nested Rows](#nested-rows)
6. [Example: Building a Simple Layout](#example-building-a-simple-layout)

## Introduction to the Grid System

The grid system in Bootstrap is one of its most powerful features. It provides a flexible and responsive layout structure that allows you to build complex, responsive designs with ease. Bootstrap’s grid system is built with **flexbox** and allows up to 12 columns across the page. This system is the foundation of most layouts in Bootstrap.

## Basic Structure

The grid system in Bootstrap is based on a series of containers, rows, and columns, which work together to create a flexible and responsive layout:

- **Container**: The container is the outermost element that houses the grid. It can be fixed-width or fluid (full-width).

- **Row**: Rows are horizontal groups of columns. They ensure that your columns are properly aligned.

- **Column**: Columns are the building blocks of the grid. You define how many columns an element should span, out of a possible 12.

### Example Structure

```html
<div class="container">
  <div class="row">
    <div class="col">
      <!-- Content for column 1 -->
    </div>
    <div class="col">
      <!-- Content for column 2 -->
    </div>
    <div class="col">
      <!-- Content for column 3 -->
    </div>
  </div>
</div>
```

In this example, the `.container` class is used to wrap the grid system, `.row` ensures the columns are aligned properly, and `.col` represents the columns which will take up equal space.

## Grid Breakpoints

Bootstrap provides a set of responsive, mobile-first breakpoints that enable you to control how the grid behaves at different screen sizes. The breakpoints are as follows:

- **Extra small (xs)**: `<576px`
- **Small (sm)**: `≥576px`
- **Medium (md)**: `≥768px`
- **Large (lg)**: `≥992px`
- **Extra large (xl)**: `≥1200px`
- **XXL (xxl)**: `≥1400px`

You can apply these breakpoints to your grid by appending the breakpoint name to the column class. For example, `.col-md-4` will create a column that spans 4 of the 12 columns at the medium breakpoint and above.

### Example

```html
<div class="row">
  <div class="col-12 col-md-6 col-lg-4">
    <!-- This column will span 12 columns on xs screens, 6 on md, and 4 on lg -->
  </div>
  <div class="col-12 col-md-6 col-lg-4">
    <!-- Similar configuration for responsiveness -->
  </div>
  <div class="col-12 col-md-6 col-lg-4">
    <!-- And this one too -->
  </div>
</div>
```

## Responsive Columns

Responsive columns automatically adjust their width depending on the viewport size. By default, columns will stack vertically on smaller screens and align horizontally as the screen size increases.

### Example

```html
<div class="container">
  <div class="row">
    <div class="col-6 col-sm-4">
      <!-- Will take up half the width on xs, one-third on sm -->
    </div>
    <div class="col-6 col-sm-4">
      <!-- Same as above -->
    </div>
    <div class="col-6 col-sm-4">
      <!-- Same as above -->
    </div>
  </div>
</div>
```

In this example, each column will occupy 50% of the width on extra small screens and 33.33% on small screens and above.

## Nested Rows

Bootstrap allows for nested rows, meaning you can create a row inside a column. This is useful when you need to create more complex layouts within a grid.

### Example

```html
<div class="container">
  <div class="row">
    <div class="col-8">
      <div class="row">
        <div class="col-6">
          <!-- Nested column 1 -->
        </div>
        <div class="col-6">
          <!-- Nested column 2 -->
        </div>
      </div>
    </div>
    <div class="col-4">
      <!-- Single column that spans 4 columns -->
    </div>
  </div>
</div>
```

## Example: Building a Simple Layout

Let's put everything we've learned together to create a simple, responsive layout using Bootstrap's grid system.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Grid Example</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container">
        <div class="row">
            <div class="col-12 col-md-8">
                <h1>Main Content</h1>
                <p>This is the main content area that takes up 8 columns on medium screens and above, and the full width on smaller screens.</p>
            </div>
            <div class="col-6 col-md-4">
                <h2>Sidebar</h2>
                <p>This sidebar takes up 4 columns on medium screens and above, and half the width on smaller screens.</p>
            </div>
        </div>
        <div class="row">
            <div class="col-12">
                <h2>Footer</h2>
                <p>This footer spans the entire width of the container.</p>
            </div>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

## Sources 📖
- [Bootstrap Documentation](https://getbootstrap.com/)
- [Flexbox Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)