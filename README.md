
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC20 – Add Contact to Database

This branch introduces functionality to **add new contacts directly into the MySQL database**.

Users can now create new contact entries through a REST API, which inserts the data into the database using **JDBC**.

This feature enables persistent storage of contact information in the database.

---

# 🛠 Tech Stack

- ☕ Java 17  
- 🌱 Spring Boot  
- 📦 Maven  
- 🔗 REST API  
- 🐬 MySQL Database  
- 🔌 JDBC  

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
├── db
│      AddressBookDBService.java
│
├── model
│      Contact.java
│      AddressBook.java
│
└── AddressBookAppApplication.java
```

---

# 🗄 Database Table

Database used:

```
addressbook_db
```

Table:

```
contacts
```

| Column | Description |
|------|-------------|
| id | Contact ID |
| first_name | First name |
| last_name | Last name |
| address | Address |
| city | City |
| state | State |
| zip | Zip code |
| phone | Phone number |
| email | Email address |
| date_added | Date when contact was added |

---

# 🧠 SQL Query Used

```
INSERT INTO contacts
(first_name,last_name,address,city,state,zip,phone,email,date_added)
VALUES
('Amit','Patel','Satellite','Ahmedabad','Gujarat','380015','9998887777','amit@email.com',CURDATE());
```

The query inserts a new contact record into the database with the current date.

---

# 🌐 API Endpoint

### Add Contact to Database

```
POST /contacts/db/add
```

This API inserts a new contact into the database.

---

# 📥 Example Request Body

```
{
 "firstName":"Amit",
 "lastName":"Patel",
 "address":"Satellite",
 "city":"Ahmedabad",
 "state":"Gujarat",
 "zip":"380015",
 "phoneNumber":"9998887777",
 "email":"amit@email.com"
}
```

---

# 📤 Example Response

```
Contact added successfully
```

---

# 🧪 Testing Using CURL

```
curl -X POST http://localhost:8080/contacts/db/add \
-H "Content-Type: application/json" \
-d '{"firstName":"Amit","lastName":"Patel","address":"Satellite","city":"Ahmedabad","state":"Gujarat","zip":"380015","phoneNumber":"9998887777","email":"amit@email.com"}'
```

---

# 🔍 Verify in Database

Run the following query in MySQL:

```
SELECT * FROM contacts;
```

Example output:

| id | first_name | city | date_added |
|----|-----------|------|-----------|
| 1 | Bhumi | Bhopal | 2026-03-09 |
| 2 | Rahul | Delhi | 2026-03-09 |
| 3 | Amit | Ahmedabad | 2026-03-09 |

---

# 🌿 Git Branch

```
feature/UC20-add-contact-to-database
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC21 – Add Multiple Contacts Using Multithreading

Next features:

- Insert multiple contacts simultaneously
- Use **Java multithreading**
- Improve performance when adding many contacts
- Synchronize database operations safely

---
