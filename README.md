# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC11 – Sort Contacts by Name

This branch introduces functionality to **sort contacts alphabetically by name**.

The sorting operation retrieves all contacts across all address books and returns them sorted by **first name**.

The implementation uses **Java Streams API with Comparator sorting**.

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

# 🧠 Implementation Logic

All contacts across all address books are collected and sorted using Java Streams:

```
contacts.stream()
        .sorted(Comparator.comparing(Contact::getFirstName))
```

This sorts contacts alphabetically by **first name**.

---

# 🌐 API Endpoint

### 🔤 Sort Contacts by Name

```
GET /contacts/sort/name
```

Example Response

```
[
 { "firstName":"Amit" },
 { "firstName":"Bhumi" },
 { "firstName":"Rahul" }
]
```

---

# 🧪 Testing Using CURL

```
curl http://localhost:8080/contacts/sort/name
```

---

# 🌿 Git Branch

```
feature/UC11-sort-contacts-by-name
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC12 – Sort Contacts by City, State, or Zip

Next features:

- Sort contacts by **city**
- Sort contacts by **state**
- Sort contacts by **zip code**
- Implement sorting using **Java Streams Comparator**

---
