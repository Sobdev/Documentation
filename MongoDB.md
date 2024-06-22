# MongoDB

MongoDB es una base de datos NoSQL orientada a documentos que permite almacenar y consultar grandes volúmenes de datos de manera rápida y eficiente. A diferencia de las bases de datos SQL tradicionales, que organizan los datos en tablas y requieren esquemas predefinidos, MongoDB utiliza un modelo flexible de documentos en formato JSON (BSON - Binary JSON), lo que permite una mayor flexibilidad y escalabilidad.

## Tipos de bases de datos
### SQL

- **Relacional**
  - La información se relacióna entre sí mediante el uso de índices, se guarda de manera separada.
- **Tablas y esquematización** 
  - Siempre cuenta con estructuras fijas y no hay forma de cambiarlas de forma sencilla, la estructura se planifica desde el principio.

### NOSQL

- **No relacional**
  - La información no tiene por qué tener vinculo alguno.
- **JavaScript**
  - El lenguaje utilizado no es SQL, es JavaScript, lo cual es útil si combinas el Front con el Backend de forma de todo use el mismo lenguaje de programación.
- **Orientadas a documentos como JSON, BSON, BinarySON**
  - No tenemos tablas, tenemos colecciones de documentos y estos documentos son objetos. En MongoDB directamente pasa de ser JSON a Binario con BSON para rapidez.
- **Sencillez, velocidad, esquema libre, extremadamente escalable**
  - El tiempo de consulta se mide en milesimas de segundo, es rápido y ligero.

### Comparativa visual:

| Concepto SQL | Concepto NoSQL      |
| ------------ | ------------------- |
| Tabla        | Colección           |
| Esquema      | No hay esquema fijo |
| Filas        | Documentos          |
| Columnas     | Campos              |
| Registros    | Documentos          |

![](https://media.cleanshot.cloud/media/38290/NvWyxia2vYtv3cXgLpEdBGIUtCi4EE39Bxdpng7l.jpeg?Expires=1719093293&Signature=K91iKpnOuALhrhB5xuDUW4qKLczD8AQ5TqZ2156tK8gObnbEjr9b0P5UeFA~yZl1oSR~gHYbF3LZZJQ15Ka~6eWItyTuMxz1F7yZ4--l9q5riwqNAQq83WnLAfBZDcnM0jTdeksJFGOGz5qEHaY4yats3YHdnEXistktIDUUiz693XAUEZAiF~oTRVWyuLokNhSWHfeTRfnferUBp~jncdyzSYZCz0Rnu6fCu0X3vtU~CrXaplcGXWEvoL41csBvOOacCDgrXqubdS2-0bJEkS1S9L6DlMbziQwrUauox1SJbvUihFkL431ko7y0R9A86rftgpBLw7m9F3y4MY3jKQ__&Key-Pair-Id=K269JMAT9ZF4GZ)

![](https://media.cleanshot.cloud/media/38290/xjdIozZFn8v0H8KaAoZCWFlTqshzz76oETqyvsma.jpeg?Expires=1719093325&Signature=j98LvO9myFlKnRjEEoz65E3Av9fcrhFyRvEYmfpwts5N9hCCHPdk0U9CnVhzepQZ9ZG7fK8FzR~sunlRVD7ECYFYsmRWBkpvtNQ0fTQaREnWXhqleaLFGAzBcTBrfBrZ02us5oOtT61YTFAeJnVdAx2I7JyeMaNduX2DSjSbaTeDgTW9sN7TfMsSbi6TmEm7fmeU5ODjYCiHe~VAKECMGg952-ukTh2cDScUqsdfFY28huTFCDWfdzLICnQQLxVQhKLqxOn7rWOo~e~yj-3eu4oOrfJJIwSgIkuAMoYcCo1jpuRRVXwVRWbPu~tgwYoEroPdgMSIJSRePUvdLDJlrg__&Key-Pair-Id=K269JMAT9ZF4GZ)

![](https://media.cleanshot.cloud/media/38290/H1CDWApeGgXdnSgQVUY0GpPRiBTntZWXYTvrGsS3.jpeg?Expires=1719093357&Signature=XF~FoWlxfn~BAnnmXjI2u9~cjjelmxyQBw8ZRN3Hs9tl2LTZXR5uYuiSFz8AjLYnNVpdbGVhJSipCiOtCj99btRfqorD39IFRtPA76ce17URRTfKmkSIiEonx-fOE4dTn6wvIDzrL8qk6ci0k7X6j4Q9jGyC5aCYK8pn3OZod6tQ0mg-Sf~jijjsQdaIxS5aZeKLAVH3-MJHLs4yvQZSpdfsm8R80b2RSfruSHMt4b634HMeUB5wxi60qqTHUAqYSr5NkXs9Z8zg9ZszwyePBmUzQFUGM08y7vFpC5vtDoXwjNCyzE~jGo0r3Azs62g9MqjuMBdNGgx5W64cdZMh9A__&Key-Pair-Id=K269JMAT9ZF4GZ)

Ejemplo de documento en MongoDB.

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

Es la GUI oficial para MongoDB. Using MongoDB Compass allows us to quickly analyze and understand the contents of our data collections and perform queries, within other cool features, such as a graphical view of our MongoDB schema and data.

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

**Resources:**
- [MongoDB CRUD Documentation](https://docs.mongodb.com/manual/crud/)
- [MongoDB Query Selectors](https://docs.mongodb.com/manual/reference/operator/query/)
- [MongoDB Compass Querying](https://docs.mongodb.com/compass/master/query/)
- [Query Operators for Arrays](https://docs.mongodb.com/manual/reference/operator/query-array/)
- [Query Operators for Elements](https://docs.mongodb.com/manual/reference/operator/query-element/)
- [Query Operators for Comparison](https://docs.mongodb.com/manual/reference/operator/query-comparison/)

