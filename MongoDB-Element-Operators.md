# 📘 MongoDB Element Operators

Element operators are used to match documents based on field existence or BSON type.

---

## 1️⃣ $exists

```js
{ field: { $exists: true } }
```
➡ Matches documents that contain the specified field.

Example:
```js
db.users.find({ phone: { $exists: true } })
```

---

## 2️⃣ $type

```js
{ field: { $type: "string" } }
```
➡ Matches documents where field is of specified BSON type.

Example:
```js
db.users.find({ age: { $type: "int" } })
```

---

# ✅ Summary

| Operator | Meaning |
|----------|---------|
| $exists | Field exists or not |
| $type | Matches BSON data type |

---
