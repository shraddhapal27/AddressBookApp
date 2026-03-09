
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

The project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC17 – Update Contact and Sync With Database

This branch introduces functionality to **update contact information stored in the MySQL database**.

The update operation ensures that any modification made to a contact is **synchronized with the database**.

The implementation uses **JDBC PreparedStatement**, which provides a secure and efficient way to execute SQL queries.

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

# 🗄 Database Configuration

Database name:

```
addressbook_db
```

Table structure:

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

---

# 🧠 SQL Query Used

```
UPDATE contacts
SET first_name=?, last_name=?, address=?, city=?, state=?, zip=?, phone=?, email=?
WHERE id=?;
```

PreparedStatement is used to safely bind parameters to the query.

---

# 🌐 API Endpoint

### Update Contact in Database

```
PUT /contacts/db/update
```

This endpoint updates the details of a contact using the provided ID.

---

# 📥 Example Request Body

```
{
 "id":1,
 "firstName":"Bhumi",
 "lastName":"Shrivas",
 "address":"MP Nagar",
 "city":"Bhopal",
 "state":"MP",
 "zip":"462001",
 "phoneNumber":"9999999999",
 "email":"bhumi@email.com"
}
```

---

# 🧪 Testing Using CURL

```
curl -X PUT http://localhost:8080/contacts/db/update \
-H "Content-Type: application/json" \
-d '{"id":1,"firstName":"Bhumi","lastName":"Shrivas","city":"Bhopal"}'
```

Response:

```
Contact updated successfully
```

---

# 🔍 Verify Update

Run in MySQL:

```
SELECT * FROM contacts;
```

The contact information should reflect the updated values.

---

# 🌿 Git Branch

```
feature/UC17-update-contact-and-sync-with-db
```

After review, this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC18 – Retrieve Contacts by Date Range

Next features:

- Retrieve contacts added between two dates
- Use **SQL date filtering**
- Implement **date-based search API**

---
