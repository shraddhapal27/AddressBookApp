
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC8 – Search Person by City or State

This branch introduces functionality to **search contacts by city or state across all address books**.

The search feature allows users to retrieve contacts that belong to a specific **city** or **state**, making it easier to locate people based on geographic information.

The implementation uses **Java Streams API** to efficiently filter contacts.

---

# 🛠 Tech Stack

- ☕ Java 17
- 🌱 Spring Boot
- 📦 Maven
- 🔗 REST API
- 🐙 Git & GitHub
- ⚡ Java Streams API

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
Client (CURL / Postman)
        │
        ▼
     Controller
        │
        ▼
      Service
        │
        ▼
Map<String, AddressBook>
        │
        ▼
Java Streams Filtering
```

Contacts from **all address books** are collected and filtered using Streams.

---

# 🔎 Search Logic (Java Streams)

Contacts are retrieved using:

```
addressBooks.values()
        .stream()
        .flatMap(addressBook -> addressBook.getContacts().stream())
```

Then filtered by **city or state**.

---

# 🌐 API Endpoints

### 🔍 Search by City

```
GET /contacts/city/{city}
```

Example:

```
GET /contacts/city/Bhopal
```

---

### 🔍 Search by State

```
GET /contacts/state/{state}
```

Example:

```
GET /contacts/state/MP
```

---

# 🧪 Testing Using CURL

### Search by City

```
curl http://localhost:8080/contacts/city/Bhopal
```

---

### Search by State

```
curl http://localhost:8080/contacts/state/MP
```

Example Response:

```
[
 {
  "id":1,
  "firstName":"Bhumi",
  "city":"Bhopal",
  "state":"MP"
 }
]
```

---

# ▶️ How to Run the Project

### Clone repository

```
git clone https://github.com/<your-username>/AddressBookApp.git
```

### Run project

```
mvn spring-boot:run
```

or run

```
AddressBookAppApplication.java
```

from your IDE.

---

# 🌿 Git Branch

```
feature/UC8-search-person-by-city-or-state
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC9 – View Persons by City or State

Next features:

- Group contacts by **city**
- Group contacts by **state**
- Return **city → list of persons**
- Use **Java Streams grouping**

---
