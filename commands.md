# 📘 MongoDB Commands

## 1️⃣ Database Commands

### Show All Databases
```js
show dbs
```
➡ Displays all available databases.

### Create / Switch Database
```js
use databaseName
```
➡ Creates (if not exists) and switches to the specified database.

### Show Current Database
```js
db
```
➡ Displays the current active database.

### Drop Database
```js
db.dropDatabase()
```
➡ Deletes the current database permanently.


---

## 2️⃣ Collection Commands

### Show Collections
```js
show collections
```
➡ Lists all collections in the current database.

### Create Collection
```js
db.createCollection("collectionName")
```
➡ Creates a new collection.

### Drop Collection
```js
db.collectionName.drop()
```
➡ Deletes a collection.


---

## 3️⃣ Insert Commands

### Insert One Document
```js
db.collectionName.insertOne({ field: value })
```
➡ Inserts a single document into a collection.

### Insert Multiple Documents
```js
db.collectionName.insertMany([{...}, {...}])
```
➡ Inserts multiple documents at once.


---

## 4️⃣ Read (Find) Commands

### Find All Documents
```js
db.collectionName.find()
```
➡ Retrieves all documents from a collection.

### Pretty Format Output
```js
db.collectionName.find().pretty()
```
➡ Displays formatted JSON output.

### Find One Document
```js
db.collectionName.findOne({ field: value })
```
➡ Retrieves the first matching document.

### Find with Condition
```js
db.collectionName.find({ field: value })
```
➡ Retrieves documents matching the condition.

### Projection (Specific Fields)
```js
db.collectionName.find({}, { field1: 1, field2: 1 })
```
➡ Retrieves only specified fields.


---

## 5️⃣ Update Commands

### Update One Document
```js
db.collectionName.updateOne(
  { condition },
  { $set: { field: newValue } }
)
```
➡ Updates a single matching document.

### Update Multiple Documents
```js
db.collectionName.updateMany(
  { condition },
  { $set: { field: newValue } }
)
```
➡ Updates multiple matching documents.

### Replace Document
```js
db.collectionName.replaceOne(
  { condition },
  { newDocument }
)
```
➡ Replaces the entire document.


---

## 6️⃣ Delete Commands

### Delete One Document
```js
db.collectionName.deleteOne({ condition })
```
➡ Deletes the first matching document.

### Delete Multiple Documents
```js
db.collectionName.deleteMany({ condition })
```
➡ Deletes all matching documents.


---

## 7️⃣ Query Operators

### Comparison Operators
```js
{ field: { $gt: value } }   // Greater than
{ field: { $lt: value } }   // Less than
{ field: { $gte: value } }  // Greater than or equal
{ field: { $lte: value } }  // Less than or equal
{ field: { $ne: value } }   // Not equal
{ field: { $in: [v1, v2] } } // Matches any value in array
```
➡ Used for value comparison.

### Logical Operators
```js
{ $and: [ {cond1}, {cond2} ] }
{ $or: [ {cond1}, {cond2} ] }
{ $not: { condition } }
```
➡ Used to combine multiple conditions.


---

## 8️⃣ Sorting & Limiting

### Sort Documents
```js
db.collectionName.find().sort({ field: 1 })
```
➡ Sorts documents (1 = ascending, -1 = descending).

### Limit Results
```js
db.collectionName.find().limit(5)
```
➡ Limits number of returned documents.

### Skip Documents
```js
db.collectionName.find().skip(5)
```
➡ Skips specified number of documents.


---

## 9️⃣ Aggregation

### Basic Aggregation
```js
db.collectionName.aggregate([
  { $match: { condition } },
  { $group: { _id: "$field", total: { $sum: 1 } } }
])
```
➡ Performs aggregation operations like grouping and counting.


---

## 🔟 Indexing

### Create Index
```js
db.collectionName.createIndex({ field: 1 })
```
➡ Creates an index to improve query performance.

### Show Indexes
```js
db.collectionName.getIndexes()
```
➡ Lists all indexes of a collection.

### Drop Index
```js
db.collectionName.dropIndex("indexName")
```
➡ Deletes a specific index.


---
