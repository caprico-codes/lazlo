## DOCUMENT UTILITIES

#### All commands related to CRUD operations & more can be found here

#### newdoc / create doc
Creates a new document in the selected database
```sh
lazlo => newdoc doc1
```
```sh
lazlo => create doc doc1
```

#### delete doc / remove doc
Delete a document
```sh
lazlo => delete doc doc1
```
```sh
lazlo => remove doc doc1
```

#### list doc / docs
List all documents in the database
```sh
lazlo => list doc
```
```sh
lazlo => docs
```

#### insert
Insert single record into the document
```sh
lazlo => insert into doc1 '{"name":"joe","age":20}'
```
Remember that the input must be a json string, else a syntactical error will be thrown

#### insert many
Insert multiple records
```sh
lazlo => insert many into doc1 '[{"name":"jim","age":18},{"name":"joe","age":20}]'
```
Remember that the input must be a json string, else a syntactical error will be thrown

#### show all
Display the data in a document
```sh
lazlo => show all from doc1
```

#### where clause 1
Compare single property of a record with a single value. Displays all the records which fulfill the condition.

Operators available:
* = : check for equality
* != : check for inequality
* &gt; : greater than operator
* < : lesser than operator
* &gt;= : greater than or equal to operator
* <= : lesser than or equal to operator

```sh
lazlo => show from doc1 where name = joe
```
```sh
lazlo => show from doc1 where age > 18
```
If the property is not found, an error will be thrown

#### where clause 2
Compare dual properties of a record with dual values using a conjunction. Displays all the records which fulfill the condition.

Operators available:
* = : check for equality
* != : check for inequality
* &gt; : greater than operator
* < : lesser than operator
* &gt;= : greater than or equal to operator
* <= : lesser than or equal to operator

Conjunctions available:
* and
* or

```sh
lazlo => pick from doc1 where name = joe and age >= 18
```
```sh
lazlo => pick from doc1 where name = jim or age < 21
```
If any property is not found, an error will be thrown

#### where clause 3
Compare two properties of a record. Displays all the records which fulfill the condition.

Operators available:
* = : check for equality
* != : check for inequality
* &gt; : greater than operator
* < : lesser than operator
* &gt;= : greater than or equal to operator
* <= : lesser than or equal to operator

Consider this data
```sh
[{name:'tokyo', monday:10, tuesday:12},{name:'mumbai', monday:15, tuesday:15}]
```
Then we can compare properties like:
```sh
lazlo => identify from doc1 where monday = tuesday   //mumbai
```
If any property is not found, an error will be thrown

#### update
In update, you first identify a record using an unique property and value pair and then update it by changing an existing property or by adding a new property and value pair. If the property and value pair used for identification was not unique, lazlo will update all the records having that property-value pair.
```sh
lazlo => update in doc1 where name = joe as name = doe
```
Here the name will be changed to doe

#### delete
In delete, you first identify a record using an unique property and value pair and then delete it. If the property and value pair used for identification was not unique, lazlo will delete all the records having that property-value pair.
```sh
lazlo => delete from doc1 where name = joe
```

#### show records by date
You can also display all the records in a document created on a specific date. The date is passed in a yyyy-mm-dd format.
```sh
lazlo => show records of 2018-12-25 from doc1
```