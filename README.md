
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

The project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC22 – Read Entries from JSON Server

This branch introduces functionality to **retrieve contact entries from a JSON Server**.

JSON Server is used as a **mock REST API** that simulates a backend database. The Spring Boot application communicates with this external API using **RestTemplate** and retrieves contact data.

This demonstrates **integration with an external REST service**.

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
│      AddressBook.java
│
└── AddressBookAppApplication.java
```

---

# 🌐 JSON Server Setup

JSON Server provides a fake REST API for testing.

### Install JSON Server

```
npm install -g json-server
```

---

### Create JSON Data File

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

Server URL:

```
http://localhost:3000/contacts
```

---

# 🧠 Implementation

The application fetches contact data from JSON Server using **RestTemplate**.

Example logic:

```
RestTemplate restTemplate = new RestTemplate();
Contact[] contacts = restTemplate.getForObject(JSON_SERVER_URL, Contact[].class);
```

The response is converted into a list of Contact objects.

---

# 🌐 API Endpoint

### Retrieve Contacts from JSON Server

```
GET /contacts/jsonserver
```

This endpoint retrieves all contacts from the external JSON Server.

---

# 📤 Example Response

```
[
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
```

---

# 🧪 Testing Using CURL

```
curl http://localhost:8080/contacts/jsonserver
```

---

# 🌿 Git Branch

```
feature/UC22-read-entries-from-jsonserver
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC23 – Add Entries to JSON Server

Next features:

- Send contact data to JSON Server
- Use **POST request**
- Demonstrate REST API integration with external services

---
