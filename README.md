
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

The project is implemented using a **Git Feature Branch Workflow**, where each use case is developed in a separate branch and merged into the `dev` branch.

---

# 🚀 UC12 – Sort Contacts by City, State, and Zip

This branch adds functionality to **sort contacts based on geographic attributes**.

Contacts can now be sorted by:

- City
- State
- Zip Code

Sorting is implemented using the **Java Streams API with Comparator**.

---

# 🛠 Tech Stack

- Java 17
- Spring Boot
- Maven
- REST API
- Git & GitHub
- Java Streams API

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
└── AddressBookAppApplication.java
```

---

# 🧠 Implementation

Contacts from all address books are collected and sorted using:

```
Comparator.comparing(Contact::getCity)
Comparator.comparing(Contact::getState)
Comparator.comparing(Contact::getZip)
```

Sorting is performed using **Java Streams**.

---

# 🌐 API Endpoints

### Sort Contacts by City

```
GET /contacts/sort/city
```

---

### Sort Contacts by State

```
GET /contacts/sort/state
```

---

### Sort Contacts by Zip

```
GET /contacts/sort/zip
```

---

# 🧪 Testing Using CURL

```
curl http://localhost:8080/contacts/sort/city
```

```
curl http://localhost:8080/contacts/sort/state
```

```
curl http://localhost:8080/contacts/sort/zip
```

---

# 🌿 Git Branch

```
feature/UC12-sort-contacts-by-city-state-zip
```

This branch implements **Use Case 12 – Sorting Contacts by Location Fields**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC13 – Read / Write Address Book Using File IO

Next features include:

- Writing address book contacts to file
- Reading contacts from file
- Using Java File IO

---
