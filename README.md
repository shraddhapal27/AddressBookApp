# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC25 – Delete Entry from JSON Server

This branch introduces functionality to **delete an existing contact entry from JSON Server**.

JSON Server acts as a **mock REST API backend** that stores data in a JSON file and exposes it through REST endpoints.  
The Spring Boot application communicates with JSON Server and deletes contact records using an **HTTP DELETE request**.

This feature demonstrates how a Spring Boot application can **remove resources from an external REST service**.

---

# 🛠 Tech Stack

- ☕ Java 17  
- 🌱 Spring Boot  
- 📦 Maven  
- 🔗 REST API  
- 📡 JSON Server  
- 🔌 RestTemplate  

---

# 📂 Project Structure

```
AddressBookApp
│
├── controller
│      AddressBookController.java
│
├── service
│      JSONServerService.java
│
├── model
│      Contact.java
│
└── AddressBookAppApplication.java
```

---

# 🌐 JSON Server Setup

JSON Server provides a fake REST API for testing and development.

### Install JSON Server

```
npm install -g json-server
```

---

### Create JSON Database File

Create a file named:

```
db.json
```

Example content:

```
{
  "contacts": [
    {
      "id": 1,
      "firstName": "Rahul",
      "lastName": "Sharma",
      "city": "Delhi"
    },
    {
      "id": 2,
      "firstName": "Bhumi",
      "lastName": "Shrivas",
      "city": "Bhopal"
    }
  ]
}
```

---

### Start JSON Server

```
json-server --watch db.json --port 3000
```

JSON Server endpoint:

```
http://localhost:3000/contacts
```

---

# 🧠 Implementation

The Spring Boot application sends an **HTTP DELETE request** to remove a contact from JSON Server.

Example logic used in the service layer:

```
RestTemplate restTemplate = new RestTemplate();
restTemplate.delete("http://localhost:3000/contacts/{id}");
```

The specified contact entry is removed from the JSON database.

---

# 🌐 API Endpoint

### Delete Contact from JSON Server

```
DELETE /contacts/jsonserver/delete/{id}
```

This endpoint deletes the contact with the specified ID.

---

# 📥 Example Request

```
DELETE /contacts/jsonserver/delete/1
```

---

# 📤 Example Response

```
Contact deleted successfully from JSON Server
```

---

# 🧪 Testing Using CURL

```
curl -X DELETE http://localhost:8080/contacts/jsonserver/delete/1
```

---

# 🔍 Verify Deletion

Open the JSON Server endpoint in a browser:

```
http://localhost:3000/contacts
```

The contact entry with the specified ID should no longer appear in the list.

---

# 🌿 Git Branch

```
feature/UC25-delete-entry-jsonserver
```

After review, this branch will be merged into:

```
dev
```

---

# 📌 Project Completion

With this branch, the **AddressBookApp project implementation is complete**, covering all use cases from **UC1 to UC25**.

The application now supports:

- Address Book REST APIs
- File operations (CSV, JSON)
- Database integration (MySQL)
- Multithreading
- Integration with external REST APIs (JSON Server)

---
