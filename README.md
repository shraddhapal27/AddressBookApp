
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

The project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and merged into the `dev` branch after completion.

---

# 🚀 UC19 – Count Contacts by City or State (Database)

This branch introduces functionality to **count the number of contacts grouped by city and state directly from the MySQL database**.

The feature uses **SQL aggregation with the `GROUP BY` clause** to calculate the number of contacts belonging to each city or state.

Instead of retrieving all contacts and counting them in memory, the counting is performed efficiently inside the database.

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

Table used:

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

# 🧠 SQL Queries Used

### Count Contacts by City

```
SELECT city, COUNT(*) AS count
FROM contacts
GROUP BY city;
```

---

### Count Contacts by State

```
SELECT state, COUNT(*) AS count
FROM contacts
GROUP BY state;
```

These queries group records by city or state and return the total number of contacts for each group.

---

# 🌐 API Endpoints

### Count Contacts by City

```
GET /contacts/db/count/city
```

---

### Count Contacts by State

```
GET /contacts/db/count/state
```

---

# 📤 Example Response

```
{
 "Bhopal": 2,
 "Delhi": 1
}
```

The response represents the number of contacts belonging to each city or state.

---

# 🧪 Testing Using CURL

### Count Contacts by City

```
curl http://localhost:8080/contacts/db/count/city
```

---

### Count Contacts by State

```
curl http://localhost:8080/contacts/db/count/state
```

---

# 🌿 Git Branch

```
feature/UC19-count-contacts-by-city-state-db
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC20 – Add Contact to Database

Next features:

- Insert new contacts into the MySQL database
- Use **JDBC PreparedStatement**
- Sync database with application APIs

---
