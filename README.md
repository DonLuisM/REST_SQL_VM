#  📚 RESTful SQL API deployed on a Virtual Machine
A RESTful API built with Flask to manage records stored in a SQL database, deployed and executed inside a Virtual Machine using Vagrant and VirtualBox.
This project focuses on backend development, database integration, and infrastructure setup in an isolated environment.

### 📖 Project overview
This project demonstrates how to design and deploy a REST API with SQL persistence inside a virtualized environment. It covers the full backend workflow:
- API development with Flask.
- CRUD operations using a relational database.
- Environment isolation using a Virtual Machine.
- Automated provisioning with shell scripts.
- The API can be consumed using tools such as Postman or curl.

---
### 🎯 Features
- RESTful API for managing database records.
- Full CRUD operations using SQL database.
- Basic authentication and security measures.
- Hosted on a Virtual Machine.
- Environment provisioning with Vagrant.

---
### 🚀 Technologies Used
- Python
- Flask
- MySQL
- Virtual Machine (Vagrant + VirtualBox)
- Vagrant (for VM management)
- Shell Scripts (VM provisioning and automation)

---
### 🛣️ API endpoints (CRUD)
| Method   | Endpoint            | Description                         | Postman Example                           | Example Usage with curl
|----------|---------------------|-------------------------------------|--------------------------------------------------|---------------------------------------------|
| **GET**      | `/books`            | Retrieves all books                 | -                                                | `curl -i http://localhost:5000/books`   |
| **GET**      | `/books/id`         | Retrieves a specific book by its ID | `/books/2`                                       | `curl -i http://localhost:5000/books/2` |
| **POST**     | `/books`            | Creates a new book                  | `{"author": "", "description":"", "title":""}`   | `curl -i -H "Content-Type: application/json" -X POST -d '{"title":"El libro"}' http://localhost:5000/books` |
| **PUT**      | `/books/id`         | Updates an existing book by its ID  | `/books/2` with body `{"title": "New Title"}`    | `curl -i -H "Content-Type: application/json" -X PUT -d '{"author":"Jorgito"}' http://localhost:5000/books/2`|
| **DELETE**   | `/books/id`         | Deletes a book by its ID            | `/books/2`                                       | `curl -i -H "Content-Type: application/json" -X DELETE http://localhost:5000/books/1`  |

---
### 🧩 Project structure
```
📁 REST_SQL_VM
│
├── README.md               # Project documentation
├── Vagrantfile             # Virtual Machine configuration (Ubuntu)
├── apirest_mysql.py        # Flask REST API with MySQL integration
├── init.sql                # SQL script to initialize database schema
└── script.sh               # VM provisioning and setup automation
```

---
### ⚙️ Installation & local setup
1. Clone this repository:
   ```
    git clone https://github.com/DonLuisM/REST_SQL_VM.git
    cd REST_SQL_VM
   ```
2. Install dependencies
   ```
   pip install -r requirements.txt
   ```
3. Configure the database connection in .env file:
   ```
   DB_HOST=your-database-host
   DB_USER=your-database-user
   DB_PASS=your-database-password
   DB_NAME=your-database-name
   ```
4. Start the server:
   ```
   flask run
   ```
---
### 🖥️ Running the project using a Virtual Machine
1. Open CMD and start the Virtual Machine:
   ```
   vagrant up
   ```
2. Access the VM:
   ```
   vagrant ssh
   ```
3. Run the API server inside the VM:
   ```
   export FLASK_APP=apirest_mysql.py
   python3 -m flask run --host=0.0.0.0 
   ```
4. Stop the VM:
   ```
   vagrant halt
   ```
5. Destroy the VM (if needed):
   ```
   vagrant destroy -f
   ```

---
### 👨‍💻 Author

Luis Muñoz <br>
🔗 GitHub: [@DonLuisM](https://github.com/DonLuisM)
