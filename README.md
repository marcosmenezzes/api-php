# 🐘 PHP API

Study project built with PHP using a layered architecture, utilizing **PDO + SQLite** for data persistence and **Docker** to simplify environment setup and execution.

The system implements a simple **product CRUD**, serving as a foundation for learning backend organization concepts using pure PHP.

---

## 🛠️ Technologies Used

- PHP 8.2
- SQLite
- PDO
- Docker
- Docker Compose

---

## 📁 Project Structure

```text
api-php/
├── src/
│   ├── controllers/
│   │   └── productController.php
│   ├── db/
│   │   └── sqlite.db
│   ├── models/
│   │   └── product.php
│   ├── repositories/
│   │   └── productRepository.php
│   ├── services/
│   │   └── productService.php
│   ├── views/
│   │   └── productView.php
│   └── server.php
├── Dockerfile
├── docker-compose.yaml
└── test.php
```

---

## 🧩 Layer Organization

### Model

Represents the system entity.

`product.php` defines the product with:

- `id`
- `name`
- `stock`

---

### Repository

Responsible for data access in the SQLite database.

`productRepository.php`:

- retrieves all products
- retrieves a product by ID
- saves a product
- updates a product
- removes a product

---

### Service

Business logic layer.

`productService.php`:

- centralizes CRUD operations
- acts as a bridge between controller and repository

---

### Controller

Responsible for coordinating application actions.

`productController.php`:

- lists products
- creates products
- updates products
- removes products

---

### View

Responsible for data output.

`productView.php`:

- displays products in text format

---

## 🚀 Current Features

- Product listing
- Product creation
- Product updating
- Product deletion
- SQLite database persistence

---

## 🐳 Running with Docker

### 1. Clone the Repository

```bash id="g3v93t"
git clone https://github.com/marcosmenezzes/api-php.git
cd api-php
```

---

### 2. Start the Container

```bash id="j9f4r2"
docker compose up --build
```

The application will be available at:

```text
http://localhost:8000
```

---

## ⚙️ How Execution Works

The project uses the `php:8.2-cli` image, installs support for `pdo` and `pdo_sqlite`, copies the project files into the container, and starts PHP’s built-in server pointing to:

```text
src/server.php
```

---

## 🧪 Quick Test

There is a `test.php` file used to test the complete product CRUD flow, including:

- creation
- listing
- updating
- deletion

---

## 📌 Notes

The `server.php` file is still in an early stage and indicates the intention to create endpoints for:

- `GET`
- `POST`
- `PUT`
- `DELETE`

In other words, the project already has the structural foundation of an API, but it can still evolve to expose complete HTTP routes.

---

## 🔮 Suggested Next Steps

- Create real HTTP routes in `server.php`
- Return JSON responses
- Implement error handling
- Add validations
- Separate environment configuration
- Create endpoint documentation
- Add migrations or a script for creating the `products` table

---

## 🎯 Project Goal

This project was developed with a focus on learning, practicing:

- layered code organization
- separation of responsibilities
- CRUD operations with PHP
- SQLite persistence
- Docker-based execution

---

## 👨‍💻 Author

Marcos Menezes
