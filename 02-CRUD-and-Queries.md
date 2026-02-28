# 📂 MongoDB CRUD & Query Basics

---

# 🏗 Database & Collection

Show databases:

```js
show dbs
```

Create database:

```js
use mydb
```

Create collection automatically on insert.

---

# ➕ INSERT

Insert one:

```js
db.users.insertOne({name: "Amit", age: 25})
```

Insert many:

```js
db.users.insertMany([
  {name: "Rahul", age: 30},
  {name: "Priya", age: 22}
])
```

---

# 🔍 FIND

Find all:

```js
db.users.find()
```

Find with condition:

```js
db.users.find({age: 25})
```

Pretty format:

```js
db.users.find().pretty()
```

---

# ✏ UPDATE

Update one:

```js
db.users.updateOne(
  {name: "Amit"},
  {$set: {age: 26}}
)
```

Update many:

```js
db.users.updateMany(
  {age: {$gt: 25}},
  {$set: {status: "Senior"}}
)
```

---

# ❌ DELETE

Delete one:

```js
db.users.deleteOne({name: "Rahul"})
```

Delete many:

```js
db.users.deleteMany({age: {$lt: 20}})
```

---

# 🔎 Query Operators

## Comparison

```js
{$gt: 20}
{$lt: 30}
{$gte: 25}
{$lte: 40}
{$in: [20,25]}
```

Example:

```js
db.users.find({age: {$gt: 25}})
```

---

## Logical Operators

```js
{$and: [...]}
{$or: [...]}
{$not: {...}}
```

Example:

```js
db.users.find({
  $or: [{age: 25}, {name: "Amit"}]
})
```
