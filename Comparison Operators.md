# 📘 MongoDB Comparison Operators

Comparison operators are used to compare values in queries and aggregation pipelines.

---

## 1️⃣ $eq (Equal)

```js
{ field: { $eq: value } }
```
➡ Matches documents where field value equals the specified value.

Example:
```js
db.users.find({ age: { $eq: 25 } })
```

---

## 2️⃣ $ne (Not Equal)

```js
{ field: { $ne: value } }
```
➡ Matches documents where field value is not equal to the specified value.

Example:
```js
db.users.find({ age: { $ne: 25 } })
```

---

## 3️⃣ $gt (Greater Than)

```js
{ field: { $gt: value } }
```
➡ Matches documents where field value is greater than the specified value.

Example:
```js
db.users.find({ age: { $gt: 18 } })
```

---

## 4️⃣ $gte (Greater Than or Equal)

```js
{ field: { $gte: value } }
```
➡ Matches documents where field value is greater than or equal to the specified value.

Example:
```js
db.users.find({ age: { $gte: 18 } })
```

---

## 5️⃣ $lt (Less Than)

```js
{ field: { $lt: value } }
```
➡ Matches documents where field value is less than the specified value.

Example:
```js
db.users.find({ age: { $lt: 60 } })
```

---

## 6️⃣ $lte (Less Than or Equal)

```js
{ field: { $lte: value } }
```
➡ Matches documents where field value is less than or equal to the specified value.

Example:
```js
db.users.find({ age: { $lte: 60 } })
```

---

## 7️⃣ $in (Matches Any Value in Array)

```js
{ field: { $in: [value1, value2] } }
```
➡ Matches documents where field value equals any value in the array.

Example:
```js
db.users.find({ status: { $in: ["Active", "Pending"] } })
```

---

## 8️⃣ $nin (Not In Array)

```js
{ field: { $nin: [value1, value2] } }
```
➡ Matches documents where field value is not in the specified array.

Example:
```js
db.users.find({ status: { $nin: ["Inactive", "Blocked"] } })
```

---

# ✅ Summary Table

| Operator | Meaning |
|----------|---------|
| $eq  | Equal |
| $ne  | Not Equal |
| $gt  | Greater Than |
| $gte | Greater Than or Equal |
| $lt  | Less Than |
| $lte | Less Than or Equal |
| $in  | Match any value in array |
| $nin | Not in array |

---

# 📌 Used In:
- `find()` queries
- `update()` conditions
- Aggregation `$match`
- Aggregation expressions

---
