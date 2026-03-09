
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC5 – Add Multiple Contacts

This branch implements the ability to **add multiple contacts to the Address Book in a single request**.

Previously, contacts could only be added **one at a time**.  
With UC5, the system now supports **bulk insertion of contacts** using a REST API.

Contacts are stored in a **local in-memory list** and handled through the **Service Layer**.

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
- Maps API endpoints
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

Adds a single contact.

---

### 📦 Add Multiple Contacts

```
POST /contacts/bulk
```

Adds multiple contacts in a single request.

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

Returns the contact matching the given ID.

---

### ✏️ Update Contact

```
PUT /contacts/{id}
```

Updates contact details.

---

### ❌ Delete Contact

```
DELETE /contacts/{id}
```

Deletes the contact with the specified ID.

---

# 🧪 Testing Using CURL

### Add Multiple Contacts

```
curl -X POST http://localhost:8080/contacts/bulk -H "Content-Type: application/json" -d "[{\"id\":2,\"firstName\":\"Rahul\",\"lastName\":\"Sharma\",\"address\":\"Delhi\",\"city\":\"Delhi\",\"state\":\"Delhi\",\"zip\":\"110001\",\"phoneNumber\":\"8888888888\",\"email\":\"rahul@email.com\"},{\"id\":3,\"firstName\":\"Priya\",\"lastName\":\"Patel\",\"address\":\"Ahmedabad\",\"city\":\"Ahmedabad\",\"state\":\"Gujarat\",\"zip\":\"380001\",\"phoneNumber\":\"7777777777\",\"email\":\"priya@email.com\"}]"
```

---

### Get All Contacts

```
curl http://localhost:8080/contacts
```

---

# ▶️ How to Run the Project

### 1️⃣ Clone the repository

```
git clone https://github.com/<your-username>/AddressBookApp.git
```

---

### 2️⃣ Navigate to the project

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
feature/UC5-add-multiple-contacts
```

This branch implements **Use Case 5 – Add Multiple Contacts**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC6 – Multiple Address Books

Next features:

- 📚 Support multiple address books
- 🗂 Store address books using a **Map or Dictionary**
- 👥 Manage contacts per address book

---
