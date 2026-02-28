# 📘 MongoDB Logical Operators

Logical operators are used to combine multiple query conditions.

---

## 1️⃣ $and

```js
{ $and: [ { condition1 }, { condition2 } ] }
```
➡ Returns documents that satisfy ALL conditions.

Example:
```js
db.users.find({
  $and: [
    { age: { $gt: 18 } },
    { status: "Active" }
  ]
})
```

---

## 2️⃣ $or

```js
{ $or: [ { condition1 }, { condition2 } ] }
```
➡ Returns documents that satisfy ANY one condition.

Example:
```js
db.users.find({
  $or: [
    { role: "Admin" },
    { age: { $lt: 18 } }
  ]
})
```

---

## 3️⃣ $not

```js
{ field: { $not: { operatorExpression } } }
```
➡ Negates a condition.

Example:
```js
db.users.find({
  age: { $not: { $gt: 18 } }
})
```

---

## 4️⃣ $nor

```js
{ $nor: [ { condition1 }, { condition2 } ] }
```
➡ Returns documents that fail ALL conditions.

Example:
```js
db.users.find({
  $nor: [
    { status: "Blocked" },
    { age: { $lt: 18 } }
  ]
})
```

---

# ✅ Summary

| Operator | Meaning |
|----------|---------|
| $and | All conditions must be true |
| $or  | At least one condition must be true |
| $not | Negates a condition |
| $nor | All conditions must be false |

---
