# 📘 MongoDB Aggregation Operators (Complete List)

MongoDB aggregation operators are used inside the `aggregate()` pipeline to process and transform data.

---

# 1️⃣ Pipeline Stage Operators

### $match
```js
{ $match: { condition } }
```
➡ Filters documents (like find).

### $group
```js
{ $group: { _id: "$field", total: { $sum: 1 } } }
```
➡ Groups documents by field.

### $project
```js
{ $project: { field: 1, newField: { $add: ["$a", "$b"] } } }
```
➡ Selects or transforms fields.

### $sort
```js
{ $sort: { field: 1 } }
```
➡ Sorts documents.

### $limit
```js
{ $limit: 5 }
```
➡ Limits result count.

### $skip
```js
{ $skip: 5 }
```
➡ Skips documents.

### $unwind
```js
{ $unwind: "$arrayField" }
```
➡ Deconstructs array into multiple documents.

### $lookup
```js
{
  $lookup: {
    from: "otherCollection",
    localField: "field",
    foreignField: "field",
    as: "result"
  }
}
```
➡ Performs left outer join.

### $addFields
```js
{ $addFields: { newField: value } }
```
➡ Adds new fields.

### $set
```js
{ $set: { field: value } }
```
➡ Alias of $addFields.

### $unset
```js
{ $unset: "field" }
```
➡ Removes field.

### $count
```js
{ $count: "totalDocs" }
```
➡ Counts documents.

### $facet
```js
{ $facet: { output1: [stage1], output2: [stage2] } }
```
➡ Runs multiple pipelines in parallel.

### $bucket
```js
{
  $bucket: {
    groupBy: "$field",
    boundaries: [0, 10, 20],
    default: "Other"
  }
}
```
➡ Groups documents into ranges.

### $bucketAuto
```js
{ $bucketAuto: { groupBy: "$field", buckets: 5 } }
```
➡ Automatically creates buckets.

### $replaceRoot
```js
{ $replaceRoot: { newRoot: "$field" } }
```
➡ Replaces document root.

### $merge
```js
{ $merge: "collectionName" }
```
➡ Writes results to collection.

### $out
```js
{ $out: "collectionName" }
```
➡ Outputs pipeline result to collection.

---

# 2️⃣ Accumulator Operators (Used in $group)

### $sum
```js
{ total: { $sum: "$field" } }
```
➡ Calculates total sum.

### $avg
```js
{ avgValue: { $avg: "$field" } }
```
➡ Calculates average.

### $min
```js
{ minValue: { $min: "$field" } }
```
➡ Finds minimum value.

### $max
```js
{ maxValue: { $max: "$field" } }
```
➡ Finds maximum value.

### $push
```js
{ allValues: { $push: "$field" } }
```
➡ Adds values to array.

### $addToSet
```js
{ uniqueValues: { $addToSet: "$field" } }
```
➡ Adds unique values to array.

### $first
```js
{ firstValue: { $first: "$field" } }
```
➡ Returns first document value.

### $last
```js
{ lastValue: { $last: "$field" } }
```
➡ Returns last document value.

### $count (Accumulator)
```js
{ totalDocs: { $count: {} } }
```
➡ Counts grouped documents.

---

# 3️⃣ Expression Operators

## Arithmetic Operators
```js
{ $add: ["$a", "$b"] }
{ $subtract: ["$a", "$b"] }
{ $multiply: ["$a", "$b"] }
{ $divide: ["$a", "$b"] }
{ $mod: ["$a", "$b"] }
```
➡ Perform mathematical operations.

## Comparison Operators
```js
{ $eq: ["$a", "$b"] }
{ $ne: ["$a", "$b"] }
{ $gt: ["$a", "$b"] }
{ $gte: ["$a", "$b"] }
{ $lt: ["$a", "$b"] }
{ $lte: ["$a", "$b"] }
```
➡ Compare values.

## Logical Operators
```js
{ $and: [expression1, expression2] }
{ $or: [expression1, expression2] }
{ $not: [expression] }
```
➡ Logical conditions.

## String Operators
```js
{ $concat: ["$first", " ", "$last"] }
{ $toUpper: "$field" }
{ $toLower: "$field" }
{ $substr: ["$field", 0, 5] }
{ $strLenCP: "$field" }
```
➡ String manipulation.

## Array Operators
```js
{ $size: "$array" }
{ $arrayElemAt: ["$array", 0] }
{ $in: ["value", "$array"] }
{ $filter: { input: "$array", as: "item", cond: {} } }
{ $map: { input: "$array", as: "item", in: {} } }
```
➡ Array processing.

## Date Operators
```js
{ $year: "$date" }
{ $month: "$date" }
{ $dayOfMonth: "$date" }
{ $hour: "$date" }
{ $minute: "$date" }
{ $second: "$date" }
```
➡ Extract date parts.

## Conditional Operators
```js
{ $cond: { if: {}, then: "", else: "" } }
{ $ifNull: ["$field", "default"] }
{ $switch: { branches: [], default: "" } }
```
➡ Conditional logic.

---

# 4️⃣ Text & Search Operators

### $regexMatch
```js
{ $regexMatch: { input: "$field", regex: /pattern/ } }
```
➡ Matches regex pattern.

---
