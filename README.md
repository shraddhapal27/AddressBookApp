
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC21 – Add Multiple Contacts Using Multithreading

This branch introduces functionality to **add multiple contacts to the MySQL database simultaneously using Java multithreading**.

Instead of inserting contacts one by one, the application creates a **separate thread for each contact insertion**, allowing multiple database operations to run concurrently.

This improves performance when inserting large numbers of contacts.

---

# 🛠 Tech Stack

- ☕ Java 17  
- 🌱 Spring Boot  
- 📦 Maven  
- 🔗 REST API  
- 🐬 MySQL Database  
- 🔌 JDBC  
- 🧵 Java Multithreading  

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
├── db
│      AddressBookDBService.java
│
├── model
│      Contact.java
│      AddressBook.java
│
└── AddressBookAppApplication.java
```

---

# 🧠 Multithreading Implementation

Each contact insertion runs in a separate thread.

Example logic:

```
contacts.forEach(contact -> {
    new Thread(() -> {
        addContact(contact);
    }).start();
});
```

This allows multiple contacts to be inserted into the database at the same time.

---

# 🌐 API Endpoint

### Add Multiple Contacts to Database

```
POST /contacts/db/add-multiple
```

This endpoint accepts a list of contacts and inserts them into the database using multithreading.

---

# 📥 Example Request Body

```
[
 {
  "firstName":"Rahul",
  "lastName":"Sharma",
  "address":"Connaught Place",
  "city":"Delhi",
  "state":"Delhi",
  "zip":"110001",
  "phoneNumber":"8888888888",
  "email":"rahul@email.com"
 },
 {
  "firstName":"Amit",
  "lastName":"Patel",
  "address":"Satellite",
  "city":"Ahmedabad",
  "state":"Gujarat",
  "zip":"380015",
  "phoneNumber":"9998887777",
  "email":"amit@email.com"
 }
]
```

---

# 📤 Example Response

```
Multiple contacts are being added using threads
```

---

# 🧪 Testing Using CURL

```
curl -X POST http://localhost:8080/contacts/db/add-multiple \
-H "Content-Type: application/json" \
-d '[{"firstName":"Rahul","lastName":"Sharma","address":"Connaught","city":"Delhi","state":"Delhi","zip":"110001","phoneNumber":"8888888888","email":"rahul@email.com"},{"firstName":"Amit","lastName":"Patel","address":"Satellite","city":"Ahmedabad","state":"Gujarat","zip":"380015","phoneNumber":"9998887777","email":"amit@email.com"}]'
```

---

# 🔍 Verify in Database

Run the following query in MySQL:

```
SELECT * FROM contacts;
```

You should see multiple records inserted into the table.

---

# 🌿 Git Branch

```
feature/UC21-add-multiple-contacts-multithreading
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC22 – Read Entries From JSON Server

Next features:

- Integrate application with **JSON Server**
- Fetch contact entries from a mock REST API
- Demonstrate external API communication

---
