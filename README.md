# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC4 – Delete Contact

This branch implements the ability to **delete an existing contact from the Address Book**.

The application now supports:
- ➕ Adding contacts
- 📋 Viewing all contacts
- 🔍 Retrieving contact by ID
- ✏️ Updating contact
- ❌ Deleting contact by ID

Contacts are stored in a **local in-memory list** and managed through a **Service Layer**.

---

# 🛠 Tech Stack

- ☕ Java 17  
- 🌱 Spring Boot  
- 📦 Maven  
- 🔗 REST API  
- 🐙 Git & GitHub  

---

# 📂 Project Structure

```
AddressBookApp
│
├── src/main/java/com/addressbookapp
│
│   ├── controller
│   │      AddressBookController.java
│   │
│   ├── service
│   │      AddressBookService.java
│   │
│   ├── model
│   │      Contact.java
│   │
│   └── AddressBookAppApplication.java
│
├── src/main/resources
│      application.properties
│
└── pom.xml
```

---

# 🧠 Architecture

```
Client (CURL / Postman / Browser)
            │
            ▼
        Controller
            │
            ▼
         Service
            │
            ▼
     Local List Storage
```

### Responsibilities

**Controller**
- Handles HTTP requests
- Maps API endpoints to methods
- Communicates with service layer

**Service**
- Contains business logic
- Performs CRUD operations on contacts

**Model**
- Defines the Contact data structure

---

# 👤 Contact Model

The `Contact` class represents a person in the Address Book.

### Fields

| Field | Description |
|------|-------------|
| id | Unique identifier |
| firstName | Person's first name |
| lastName | Person's last name |
| address | Street address |
| city | City |
| state | State |
| zip | Postal code |
| phoneNumber | Contact number |
| email | Email address |

---

# 🌐 API Endpoints

### ➕ Add Contact

```
POST /contacts
```

Adds a new contact.

---

### 📋 Get All Contacts

```
GET /contacts
```

Returns all contacts stored in memory.

---

### 🔍 Get Contact by ID

```
GET /contacts/{id}
```

Returns contact matching the given ID.

Example:

```
GET /contacts/1
```

---

### ✏️ Update Contact

```
PUT /contacts/{id}
```

Updates contact information.

Example:

```
PUT /contacts/1
```

---

### ❌ Delete Contact

```
DELETE /contacts/{id}
```

Deletes the contact with the specified ID.

Example:

```
DELETE /contacts/1
```

---

# 🧪 Testing Using CURL

### Add Contact

```
curl -X POST http://localhost:8080/contacts -H "Content-Type: application/json" -d "{\"id\":1,\"firstName\":\"Bhumi\",\"lastName\":\"Shrivas\",\"address\":\"MP Nagar\",\"city\":\"Bhopal\",\"state\":\"MP\",\"zip\":\"462001\",\"phoneNumber\":\"9876543210\",\"email\":\"bhumi@email.com\"}"
```

---

### Get Contact by ID

```
curl http://localhost:8080/contacts/1
```

---

### Update Contact

```
curl -X PUT http://localhost:8080/contacts/1 -H "Content-Type: application/json" -d "{\"id\":1,\"firstName\":\"Bhumi\",\"lastName\":\"Updated\",\"address\":\"Bhopal\",\"city\":\"Bhopal\",\"state\":\"MP\",\"zip\":\"462001\",\"phoneNumber\":\"9999999999\",\"email\":\"bhumi@email.com\"}"
```

---

### Delete Contact

```
curl -X DELETE http://localhost:8080/contacts/1
```

---

# ▶️ How to Run the Project

### 1️⃣ Clone the repository

```
git clone https://github.com/<your-username>/AddressBookApp.git
```

---

### 2️⃣ Navigate to project directory

```
cd AddressBookApp
```

---

### 3️⃣ Run the Spring Boot application

```
mvn spring-boot:run
```

or run

```
AddressBookAppApplication.java
```

from your IDE.

---

### 4️⃣ Access APIs

```
http://localhost:8080/contacts
```

---

# 🌿 Git Branch

```
feature/UC4-delete-contact
```

This branch implements **Use Case 4 – Delete Contact**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC5 – Add Multiple Contacts

Next features:

- ➕ Add multiple contacts
- 📚 Manage multiple entries efficiently
- Improve collection handling

---
