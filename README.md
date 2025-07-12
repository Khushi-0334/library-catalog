# 📚 Library Catalog API

A simple Java-based RESTful API built with Spring Boot to manage a library's book catalog. This project demonstrates core backend principles such as object-oriented design, REST architecture, in-memory data handling, and validation.

---

## 🎯 Objective

This project was built as part of a Java code challenge to showcase:
- REST API design using Spring Boot
- Object-Oriented Programming (OOP) principles
- In-memory data handling with `Map`
- API testing via Postman

---

## 🚀 Features

- ✅ Add a new book
- 📚 Retrieve all books
- 🔍 Get a book by its ID
- 🗑️ Delete a book
- 🔁 Update the availability of a book
- ✨ Simple input validation using annotations

---

## 🛠️ Tech Stack

- **Java 17**
- **Spring Boot**
- **Spring Web**
- **Jakarta Bean Validation**
- **Postman** for testing

---

## 📂 Project Structure

library-catalog/

 ├── model/ # Book.java 
 
 ├── service/ # BookService.java 
 
 ├── controller/ # BookController.java 
 
 ├── application.properties
 
 ├── library-catalog.postman_collection.json
 
 ├── pom.xml
 
 └── README.md


---

## ▶️ How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/library-catalog.git

2. Navigate into the project folder:
   
   cd library-catalog

3.  Run the application

4.  The server will start at:
    
    http://localhost:8080


## 🔗 REST Endpoints

| Method   | Endpoint                       | Description                |
| -------- | ------------------------------ | -------------------------- |
| `POST`   | `/api/books`                   | Add a new book             |
| `GET`    | `/api/books`                   | Retrieve all books         |
| `GET`    | `/api/books/{id}`              | Get book by ID             |
| `DELETE` | `/api/books/{id}`              | Delete book by ID          |
| `PUT`    | `/api/books/{id}/availability` | Update availability status |


## 📦 Sample JSON Requests
   
✅ 1. Add a New Book
    Request:
    POST /api/books

    Body (JSON):
     {
      "title": "The Alchemist",
      "author": "Paulo Coelho",
      "isbn": "978-0061122415"
     }

    Expected Response (201 Created):
     {
      "id": 1,
      "title": "The Alchemist",
      "author": "Paulo Coelho",
      "isbn": "978-0061122415",
      "available": true
     }

📚 2. Get All Books
    Request:
    GET /api/books

    Expected Response (200 OK):
 
    [
     {
      "id": 1,
      "title": "The Alchemist",
      "author": "Paulo Coelho",
      "isbn": "978-0061122415",
      "available": true
     },
     {
      "id": 2,
      "title": "Atomic Habits",
      "author": "James Clear",
      "isbn": "978-0735211292",
      "available": true
     }
    ]

🔍 3. Get Book by ID
    Request:
    GET /api/books/1

    Expected Response (200 OK):

    {
     "id": 1,
     "title": "The Alchemist",
     "author": "Paulo Coelho",
     "isbn": "978-0061122415",
     "available": true
    }

📛 If the book doesn’t exist:
    
    Response (404 Not Found):
    null

🗑️ 4. Delete a Book
    Request:
    DELETE /api/books/1

    Expected Response (204 No Content):
    No body.

    📛 If the book doesn’t exist:
    Response (404 Not Found)

🔁 5. Update Availability
    Request:
    PUT /api/books/2/availability
  
    Body (JSON):
    false

    Expected Response (200 OK):
    No body.

    📛 If the book doesn’t exist:
    Response (404 Not Found)

❌ 6. Validation Example
    Request:
    POST /api/books
   
   Invalid Body:
    
    {
     "title": "",
     "author": "",
     "isbn": ""
    }

    Expected Response (400 Bad Request):

    json
    
     {
      "timestamp": "...",
      "status": 400,
      "errors": [
      "Title is required",
      "Author is required",
      "ISBN is required"
      ]
     }

## 🧪 Postman Collection

You can import and test all API endpoints using the included Postman collection:

📄 [`library-catalog.postman_collection.json`](library-catalog.postman_collection.json)


