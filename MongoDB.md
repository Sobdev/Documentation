## Tipos de bases de datos

# SQL
- Relacionales
Son relacionales porque la información se relaciona entre sí mediante el uso de índices, se guarda de manera separada.
- Tablas
- Esquemas
Siempre son fijos y no hay forma de cambiarlos.
￼
￼

# NoSQL
- No relacionales
No tiene por qué tener relación entre sí.
- JavaScript.
El lenguaje es JS
- Orientadas a documentos como JSON, BSON BinarySON
No tenemos tablas, tenemos colecciones de documentos y estos documentos son objetos. En MongoDB directamente pasa de ser JSON a Binario con BSON para rapidez.
- Sencillez, velocidad. La velocidad de consulta es, de verdad, abismalmente más rápida.
- Esquema libre.

￼
Usuarios:
{
	nombre: ‘Adrian’,
	apellido: ’Sobota’,
	email: ‘emal@email.com’
}

￼

1. Tablas -> Colecciones:
    * SQL: Las tablas en bases de datos relacionales organizan los datos en filas y columnas.
    * NoSQL: Las colecciones en MongoDB agrupan documentos similares, pero no tienen un esquema rígido.
2. Esquema -> Sin esquema fijo:
    * SQL: Cada tabla tiene un esquema fijo, que define las columnas y tipos de datos de antemano.
    * NoSQL: Las colecciones pueden contener documentos con diferentes estructuras y tipos de datos.
3. Tablas -> Colecciones (Documentos):
    * SQL: Tablas se utilizan para organizar datos en un formato estructurado.
    * NoSQL: Las colecciones contienen documentos en un formato flexible (como JSON o BSON).
4. Filas -> Documentos:
    * SQL: Las filas representan un registro individual en una tabla.
    * NoSQL: Los documentos representan una unidad de datos similar a una fila, pero pueden tener estructuras anidadas y diferentes tipos de datos.
5. Columnas -> Campos:
    * SQL: Las columnas definen los tipos de datos específicos y los nombres para cada valor en una fila.
    * NoSQL: Los campos en un documento almacenan datos y pueden variar de un documento a otro dentro de la misma colección.
6. Registros -> Documentos:
    * SQL: Un registro es una fila completa en una tabla.
    * NoSQL: Un documento es una estructura de datos completa dentro de una colección, similar a un registro en SQL pero más flexible.
    * 
Comparativa visual:
Concepto SQL	Concepto NoSQL
Tabla	Colección
Esquema	No hay esquema fijo
Filas	Documentos
Columnas	Campos
Registros	Documentos

* Tablas -> Colecciones: Las tablas en SQL son estrictas en términos de esquema y estructura, mientras que las colecciones en NoSQL permiten una estructura más libre, adaptándose a las necesidades cambiantes de la aplicación.
* Esquema -> Sin esquema fijo: En SQL, el esquema es necesario para definir la estructura de los datos antes de su almacenamiento, asegurando consistencia y restricciones de integridad. En NoSQL, la ausencia de un esquema fijo permite una flexibilidad considerable en la forma en que se almacenan los datos, permitiendo que diferentes documentos en una colección tengan diferentes campos y tipos de datos.
* Filas -> Documentos: Las filas en SQL contienen datos estructurados en columnas predefinidas, mientras que los documentos en NoSQL pueden tener estructuras anidadas, arrays y tipos de datos variados.
* Columnas -> Campos: Las columnas en SQL son definidas por el esquema de la tabla y son consistentes para todas las filas. Los campos en NoSQL pueden variar entre documentos dentro de la misma colección, permitiendo una gran flexibilidad en la representación de datos.
* Registros -> Documentos: Los registros en SQL son equivalentes a las filas y contienen datos coherentes con el esquema de la tabla. Los documentos en NoSQL son unidades de datos independientes que pueden incluir datos complejos y anidados.
