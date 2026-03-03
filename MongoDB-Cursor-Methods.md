# 📘 MongoDB Cursor Methods

Cursor methods are used to modify or process the result set returned by `find()`.

---

## 1️⃣ .limit()

```js
db.collection.find().limit(5)
```
➡ Limits the number of returned documents.

---

## 2️⃣ .skip()

```js
db.collection.find().skip(5)
```
➡ Skips specified number of documents.

---

## 3️⃣ .sort()

```js
db.collection.find().sort({ age: 1 })
```
➡ Sorts documents (1 = ascending, -1 = descending).

---

## 4️⃣ .count()

```js
db.collection.find().count()
```
➡ Returns number of matching documents.

---

## 5️⃣ .pretty()

```js
db.collection.find().pretty()
```
➡ Displays formatted output in shell.

---

## 6️⃣ .forEach()

```js
db.collection.find().forEach(doc => printjson(doc))
```
➡ Iterates through each document.

---

## 7️⃣ .toArray()

```js
db.collection.find().toArray()
```
➡ Converts cursor results into array.

---

# ✅ Summary

| Method | Purpose |
|--------|----------|
| limit() | Limit results |
| skip() | Skip documents |
| sort() | Sort results |
| count() | Count documents |
| pretty() | Format output |
| forEach() | Iterate results |
| toArray() | Convert to array |

---
