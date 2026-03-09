# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC6 – Multiple Address Books

This branch introduces support for **multiple Address Books** in the system.

Previously, the application supported only **one list of contacts**.  
With UC6, the system now allows users to **create and manage multiple address books**, each containing its own contacts.

Each Address Book has a **unique name** and stores a **list of contacts**.

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
│   │      AddressBook.java
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
     Map<String, AddressBook>
```

Each **AddressBook** contains its own list of contacts.

Example structure:

```
AddressBooks
│
├── Personal
│     ├── Contact1
│     └── Contact2
│
├── Work
│     ├── Contact1
│     └── Contact2
```

---

# 📦 Data Structure Used

A **Map** is used to store address books.

```
Map<String, AddressBook>
```

Where:

| Key | Value |
|----|----|
| AddressBook Name | AddressBook Object |

Example:

```
{
 "Personal": AddressBook,
 "Work": AddressBook
}
```

---

# 👤 Contact Model

The `Contact` class represents a person in an Address Book.

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

# 📚 AddressBook Model

The `AddressBook` class represents a collection of contacts.

### Fields

| Field | Description |
|------|-------------|
| name | Name of address book |
| contacts | List of contacts |

---

# 🌐 API Endpoints

### 📚 Create Address Book

```
POST /addressbooks?name=Personal
```

Creates a new address book.

---

### 📋 Get All Address Books

```
GET /addressbooks
```

Returns all address books in the system.

---

### ➕ Add Contact to Address Book

```
POST /addressbooks/{name}/contacts
```

Adds a contact to a specific address book.

Example:

```
POST /addressbooks/Personal/contacts
```

---

### 👥 Get Contacts from Address Book

```
GET /addressbooks/{name}/contacts
```

Returns all contacts from the specified address book.

Example:

```
GET /addressbooks/Personal/contacts
```

---

# 🧪 Testing Using CURL

### Create Address Book

```
curl -X POST "http://localhost:8080/addressbooks?name=Personal"
```

---

### Add Contact

```
curl -X POST http://localhost:8080/addressbooks/Personal/contacts -H "Content-Type: application/json" -d "{\"id\":1,\"firstName\":\"Bhumi\",\"lastName\":\"Shrivas\",\"city\":\"Bhopal\"}"
```

---

### Get Contacts

```
curl http://localhost:8080/addressbooks/Personal/contacts
```

---

# ▶️ How to Run the Project

### 1️⃣ Clone repository

```
git clone https://github.com/<your-username>/AddressBookApp.git
```

---

### 2️⃣ Navigate to project

```
cd AddressBookApp
```

---

### 3️⃣ Run application

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
http://localhost:8080/addressbooks
```

---

# 🌿 Git Branch

```
feature/UC6-multiple-addressbooks
```

This branch implements **Use Case 6 – Multiple Address Books**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC7 – Prevent Duplicate Contact

Next features:

- 🚫 Prevent duplicate contacts in an address book
- 🔍 Search contact before insertion
- 🧩 Implement `equals()` method
- ⚡ Use **Java Streams**

---
