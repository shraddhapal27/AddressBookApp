
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where every **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC2 – Add Contact Using Service Layer

This branch implements the ability to **add a new contact to the Address Book using a REST API**.

The contacts are stored in a **local in-memory list** and accessed through a **Service Layer**, following the **Controller → Service → Model architecture**.

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
- Calls service methods
- Returns API responses

**Service**
- Contains business logic
- Manages contact list

**Model**
- Represents Contact data structure

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

Adds a new contact to the address book.

---

### 📋 Get All Contacts

```
GET /contacts
```

Returns the list of all contacts stored in memory.

---

# 🧪 Testing Using CURL

### Add Contact

```
curl -X POST http://localhost:8080/contacts -H "Content-Type: application/json" -d "{\"id\":1,\"firstName\":\"Bhumi\",\"lastName\":\"Shrivas\",\"address\":\"MP Nagar\",\"city\":\"Bhopal\",\"state\":\"MP\",\"zip\":\"462001\",\"phoneNumber\":\"9876543210\",\"email\":\"bhumi@email.com\"}"
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

### 2️⃣ Navigate to project folder

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

### 4️⃣ Access the API

```
http://localhost:8080/contacts
```

---

# 🌿 Git Branch

```
feature/UC2-add-contact
```

This branch implements **Use Case 2 – Add Contact**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC3 – Edit Contact

Next features to be implemented:

- ✏️ Update contact using **PUT API**
- 🔍 Get contact by **ID**
- ❌ Delete contact

---
