### Hover, Focus, and Other States

![TailwindCSS Logo](https://tailwindcss.com/_next/static/media/social-card-large.fcc2850f.jpg)

[TailwindCSS Documentation](https://tailwindcss.com/docs)

## Index
1. [What are State Variants?](#what-are-state-variants)
2. [Hover and Focus States](#hover-and-focus-states)
3. [Active and Disabled States](#active-and-disabled-states)
4. [Custom States with Arbitrary Variants](#custom-states-with-arbitrary-variants)
5. [Example: Interactive Button with Multiple States](#example-interactive-button-with-multiple-states)

## What are State Variants?

In TailwindCSS, state variants allow you to conditionally apply styles based on different states of an element, such as hover, focus, active, and disabled states. Tailwind makes it easy to style elements based on these states using prefix variants like `hover:`, `focus:`, and more.

### Example

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Hover me
</button>
```

In this example, when the user hovers over the button, the background color changes from `bg-blue-500` to `bg-blue-700`.

## Hover and Focus States

### Hover

The `hover:` variant applies styles when an element is hovered over by the mouse pointer.

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Hover Button
</button>
```

### Focus

The `focus:` variant applies styles when an element is focused, such as when a user clicks on an input or navigates to it using the keyboard.

```html
<input class="border border-gray-300 focus:border-blue-500 p-2" type="text" placeholder="Focus on me">
```

In this example, the input field’s border changes to blue when it is focused.

## Active and Disabled States

### Active

The `active:` variant applies styles when an element is in an active state, such as when a button is being clicked.

```html
<button class="bg-blue-500 active:bg-blue-800 text-white font-bold py-2 px-4 rounded">
  Active Button
</button>
```

In this example, the button changes to a darker blue (`bg-blue-800`) while it is being pressed.

### Disabled

The `disabled:` variant applies styles when an element is disabled. This is useful for buttons or form elements that should have different styling when they are not interactable.

```html
<button class="bg-blue-500 text-white font-bold py-2 px-4 rounded disabled:bg-gray-400" disabled>
  Disabled Button
</button>
```

Here, the button changes to a gray background when disabled.

## Custom States with Arbitrary Variants

Tailwind also allows you to create custom state variants using arbitrary values. For example, you can apply styles based on custom focus or hover conditions that are not predefined.

### Example

```html
<button class="bg-blue-500 hover:bg-red-500 focus:bg-green-500 text-white font-bold py-2 px-4 rounded">
  Hover or Focus Button
</button>
```

In this example, the button changes to red when hovered and green when focused.

## Example: Interactive Button with Multiple States

Let's create an interactive button that uses hover, focus, active, and disabled states.

```html
<button class="bg-blue-500 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-50 active:bg-blue-900 text-white font-bold py-2 px-4 rounded disabled:bg-gray-400" disabled>
  Interactive Button
</button>
```

### Explanation

- **Hover State**: When hovered, the button’s background changes to `bg-blue-700`.
- **Focus State**: When focused, the button shows an outline (`focus:outline-none`) and a blue ring effect (`focus:ring-2 focus:ring-blue-400`).
- **Active State**: When the button is clicked or held down, the background changes to a darker blue (`bg-blue-900`).
- **Disabled State**: When disabled, the button has a gray background (`bg-gray-400`) and cannot be interacted with.

## Sources 📖
- [TailwindCSS Documentation](https://tailwindcss.com/docs)
- [State Variants in Tailwind](https://tailwindcss.com/docs/hover-focus-and-other-states)