# Advanced MongoDB Concepts & Performance

Using:
MongoDB
MongoDB Atlas
MongoDB Compass

---

# 1️⃣ Schema Validation

MongoDB is schema-less, but we can enforce structure.

Example:

db.createCollection("users", {
   validator: {
      $jsonSchema: {
         bsonType: "object",
         required: ["name", "email"],
         properties: {
            name: {
               bsonType: "string",
               description: "must be a string"
            },
            age: {
               bsonType: "int",
               minimum: 18
            },
            email: {
               bsonType: "string"
            }
         }
      }
   }
})

---

# 2️⃣ Transactions

Transactions ensure multiple operations succeed or fail together.

Example:

const session = db.getMongo().startSession();
session.startTransaction();

try {
   db.users.insertOne({ name: "Rahul" });
   db.orders.insertOne({ item: "Laptop" });
   session.commitTransaction();
} catch (error) {
   session.abortTransaction();
}

Used in:
- Banking
- E-commerce payments

---

# 3️⃣ Replication (Concept)

Replication = Copy data to multiple servers.

Primary → Secondary nodes

Purpose:
- High Availability
- Backup
- Fault Tolerance

---

# 4️⃣ Sharding (Concept)

Sharding = Split large data into smaller parts across servers.

Used when:
- Data is very large
- High traffic applications

Example:
Social media apps

---

# 5️⃣ Performance Optimization

## Use Index Properly

db.users.createIndex({ email: 1 })

## Use explain()

db.users.find({ age: 25 }).explain("executionStats")

## Avoid Large Documents
## Limit returned fields

db.users.find({}, { name: 1 })

---

# 6️⃣ MongoDB Atlas

Cloud database service.

Features:
- Auto scaling
- Backup
- Monitoring

Connection string example:

mongodb+srv://username:password@cluster.mongodb.net/dbname

---

# 7️⃣ MongoDB Compass

GUI tool to:
- View documents
- Run queries
- Analyze performance

---

# 8️⃣ Security Best Practices

- Enable authentication
- Use strong passwords
- Restrict IP access
- Use HTTPS in production
- Do not expose connection string publicly

---

# Summary

Schema Validation → Data control
Transactions → Data safety
Replication → High availability
Sharding → Scalability
Explain → Query performance check
