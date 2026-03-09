
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC7 – Prevent Duplicate Contact

This branch introduces functionality to **prevent duplicate contacts** from being added to an Address Book.

Previously, the system allowed multiple contacts with the same name to be inserted.  
With UC7 implemented, the application now checks for **duplicate entries before adding a contact**.

A contact is considered **duplicate if the first name and last name match an existing contact** in the same address book.

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

Duplicate checking occurs inside the **Service Layer** before inserting a new contact.

---

# 🚫 Duplicate Prevention Logic

To detect duplicates, the `equals()` and `hashCode()` methods are implemented in the `Contact` class.

Two contacts are considered **equal if**:

```
firstName + lastName are the same
```

Example:

| Contact 1 | Contact 2 | Result |
|-----------|-----------|-------|
| Bhumi Shrivas | Bhumi Shrivas | ❌ Duplicate |
| Bhumi Shrivas | Rahul Sharma | ✅ Allowed |

---

# 🌐 API Endpoints

### 📚 Create Address Book

```
POST /addressbooks?name=Personal
```

Creates a new address book.

---

### ➕ Add Contact

```
POST /addressbooks/{name}/contacts
```

Adds a contact to the specified address book.

If a duplicate contact is detected, the system will return a **duplicate warning message**.

Example:

```
POST /addressbooks/Personal/contacts
```

---

### 👥 Get Contacts

```
GET /addressbooks/{name}/contacts
```

Returns all contacts from the specified address book.

---

### 📋 Get All Address Books

```
GET /addressbooks
```

Returns all address books.

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

Response:

```
Contact added successfully
```

---

### Try Duplicate Contact

```
curl -X POST http://localhost:8080/addressbooks/Personal/contacts -H "Content-Type: application/json" -d "{\"id\":2,\"firstName\":\"Bhumi\",\"lastName\":\"Shrivas\",\"city\":\"Bhopal\"}"
```

Response:

```
Duplicate contact not allowed
```

---

# ▶️ How to Run the Project

### 1️⃣ Clone repository

```
git clone https://github.com/<your-username>/AddressBookApp.git
```

---

### 2️⃣ Navigate to project directory

```
cd AddressBookApp
```

---

### 3️⃣ Run the application

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
feature/UC7-prevent-duplicate-contact
```

This branch implements **Use Case 7 – Prevent Duplicate Contact**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC8 – Search Person by City or State

Next features:

- 🔍 Search contacts by **city**
- 🔍 Search contacts by **state**
- ⚡ Use **Java Streams API**
- 📊 Return matching contacts

---
