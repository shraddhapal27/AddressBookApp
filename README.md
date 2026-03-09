
# 🚀 UC16 – Retrieve Contacts From Database

This branch introduces **database connectivity using JDBC**.

The AddressBook application now supports retrieving contacts from a **MySQL database**.

---

# Technologies

- Java
- Spring Boot
- JDBC
- MySQL

---

# Database Table

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
| email | Email |

---

# API Endpoint

Retrieve contacts from DB

```
GET /contacts/db
```

---

# Test

```
curl http://localhost:8080/contacts/db
```

---

# Next UC

UC17 – Update Contact and Sync With Database

---

