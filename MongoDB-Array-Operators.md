# 📘 MongoDB Array Operators

Array operators are used to query and manipulate array-type fields.

---

## 1️⃣ $all

```js
{ field: { $all: [value1, value2] } }
```
➡ Matches documents where array contains ALL specified values.

Example:
```js
db.users.find({
  skills: { $all: ["MongoDB", "NodeJS"] }
})
```

---

## 2️⃣ $elemMatch

```js
{ field: { $elemMatch: { condition } } }
```
➡ Matches documents where at least one array element satisfies multiple conditions.

Example:
```js
db.users.find({
  marks: {
    $elemMatch: { $gt: 70, $lt: 90 }
  }
})
```

---

## 3️⃣ $size

```js
{ field: { $size: number } }
```
➡ Matches arrays with exact specified length.

Example:
```js
db.users.find({
  skills: { $size: 3 }
})
```

---

## 4️⃣ $in (Array Matching)

```js
{ field: { $in: [value1, value2] } }
```
➡ Matches if any array element equals one of the values.

Example:
```js
db.users.find({
  skills: { $in: ["React"] }
})
```

---

## 5️⃣ $nin

```js
{ field: { $nin: [value1, value2] } }
```
➡ Matches if array elements do NOT contain specified values.

Example:
```js
db.users.find({
  skills: { $nin: ["PHP"] }
})
```

---

# ✅ Summary

| Operator | Meaning |
|----------|---------|
| $all | Array must contain all values |
| $elemMatch | At least one element matches condition |
| $size | Exact array length |
| $in | Matches any value |
| $nin | Does not match values |

---
