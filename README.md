# 📒 AddressBookApp

A **Spring Boot REST API** application for managing contacts in an Address Book.

The project is implemented using a **Git Feature Branch Workflow**, where each use case is developed in a separate branch and merged into the `dev` branch.

---

# 🚀 UC13 – Read / Write Address Book Using File IO

This branch introduces **File Input/Output operations** for the Address Book application.

Contacts can now be **written to a file** using Java File IO.

This allows persistent storage of contact information outside the application memory.

---

# 🛠 Tech Stack

- Java 17
- Spring Boot
- Maven
- REST API
- Git & GitHub
- Java File IO

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
│
└── AddressBookAppApplication.java
```

---

# 🧠 Implementation Logic

Contacts are retrieved from all address books and written to a text file.

The application performs the following steps:

1. Retrieve all contacts using

```
addressBookService.getAllContacts()
```

2. Pass contacts to the File Service

```
AddressBookFileService.writeContactsToFile()
```

3. Write contact details to

```
contacts.txt
```

---

# 📁 Example File Output

Example content of `contacts.txt`:

```
Bhumi Shrivas Bhopal
Rahul Sharma Delhi
Amit Patel Ahmedabad
```

Each line represents a contact entry.

---

# 🌐 API Endpoint

### Write Contacts to File

```
GET /contacts/write
```

This API retrieves all contacts and writes them to the file.

---

# 🧪 Testing Using CURL

```
curl http://localhost:8080/contacts/write
```

Response:

```
Contacts written to file
```

A file named **contacts.txt** will be created in the project directory.

---

# 🌿 Git Branch

```
feature/UC13-read-write-addressbook-file-io
```

This branch implements **Use Case 13 – File IO for Address Book Contacts**.

After review it will be merged into:

```
dev
```

---

# 📌 Next Implementation

### UC14 – Read / Write AddressBook CSV

Next features:

- Write contacts to **CSV file**
- Read contacts from CSV
- Use **OpenCSV Library**

---
