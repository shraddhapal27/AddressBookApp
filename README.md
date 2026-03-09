# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC24 – Update Entry in JSON Server

This branch introduces functionality to **update an existing contact entry stored in JSON Server**.

JSON Server acts as a **mock REST API backend** that stores data in a JSON file and exposes it through REST endpoints.  
The Spring Boot application communicates with this server and updates contact data using an **HTTP PUT request**.

This demonstrates how a Spring Boot application can **modify data in an external REST service**.

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
    }
  ]
}
```

---

### Start JSON Server

```
json-server --watch db.json --port 3000
```

Server endpoint:

```
http://localhost:3000/contacts
```

---

# 🧠 Implementation

The Spring Boot application sends an **HTTP PUT request** to update a specific contact in JSON Server.

Example logic:

```
RestTemplate restTemplate = new RestTemplate();
restTemplate.put("http://localhost:3000/contacts/{id}", contact);
```

The existing contact entry is replaced with the updated data.

---

# 🌐 API Endpoint

### Update Contact in JSON Server

```
PUT /contacts/jsonserver/update/{id}
```

This endpoint updates the contact with the specified ID.

---

# 📥 Example Request

```
PUT /contacts/jsonserver/update/1
```

Request body:

```
{
 "id": 1,
 "firstName": "Bhumi",
 "lastName": "Shrivas",
 "city": "Bhopal"
}
```

---

# 📤 Example Response

```
Contact updated successfully in JSON Server
```

---

# 🧪 Testing Using CURL

```
curl -X PUT http://localhost:8080/contacts/jsonserver/update/1 \
-H "Content-Type: application/json" \
-d '{"id":1,"firstName":"Bhumi","lastName":"Shrivas","city":"Bhopal"}'
```

---

# 🔍 Verify Update

Open the JSON Server endpoint:

```
http://localhost:3000/contacts
```

The contact entry should reflect the updated information.

---

# 🌿 Git Branch

```
feature/UC24-update-entry-jsonserver
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC25 – Delete Entry from JSON Server

The next feature will allow deleting contacts from JSON Server using **HTTP DELETE requests**.

---
