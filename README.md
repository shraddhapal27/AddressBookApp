# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC10 – Count Contacts by City or State

This branch introduces functionality to **count the number of contacts grouped by city or state**.

Instead of listing contacts, this feature returns the **total number of contacts belonging to each city or state**.

The implementation uses **Java Streams API with grouping and counting collectors**.

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

All contacts across all address books are collected using **Java Streams**, then grouped by city or state and counted.

Example logic:

```
contacts.stream()
        .collect(groupingBy(Contact::getCity, counting()))
```

---

# 🌐 API Endpoints

### 📍 Count Contacts by City

```
GET /contacts/count/city
```

Example Response

```
{
 "Bhopal": 3,
 "Delhi": 2
}
```

---

### 📍 Count Contacts by State

```
GET /contacts/count/state
```

Example Response

```
{
 "MP": 3,
 "Delhi": 2
}
```

---

# 🧪 Testing Using CURL

### Count by City

```
curl http://localhost:8080/contacts/count/city
```

---

### Count by State

```
curl http://localhost:8080/contacts/count/state
```

---

# 🌿 Git Branch

```
feature/UC10-count-contacts-by-city-or-state
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC11 – Sort Contacts by Name

Next features:

- Sort contacts alphabetically by **first name**
- Use **Java Streams sorting**
- Provide sorted API response

---
