
# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

This project follows a **Git Feature Branch Workflow**, where each **Use Case (UC)** is implemented in a separate branch and later merged into the `dev` branch.

---

# 🚀 UC14 – Read / Write Address Book Using CSV

This branch introduces functionality to **store and retrieve Address Book contacts using a CSV file**.

The application now supports:

- Writing contacts to a **CSV file**
- Reading contacts from a **CSV file**
- Using the **OpenCSV library** for CSV operations

CSV files make it easy to **store structured data in a tabular format**, which can later be opened in tools like Excel.

---

# 🛠 Tech Stack

- ☕ Java 17  
- 🌱 Spring Boot  
- 📦 Maven  
- 🔗 REST API  
- 🐙 Git & GitHub  
- 📄 OpenCSV Library  

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
├── model
│      Contact.java
│      AddressBook.java
│
├── io
│      AddressBookFileService.java
│      AddressBookCSVService.java
│
└── AddressBookAppApplication.java
```

---

# 📄 CSV File Format

Contacts are stored in:

```
contacts.csv
```

Example file content:

```
ID,FirstName,LastName,Address,City,State,Zip,Phone,Email
1,Bhumi,Shrivas,Bhopal,Bhopal,MP,462001,9876543210,bhumi@email.com
2,Rahul,Sharma,Delhi,Delhi,Delhi,110001,8888888888,rahul@email.com
```

Each row represents a **contact entry**.

---

# 🧠 Implementation Logic

The OpenCSV library is used to:

### Write CSV

```
CSVWriter writer = new CSVWriter(new FileWriter("contacts.csv"));
```

### Read CSV

```
CSVReader reader = new CSVReader(new FileReader("contacts.csv"));
```

Contacts are converted between **Java objects and CSV rows**.

---

# 🌐 API Endpoints

### Write Contacts to CSV

```
GET /contacts/csv/write
```

This API retrieves all contacts from the Address Book and writes them to a CSV file.

---

### Read Contacts from CSV

```
GET /contacts/csv/read
```

This API reads contacts from the CSV file and returns them as a list.

---

# 🧪 Testing Using CURL

### Write CSV File

```
curl http://localhost:8080/contacts/csv/write
```

Response:

```
Contacts written to CSV file
```

---

### Read CSV File

```
curl http://localhost:8080/contacts/csv/read
```

Example Response:

```
[
 {
  "id":1,
  "firstName":"Bhumi",
  "city":"Bhopal"
 }
]
```

---

# 🌿 Git Branch

```
feature/UC14-read-write-addressbook-csv
```

This branch implements **Use Case 14 – CSV File Operations**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC15 – Read / Write Address Book JSON

Next features:

- Write contacts to **JSON file**
- Read contacts from JSON
- Use **GSON library**

JSON files are commonly used for **data exchange in APIs and microservices**.

---
