
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC18 – Retrieve Contacts by Date Range

This branch introduces functionality to **retrieve contacts added within a specific date range from the MySQL database**.

The application now supports querying contacts based on the date they were added using **SQL date filtering**.

This feature is implemented using **JDBC and SQL `BETWEEN` operator**.

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

# 🗄 Database Update

A new column was added to the contacts table to track when a contact was added.

```
date_added DATE
```

SQL used:

```
ALTER TABLE contacts
ADD date_added DATE;
```

Example table structure:

| id | first_name | last_name | city | state | date_added |
|----|-----------|-----------|------|------|-----------|
| 1 | Bhumi | Shrivas | Bhopal | MP | 2026-03-09 |
| 2 | Rahul | Sharma | Delhi | Delhi | 2026-03-08 |

---

# 🧠 SQL Query Used

```
SELECT * FROM contacts
WHERE date_added BETWEEN ? AND ?;
```

PreparedStatement is used to safely bind the start and end dates.

---

# 🌐 API Endpoint

### Retrieve Contacts by Date Range

```
GET /contacts/db/date-range
```

Parameters:

| Parameter | Description |
|----------|-------------|
| startDate | Start date for filtering |
| endDate | End date for filtering |

---

# 📥 Example Request

```
GET /contacts/db/date-range?startDate=2026-03-01&endDate=2026-03-10
```

---

# 📤 Example Response

```
[
 {
  "id":1,
  "firstName":"Bhumi",
  "lastName":"Shrivas",
  "city":"Bhopal",
  "state":"MP"
 }
]
```

---

# 🧪 Testing Using CURL

```
curl "http://localhost:8080/contacts/db/date-range?startDate=2026-03-01&endDate=2026-03-10"
```

---

# 🌿 Git Branch

```
feature/UC18-retrieve-contacts-by-date-range
```

After review this branch will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC19 – Count Contacts by City or State (Database)

Next features:

- Count contacts grouped by city
- Count contacts grouped by state
- Use SQL aggregation with **GROUP BY**

Example result:

```
Bhopal → 3 contacts
Delhi → 2 contacts
```

---
