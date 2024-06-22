# MongoDB

MongoDB is a NoSQL, document-oriented database that allows for the storage and querying of large volumes of data quickly and efficiently. Unlike traditional SQL databases, which organize data in tables and require predefined schemas, MongoDB uses a flexible document model in JSON format (BSON - Binary JSON), providing greater flexibility and scalability.

## Types of Databases

### SQL

- **Relational**
  - Information is related through the use of indexes and stored separately.
- **Tables and Schemas**
  - Always have fixed structures that cannot be changed easily; the structure is planned from the beginning.

### NoSQL

- **Non-relational**
  - Information does not need to have any links.
- **JavaScript**
  - The language used is not SQL but JavaScript, which is useful when combining the front-end with the back-end, ensuring that everything uses the same programming language.
- **Document-oriented like JSON, BSON, BinarySON**
  - Instead of tables, we have collections of documents, and these documents are objects. In MongoDB, data transitions directly from JSON to binary BSON for speed.
- **Simplicity, Speed, Flexible Schema, Extremely Scalable**
  - Query times are measured in milliseconds, making it fast and lightweight.

### Visual Comparison:

| SQL Concept | NoSQL Concept      |
| ----------- | ------------------ |
| Table       | Collection         |
| Schema      | No fixed schema    |
| Rows        | Documents          |
| Columns     | Fields             |
| Records     | Documents          |

### Example of a Document in MongoDB:

```json
{
  "nombre": "Adrian",
  "apellido": "Sobota",
  "email": "email@example.com",
  "edad": 28,
  "intereses": ["programming", "graphic design", "marketing"]
}


![](https://media.cleanshot.cloud/media/38290/NvWyxia2vYtv3cXgLpEdBGIUtCi4EE39Bxdpng7l.jpeg?Expires=1719093293&Signature=K91iKpnOuALhrhB5xuDUW4qKLczD8AQ5TqZ2156tK8gObnbEjr9b0P5UeFA~yZl1oSR~gHYbF3LZZJQ15Ka~6eWItyTuMxz1F7yZ4--l9q5riwqNAQq83WnLAfBZDcnM0jTdeksJFGOGz5qEHaY4yats3YHdnEXistktIDUUiz693XAUEZAiF~oTRVWyuLokNhSWHfeTRfnferUBp~jncdyzSYZCz0Rnu6fCu0X3vtU~CrXaplcGXWEvoL41csBvOOacCDgrXqubdS2-0bJEkS1S9L6DlMbziQwrUauox1SJbvUihFkL431ko7y0R9A86rftgpBLw7m9F3y4MY3jKQ__&Key-Pair-Id=K269JMAT9ZF4GZ)

![](https://media.cleanshot.cloud/media/38290/xjdIozZFn8v0H8KaAoZCWFlTqshzz76oETqyvsma.jpeg?Expires=1719093325&Signature=j98LvO9myFlKnRjEEoz65E3Av9fcrhFyRvEYmfpwts5N9hCCHPdk0U9CnVhzepQZ9ZG7fK8FzR~sunlRVD7ECYFYsmRWBkpvtNQ0fTQaREnWXhqleaLFGAzBcTBrfBrZ02us5oOtT61YTFAeJnVdAx2I7JyeMaNduX2DSjSbaTeDgTW9sN7TfMsSbi6TmEm7fmeU5ODjYCiHe~VAKECMGg952-ukTh2cDScUqsdfFY28huTFCDWfdzLICnQQLxVQhKLqxOn7rWOo~e~yj-3eu4oOrfJJIwSgIkuAMoYcCo1jpuRRVXwVRWbPu~tgwYoEroPdgMSIJSRePUvdLDJlrg__&Key-Pair-Id=K269JMAT9ZF4GZ)

![](https://media.cleanshot.cloud/media/38290/H1CDWApeGgXdnSgQVUY0GpPRiBTntZWXYTvrGsS3.jpeg?Expires=1719093357&Signature=XF~FoWlxfn~BAnnmXjI2u9~cjjelmxyQBw8ZRN3Hs9tl2LTZXR5uYuiSFz8AjLYnNVpdbGVhJSipCiOtCj99btRfqorD39IFRtPA76ce17URRTfKmkSIiEonx-fOE4dTn6wvIDzrL8qk6ci0k7X6j4Q9jGyC5aCYK8pn3OZod6tQ0mg-Sf~jijjsQdaIxS5aZeKLAVH3-MJHLs4yvQZSpdfsm8R80b2RSfruSHMt4b634HMeUB5wxi60qqTHUAqYSr5NkXs9Z8zg9ZszwyePBmUzQFUGM08y7vFpC5vtDoXwjNCyzE~jGo0r3Azs62g9MqjuMBdNGgx5W64cdZMh9A__&Key-Pair-Id=K269JMAT9ZF4GZ)
