# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC15 – Read / Write Address Book Using JSON

This branch introduces functionality to **store and retrieve Address Book contacts using JSON files**.

The implementation uses the **Gson library** to convert Java objects to JSON and vice versa.

---

# 🛠 Technologies

- Java 17
- Spring Boot
- Maven
- Gson Library
- REST API

---

# 📂 Project Structure

```
AddressBookApp
│
├── controller
│      AddressBookController.java
│
├── service
│      AddressBookService.java
│
├── model
│      Contact.java
│      AddressBook.java
│
├── io
│      AddressBookJSONService.java
│
└── AddressBookAppApplication.java
```

---

# 📄 JSON File Example

```
contacts.json
```

Example content:

```
[
 {
  "id":1,
  "firstName":"Bhumi",
  "lastName":"Shrivas",
  "city":"Bhopal",
  "state":"MP"
 }
]
```

---

# 🌐 API Endpoints

### Write JSON File

```
GET /contacts/json/write
```

---

### Read JSON File

```
GET /contacts/json/read
```

---

# 🧪 Testing

Write JSON

```
curl http://localhost:8080/contacts/json/write
```

Read JSON

```
curl http://localhost:8080/contacts/json/read
```

---

# 🌿 Git Branch

```
feature/UC15-read-write-addressbook-json
```

After review this branch will be merged into **dev**.

---

# 📌 Next Implementation

### UC16 – Retrieve Contacts From Database

Next we introduce:

- JDBC
- Database connection
- Storing contacts in DB.

---
