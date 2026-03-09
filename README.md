
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project is developed using a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC1 – Create Contact Model & Basic Controller

This branch implements the **initial setup of the Address Book application**.

It includes the **Contact model** and a **basic REST API endpoint** to verify that the Spring Boot application is running successfully.

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
│ ├── controller
│ │ AddressBookController.java
│ │
│ ├── model
│ │ Contact.java
│ │
│ └── AddressBookAppApplication.java
│
├── src/main/resources
│ application.properties
│
└── pom.xml
```

---

# 👤 Contact Model

The `Contact` class represents a person in the Address Book.

### Fields included

| Field | Description |
|------|-------------|
| id | Unique identifier |
| firstName | Person's first name |
| lastName | Person's last name |
| address | Street address |
| city | City name |
| state | State name |
| zip | Postal code |
| phoneNumber | Contact phone number |
| email | Email address |

---

# 🌐 API Endpoint

### Welcome API

GET /addressbook

This endpoint verifies that the **Address Book application is running**.

---

# 🧪 Test Using CURL

Run the following command in terminal:

curl http://localhost:8080/addressbook

### Expected Response
Welcome to Address Book Application

---

# ▶️ How to Run the Project

### 1️⃣ Clone the repository
git clone https://github.com/
<your-username>/AddressBookApp.git

---

### 2️⃣ Navigate to the project
cd AddressBookApp

---

### 3️⃣ Run the Spring Boot application
mvn spring-boot:run
or run
AddressBookAppApplication.java
from your IDE.

---

### 4️⃣ Open in browser
http://localhost:8080/addressbook

---

# 🌿 Git Branch
feature/UC1-create-contact

This branch contains the implementation for **Use Case 1**.

After review it will be merged into:
dev

---

# 📌 Next Implementation

### UC2 – Add Contact

Next features to be implemented:

- ➕ Add new contact using **POST API**
- 📋 Store contacts in a **Local List**
- 🧠 Introduce **Service Layer**
- 🔍 Retrieve all contacts

---
