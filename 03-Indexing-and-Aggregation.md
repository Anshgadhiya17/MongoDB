# ⚡ Indexing & Aggregation in MongoDB

---

# 📌 What is Index?

Index improves query performance.

Without index:
MongoDB scans full collection.

With index:
MongoDB searches faster.

---

# 🏗 Create Index

Single field:

```js
db.users.createIndex({age: 1})
```

1 → Ascending  
-1 → Descending  

---

# 🔗 Compound Index

```js
db.users.createIndex({age: 1, name: -1})
```

---

# ⭐ Unique Index

```js
db.users.createIndex({email: 1}, {unique: true})
```

---

# 📊 Aggregation Pipeline

Used for advanced data processing.

Structure:

```js
db.collection.aggregate([
  { stage1 },
  { stage2 }
])
```

---

# 🔹 $match

Filter documents.

```js
{$match: {age: {$gt: 25}}}
```

---

# 🔹 $group

Group data.

```js
{
  $group: {
    _id: "$age",
    count: {$sum: 1}
  }
}
```

---

# 🔹 $project

Select fields.

```js
{$project: {name: 1, age: 1}}
```

---

# 🔹 $sort

```js
{$sort: {age: -1}}
```

---

# 🔹 $lookup (Join)

```js
{
  $lookup: {
    from: "orders",
    localField: "_id",
    foreignField: "user_id",
    as: "user_orders"
  }
}
```
