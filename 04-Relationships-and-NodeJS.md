# 🔗 Relationships & MongoDB with Node.js

---

# 📌 Types of Relationships

---

## 1️⃣ Embedding

Store related data inside document.

Example:

```js
{
  name: "Amit",
  orders: [
    {product: "Laptop", price: 50000}
  ]
}
```

✔ Fast read  
✖ Large document issue  

---

## 2️⃣ Referencing

Store reference ID.

```js
{
  name: "Amit",
  order_id: ObjectId("12345")
}
```

✔ Scalable  
✖ Needs lookup  

---

# 📊 Relationship Types

- One-to-One
- One-to-Many
- Many-to-Many

---

# 🟢 MongoDB with Node.js

Install:

```bash
npm install mongodb
```

---

# 🔌 Connect to MongoDB

```js
const { MongoClient } = require("mongodb");

const client = new MongoClient("Localhost URI");

async function connect() {
  await client.connect();
  console.log("Connected");
}

connect();
```

---

# 🟢 Using Mongoose (Optional)

Install:

```bash
npm install mongoose
```

---

# 🧱 Create Schema

```js
const mongoose = require("mongoose");

const userSchema = new mongoose.Schema({
  name: String,
  age: Number
});

const User = mongoose.model("User", userSchema);
```

---

# ➕ Insert using Mongoose

```js
User.create({name: "Amit", age: 25});
```

---

# 🔍 Find using Mongoose

```js
User.find({age: {$gt: 20}});
```
