Using `rafc` we made this simple component to list an array of books and then we rendered it in case there is one or more.
```javascript
import React from 'react'

export const MyAdvancedComponent = () => {

    const books = ["Harry Potter", "Game of Thrones", "Lord of the Rings"]

    return (
        <div className="book-list">

            <h1>My booklist</h1>
            {books.length >= 1 ?
                (
                    <ul>
                        {
                            books.map((book, index) => {
                                return <li key={index}>{book}</li>
                            })
                        }
                    </ul>
                )
                : <p>There are no books in the list</p>
            }
        </div>
    )
}
```
### Code Explanation

```jsx
{
    books.map((book, index) => {
        return <li key={index}>{book}</li>
    })
}
```

1. **Opening Curly Brace `{`**:
   - This indicates the start of a JavaScript expression within JSX. In JSX, curly braces `{}` are used to embed JavaScript expressions.

2. **`books.map((book, index) => {`**:
   - `books` is an array that contains a list of book titles.
   - `.map()` is an array method that creates a new array populated with the results of calling a provided function on every element in the calling array.
   - `(book, index) => {` is an arrow function that takes two parameters:
     - `book` The current element being processed in the array.
     - `index` The index of the current element being processed in the array.

3. **`return <li key={index}>{book}</li>`**:
   - This line returns a JSX `<li>` element for each book in the `books` array.
   - `key={index}` The `key` attribute is a special attribute in React that helps identify which items have changed, are added, or are removed. Using the `index` as the key is a common practice when the list items are static and do not change.
   - `{book}`: This is the content of the `<li>` element, which will be the title of the book.

4. **Closing Curly Brace `}`**:
   - This indicates the end of the JavaScript expression within JSX.

### Why `book` and `index`?

- **`book`**:
  - The name `book` is used because it represents each element in the `books` array, which are book titles. This name is descriptive and makes the code more readable.

- **`index`**:
  - The name `index` is used because it represents the position of the current element in the array. This is useful for setting the `key`attribute, which requires a unique identifier for each list item.

The unique key need to be declared in line 15 in case you need to modify it in the future, its mandatory. That's why we use the index of the array as the key.