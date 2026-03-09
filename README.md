# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC23 – Add Multiple Entries to JSON Server

This branch introduces functionality to **add multiple contacts to a JSON Server using REST API calls**.

JSON Server acts as a **mock backend service** that stores contact information in a JSON file and exposes it through REST endpoints.

The Spring Boot application sends **HTTP POST requests** to JSON Server to insert new contact records.

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
  "contacts": []
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

The application sends contact data to JSON Server using **RestTemplate**.

Example logic:

```
RestTemplate restTemplate = new RestTemplate();
restTemplate.postForObject(url, contact, Contact.class);
```

Each contact in the request list is sent to the JSON Server and stored in the JSON database.

---

# 🌐 API Endpoint

### Add Multiple Contacts to JSON Server

```
POST /contacts/jsonserver/add-multiple
```

This endpoint sends multiple contacts to the JSON Server.

---

# 📥 Example Request Body

```
[
 {
  "firstName": "Amit",
  "lastName": "Patel",
  "city": "Ahmedabad"
 },
 {
  "firstName": "Neha",
  "lastName": "Verma",
  "city": "Indore"
 }
]
```

---

# 📤 Example Response

```
Contacts added to JSON Server successfully
```

---

# 🧪 Testing Using CURL

```
curl -X POST http://localhost:8080/contacts/jsonserver/add-multiple \
-H "Content-Type: application/json" \
-d '[{"firstName":"Amit","lastName":"Patel","city":"Ahmedabad"},{"firstName":"Neha","lastName":"Verma","city":"Indore"}]'
```

---

# 🔍 Verify in JSON Server

Open in browser:

```
http://localhost:3000/contacts
```

You should see the newly added contact entries.

---

# 🌿 Git Branch

```
feature/UC23-add-multiple-entries-jsonserver
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC24 – Update Entry in JSON Server

Next feature will allow updating contact entries in JSON Server using **HTTP PUT requests**.

---
