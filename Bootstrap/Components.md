### Components

![Bootstrap Logo](https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg)

[Bootstrap Documentation](https://getbootstrap.com/)

## Index
1. [What are Bootstrap Components?](#what-are-bootstrap-components)
2. [Commonly Used Components](#commonly-used-components)
3. [Alerts](#alerts)
4. [Buttons](#buttons)
5. [Cards](#cards)
6. [Example: Creating a Simple Dashboard Layout](#example-creating-a-simple-dashboard-layout)

## What are Bootstrap Components?

Bootstrap components are pre-designed, reusable pieces of code that help you build consistent, responsive web interfaces quickly. These components are built using Bootstrap's CSS and JavaScript, providing functionality and styling out of the box. By using these components, you can significantly reduce development time and ensure a cohesive design throughout your application.

## Commonly Used Components

Bootstrap includes a wide variety of components that you can use in your projects. Some of the most commonly used components include:

- **Alerts**: For displaying important messages to the user.
- **Buttons**: For creating interactive buttons with various styles.
- **Cards**: For displaying content in a flexible and extensible container.
- **Modals**: For creating dialog boxes, popovers, or lightboxes.
- **Navbars**: For building responsive navigation bars.
- **Forms**: For building interactive forms with validation.

## Alerts

Alerts are used to display important messages or notifications to the user. Bootstrap provides several styles for alerts, such as success, danger, warning, and info.

### Example

```html
<div class="alert alert-success" role="alert">
  This is a success alert—check it out!
</div>

<div class="alert alert-danger" role="alert">
  This is a danger alert—be careful!
</div>

<div class="alert alert-warning" role="alert">
  This is a warning alert—proceed with caution!
</div>

<div class="alert alert-info" role="alert">
  This is an info alert—just so you know!
</div>
```

### Explanation

- **Classes**: The `.alert` class is used to create an alert. Additional classes like `.alert-success`, `.alert-danger`, etc., are used to define the type of alert.
- **Role**: The `role="alert"` attribute is used to identify the element as an alert for assistive technologies.

## Buttons

Buttons are essential components in any web application. Bootstrap provides a wide range of button styles, sizes, and states.

### Example

```html
<button type="button" class="btn btn-primary">Primary Button</button>
<button type="button" class="btn btn-secondary">Secondary Button</button>
<button type="button" class="btn btn-success">Success Button</button>
<button type="button" class="btn btn-danger">Danger Button</button>
<button type="button" class="btn btn-warning">Warning Button</button>
<button type="button" class="btn btn-info">Info Button</button>
<button type="button" class="btn btn-light">Light Button</button>
<button type="button" class="btn btn-dark">Dark Button</button>
```

### Explanation

- **Classes**: The `.btn` class is used to create a button. Additional classes like `.btn-primary`, `.btn-secondary`, etc., define the button's appearance.
- **Button Types**: Buttons can be used as standard clickable buttons or can trigger JavaScript actions when clicked.

## Cards

Cards are flexible content containers that allow you to combine text, images, links, and more. Cards are one of the most versatile components in Bootstrap.

### Example

```html
<div class="card" style="width: 18rem;">
  <img src="https://via.placeholder.com/150" class="card-img-top" alt="Placeholder Image">
  <div class="card-body">
    <h5 class="card-title">Card Title</h5>
    <p class="card-text">This is a simple card example using Bootstrap's card component.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

### Explanation

- **Card Container**: The `.card` class is used to create a card. The width of the card can be controlled using inline styles or additional utility classes.
- **Card Image**: The `.card-img-top` class is used to place an image at the top of the card.
- **Card Body**: The `.card-body` class wraps the text and other content inside the card.
- **Card Title and Text**: The `.card-title` and `.card-text` classes are used to style the title and content of the card.
- **Card Button**: The button inside the card is styled using the `.btn` and `.btn-primary` classes.

## Example: Creating a Simple Dashboard Layout

Let's build a simple dashboard layout using Bootstrap's components.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Dashboard Example</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container">
        <div class="row my-4">
            <div class="col">
                <h1>Dashboard</h1>
                <p>Welcome to the dashboard. Here you can manage your data.</p>
            </div>
        </div>
        <div class="row">
            <div class="col-md-6">
                <div class="card mb-4">
                    <div class="card-body">
                        <h5 class="card-title">Sales</h5>
                        <p class="card-text">Total sales: $10,000</p>
                        <a href="#" class="btn btn-primary">View Details</a>
                    </div>
                </div>
            </div>
            <div class="col-md-6">
                <div class="card mb-4">
                    <div class="card-body">
                        <h5 class="card-title">Users</h5>
                        <p class="card-text">Total users: 500</p>
                        <a href="#" class="btn btn-secondary">Manage Users</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-12">
                <div class="alert alert-info" role="alert">
                    This is an important update for all users!
                </div>
            </div>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

### Explanation

- **Dashboard Layout**: The layout consists of a header, two cards, and an alert. The cards are placed side by side on medium to large screens, and stack on smaller screens.
- **Responsive Design**: The `.col-md-6` class ensures that each card takes up half the width on medium and larger screens, and the full width on smaller screens.
- **Alert**: The alert at the bottom of the dashboard provides an important message to the user.

## Sources 📖
- [Bootstrap Documentation](https://getbootstrap.com/)
- [Bootstrap Components Overview](https://getbootstrap.com/docs/5.3/components/)