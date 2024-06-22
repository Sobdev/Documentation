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
