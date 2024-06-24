# MongoDB

MongoDB is a NoSQL document-oriented database that allows for the storage and querying of large volumes of data quickly and efficiently. Unlike traditional SQL databases, which organize data in tables and require predefined schemas, MongoDB uses a flexible document model in JSON format (BSON - Binary JSON), allowing for greater flexibility and scalability.

## Types of Databases

### SQL

- **Relational**
  - Information is related to each other through the use of indices and is stored separately.
- **Tables and Schematization** 
  - Always has fixed structures and cannot be easily changed; the structure is planned from the beginning.

### NoSQL

- **Non-relational**
  - Information does not need to have any relationship.
- **JavaScript**
  - The language used is not SQL, it is JavaScript, which is useful if you combine Frontend with Backend, making everything use the same programming language.
- **Document-oriented like JSON, BSON, BinarySON**
  - We don't have tables, we have collections of documents, and these documents are objects. In MongoDB, it directly goes from JSON to Binary with BSON for speed.
- **Simplicity, speed, schema-free, extremely scalable**
  - The query time is measured in milliseconds; it is fast and lightweight.

### Visual Comparison:

| SQL Concept | NoSQL Concept       |
| ----------- | ------------------- |
| Table       | Collection          |
| Schema      | No fixed schema     |
| Rows        | Documents           |
| Columns     | Fields              |
| Records     | Documents           |

![](https://media.cleanshot.cloud/media/38290/NvWyxia2vYtv3cXgLpEdBGIUtCi4EE39Bxdpng7l.jpeg?Expires=1719093293&Signature=K91iKpnOuALhrhB5xuDUW4qKLczD8AQ5TqZ2156tK8gObnbEjr9b0P5UeFA~yZl1oSR~gHYbF3LZZJQ15Ka~6eWItyTuMxz1F7yZ4--l9q5riwqNAQq83WnLAfBZDcnM0jTdeksJFGOGz5qEHaY4yats3YHdnEXistktIDUUiz693XAUEZAiF~oTRVWyuLokNhSWHfeTRfnferUBp~jncdyzSYZCz0Rnu6fCu0X3vtU~CrXaplcGXWEvoL41csBvOOacCDgrXqubdS2-0bJEkS1S9L6DlMbziQwrUauox1SJbvUihFkL431ko7y0R9A86rftgpBLw7m9F3y4MY3jKQ__&Key-Pair-Id=K269JMAT9ZF4GZ)

![](https://media.cleanshot.cloud/media/38290/xjdIozZFn8v0H8KaAoZCWFlTqshzz76oETqyvsma.jpeg?Expires=1719093325&Signature=j98LvO9myFlKnRjEEoz65E3Av9fcrhFyRvEYmfpwts5N9hCCHPdk0U9CnVhzepQZ9ZG7fK8FzR~sunlRVD7ECYFYsmRWBkpvtNQ0fTQaREnWXhqleaLFGAzBcTBrfBrZ02us5oOtT61YTFAeJnVdAx2I7JyeMaNduX2DSjSbaTeDgTW9sN7TfMsSbi6TmEm7fmeU5ODjYCiHe~VAKECMGg952-ukTh2cDScUqsdfFY28huTFCDWfdzLICnQQLxVQhKLqxOn7rWOo~e~yj-3eu4oOrfJJIwSgIkuAMoYcCo1jpuRRVXwVRWbPu~tgwYoEroPdgMSIJSRePUvdLDJlrg__&Key-Pair-Id=K269JMAT9ZF4GZ)

![](https://media.cleanshot.cloud/media/38290/H1CDWApeGgXdnSgQVUY0GpPRiBTntZWXYTvrGsS3.jpeg?Expires=1719093357&Signature=XF~FoWlxfn~BAnnmXjI2u9~cjjelmxyQBw8ZRN3Hs9tl2LTZXR5uYuiSFz8AjLYnNVpdbGVhJSipCiOtCj99btRfqorD39IFRtPA76ce17URRTfKmkSIiEonx-fOE4dTn6wvIDzrL8qk6ci0k7X6j4Q9jGyC5aCYK8pn3OZod6tQ0mg-Sf~jijjsQdaIxS5aZeKLAVH3-MJHLs4yvQZSpdfsm8R80b2RSfruSHMt4b634HMeUB5wxi60qqTHUAqYSr5NkXs9Z8zg9ZszwyePBmUzQFUGM08y7vFpC5vtDoXwjNCyzE~jGo0r3Azs62g9MqjuMBdNGgx5W64cdZMh9A__&Key-Pair-Id=K269JMAT9ZF4GZ)

Example of a document in MongoDB.

```
{
  "nombre": "Adrian",
  "apellido": "Sobota",
  "email": "email@example.com",
  "edad": 28,
  "intereses": ["programación", "diseño gráfico", "marketing"]
}
```

## MongoDB Compass

Is the oficial GUI for MongoDB. Using MongoDB Compass allows us to quickly analyze and understand the contents of our data collections and perform queries, within other cool features, such as a graphical view of our MongoDB schema and data.

### Data types in MongoDB

When we add a new field to a document, we will see a label on the right specifying the **data type** that *values* must have for that *key*. In our previous example, `name` and `lastName` were both Strings.

Our documents can store different type of values. So for example, we can save our `name` as a string, but our `dateOfBirth` as a Date.

These are some of the most useful data types used in mongo documents:

| type             | Examples                             |
| ---------------- | ------------------------------------ |
| Double (Numbers) | 3.141625                             |
| String           | “IronHack Coding Bootcamp”           |
| Date             | “Sun Dec 08 07:15:44 UTC 2013”       |
| Boolean          | true                                 |
| Object           | { foo: ‘bar’, }                      |
| Array            | [“apple”, “oranges”, “kiwis”]        |
| ObjectID         | ObjectId(“52cdef7c4bab8bd675297d8a”) |
| Null             | null                                 |

### ObjectID

`ObjectID` is a MongoDB type used to identify documents in a collection uniquely. MongoDB will create them automatically for us.

In the previous example, when we added the `Elon Musk` document, MongoDB automatically created a key `_id` for the document.

We will use this `_id` key later to identify a particular document in a collection. Even if we introduce two documents with the same information, we can always refer to each document unequivocally using the `_id` property.

The `_id` property is not an integer or a string; it’s aN [ObjectId BSON data type](https://docs.mongodb.com/v3.2/reference/bson-types/#objectid) generated by using MongoDB’s [ObjectId](https://docs.mongodb.com/v3.2/reference/method/ObjectId/) function.

### MongoDB Compass CRUD Operations

**CRUD:**
CRUD operations are essential for working with any database. These operations include:
- **Create:** Adding new data.
- **Read:** Retrieving data.
- **Update:** Modifying existing data.
- **Delete:** Removing data.

**Importing Data:**
MongoDB Compass allows you to import data from JSON or CSV files into your database.

**CRUD Operations:**
- **Create:** Adding new documents to a collection.
- **Read:** Viewing documents in a collection.
- **Update:** Editing existing documents.
- **Delete:** Removing documents from a collection.

**Schema Analysis:**
MongoDB Compass includes a Schema tab for analyzing the structure and data types within your documents.

**Updating Documents:**
You can update fields, delete fields, or add new fields within documents directly in MongoDB Compass.

**Querying Documents:**
You can query for specific documents using MongoDB’s powerful query language. This includes using:
- **Logical operators:** `$and`, `$or`, `$ne`, `$nor`
- **Comparison operators:** `$gt`, `$lt`, `$gte`, `$lte`
- **Array operators:** `$in`, `$nin`, `$all`, `$elemMatch`
- **Element operators:** `$exists`, `$type`

**Projections:**
Projections allow you to specify which fields to include or exclude in the query results, optimizing performance.

**Sorting, Limiting, and Skipping:**
You can sort documents, limit the number of documents returned, and skip documents in your query results for pagination.

**Advanced Queries:**
Construct complex queries by combining various operators to filter and retrieve specific data efficiently.

**Summary:**
This lesson covered essential CRUD operations using MongoDB Compass, importing data, and constructing advanced queries. You learned how to use logical, comparison, array, and element operators to refine your queries and optimize your database interactions.

## Resources
<details>
  <summary>Click to expand the resources</summary>

  - [Mongo CRUD Documentation](https://docs.mongodb.com/manual/crud/)
  - [Query selectors in MongoDB](https://docs.mongodb.com/manual/reference/operator/query/)
  - [Reference Operators](https://docs.mongodb.com/manual/reference/operator/)
  - [Mongo Compass Querying](https://docs.mongodb.com/compass/master/query/)
  - [Query Operators](https://docs.mongodb.com/manual/reference/operator/query/)
  - [Query Operators for Arrays](https://docs.mongodb.com/manual/reference/operator/query-array/)
  - [Query Operators for Elements](https://docs.mongodb.com/manual/reference/operator/query-element/)
  - [Query Operators for Comparison](https://docs.mongodb.com/manual/reference/operator/query-comparison/)
</details>

# MongoDB Data Modeling

## Introduction
One of MongoDB's strengths is its flexible schema, allowing for documents with different structures within the same collection. The standard approach is to group documents with similar structures in the same collection. When designing a database model, it's crucial to consider the data types and how documents and collections will connect.

## Glossary
- **Data Model**: Representation of data elements and their relationships.
- **Normalization**: Organizing data to eliminate duplication, reduce errors, eliminate redundancy, and simplify querying.
- **Normalized Database**: Structured to eliminate data duplication and redundancy, simplifying queries.
- **Schema**: Defines the structure of a database, including fields, data types, relationships, and constraints.

## Data Model
A data model defines how collections and documents are organized and related. Key considerations include document structure and relationships between collections. There are two main approaches:

- **Referencing Documents**: Storing references between documents using identifiers.
- **Embedding Documents**: Storing documents within other documents as nested data.

## Referencing Documents - Relationships
Database relationships are logical links between collections/tables. In MongoDB, relationships use unique document IDs (_id). Relationships can be established using references, similar to foreign keys in SQL. For example:

**Users Collection**:
```json
{
   "_id": ObjectId('593e7a1a4299c306d656200f'),
   "username": "123xyz"
}
```
Contacts Collection:
```
json
{
    "_id": ObjectId('59f30dd86f0b06a96e31bbb9'),
    "user_id": ObjectId('593e7a1a4299c306d656200f'),
    "phone": "123-456-7890",
    "email": "xyz@example.com"
}
```
Accesses Collection:
```
json
{
    "_id": ObjectId('59e1a1c13f0b12a96e31aaa9'),
    "user_id": ObjectId('593e7a1a4299c306d656200f'),
    "level": 5,
    "group": "dev"
}
```

Embedding Documents
Documents can also be related by embedding them. For example:

```
json
{
    "_id": ObjectId('593e7a1a4299c306d656200f'),
    "username": "123xyz",
    "contact": {
        "phone": "123-456-7890",
        "email": "xyz@example.com"
    },
    "access": {
        "level": 5,
        "group": "dev"
    }
}
```

Multiple Sub-documents
To embed multiple documents, use arrays:

```
json
{
    "_id": ObjectId('593e7a1a4299c306d656200f'),
    "username": "123xyz",
    "addresses": [
        {
            "street": "123 Fake Street",
            "city": "Faketon",
            "state": "MA",
            "zip": "12345"
        },
        {
            "street": "1 Some Other Street",
            "city": "Boston",
            "state": "MA",
            "zip": "12345"
        }
    ]
}
```

Model Relationships Between Documents
It's crucial to identify primary use cases and define the necessary information. Properly organizing relationships ensures a tidy database and efficient queries. 
