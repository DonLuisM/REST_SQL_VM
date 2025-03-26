#  📚 REST SQL VM
This project is built with Flask to manage a database using SQL, deployed on a Virtual Machine (VM).

### 🎯 Features
- REST API for managing database records.
- CRUD operations with SQL database.
- Hosted on a Virtual Machine.
- Authentication and security measures.
  
### 🚀 Technologies Used
- Python
- Flask
- MySQL
- Virtual Machine (Vagrant + VirtualBox)
- Vagrant (for VM management)
- Shell Scripts (for provisioning and automation)

### 🛠️ CRUD Route
| Method   | Endpoint            | Description                         | Example Usage on Postman                             | Example Usage with curl
|----------|---------------------|-------------------------------------|--------------------------------------------------|---------------------------------------------|
| **GET**      | `/books`            | Retrieves all books                 | -                                                | `curl -i http://localhost:5000/books`   |
| **GET**      | `/books/id`         | Retrieves a specific book by its ID | `/books/2`                                       | `curl -i http://localhost:5000/books/2` |
| **POST**     | `/books`            | Creates a new book                  | `{"author": "", "description":"", "title":""}`   | `curl -i -H "Content-Type: application/json" -X POST -d '{"title":"El libro"}' http://localhost:5000/books` |
| **PUT**      | `/books/id`         | Updates an existing book by its ID  | `/books/2` with body `{"title": "New Title"}`    | `curl -i -H "Content-Type: application/json" -X PUT -d '{"author":"Jorgito"}' http://localhost:5000/books/2`|
| **DELETE**   | `/books/id`         | Deletes a book by its ID            | `/books/2`                                       | `curl -i -H "Content-Type: application/json" -X DELETE http://localhost:5000/books/1`  |

---
### ⚙️ Instalation
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
### 🖥️ Using a VM
1. Open CMD and start the Virtual Machine:
   ```
   vagrant up
   ```
2. Access the VM:
   ```
   vagrant ssh
   ```
3. Run the API server:
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
