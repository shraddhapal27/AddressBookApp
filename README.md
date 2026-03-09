
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC9 – View Persons by City or State

This branch introduces functionality to **view all persons grouped by their city or state**.

Unlike UC8 where contacts were searched individually, UC9 allows users to **view a grouped list of contacts based on city or state**.

This feature uses the **Java Streams API with grouping operations**.

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
Java Streams Grouping
```

Contacts are retrieved from all address books and **grouped by city or state**.

---

# 🌐 API Endpoints

### 📍 View Persons by City

```
GET /contacts/view/city
```

Returns contacts grouped by city.

Example Response:

```
{
 "Bhopal": [
   { "firstName": "Bhumi" },
   { "firstName": "Rahul" }
 ],
 "Delhi": [
   { "firstName": "Priya" }
 ]
}
```

---

### 📍 View Persons by State

```
GET /contacts/view/state
```

Returns contacts grouped by state.

Example Response:

```
{
 "MP": [
   { "firstName": "Bhumi" }
 ],
 "Delhi": [
   { "firstName": "Rahul" }
 ]
}
```

---

# 🧪 Testing Using CURL

### View Persons by City

```
curl http://localhost:8080/contacts/view/city
```

---

### View Persons by State

```
curl http://localhost:8080/contacts/view/state
```

---

# ▶️ How to Run the Project

Clone repository:

```
git clone https://github.com/<your-username>/AddressBookApp.git
```

Run application:

```
mvn spring-boot:run
```

or run `AddressBookAppApplication.java` from your IDE.

---

# 🌿 Git Branch

```
feature/UC9-view-persons-by-city-or-state
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC10 – Count Contacts by City or State

Next features:

- Count contacts by **city**
- Count contacts by **state**
- Use **Java Streams counting**

Example output:

```
{
 "Bhopal": 3,
 "Delhi": 2
}
```

---
