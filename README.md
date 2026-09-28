# 🍽️ Restaurant Management System

A web-based **Restaurant Management System** built using **PHP, MySQL, HTML, CSS, JavaScript, and Bootstrap**. The application provides an online platform where customers can register, log in, browse restaurants and food items, place orders, and view their previous orders. It also includes an administration section for managing restaurant-related data and orders.

## 📌 Project Overview

The Restaurant Management System is designed to simplify the process of ordering food online and managing restaurant operations.

The system provides a user-friendly interface for customers to:

* Create an account
* Log in securely
* Browse available restaurants
* View food menus
* Select food items
* Place food orders
* Checkout orders
* View previous orders
* Log out of their account

The project also contains an **Admin Panel** for managing restaurant and food-related information.

---

## ✨ Features

### 👤 Customer Features

* User registration
* User login and logout
* CAPTCHA verification during login
* Browse restaurants
* View restaurant menus
* View individual food/dish details
* Add food items to an order
* Checkout
* Place food orders
* View previous orders
* Session-based authentication

### 🏪 Restaurant & Food Management

* Restaurant listing
* Food/dish listing
* Product management
* Food ordering workflow
* Order management
* Checkout functionality

### 🛠️ Admin Features

The project includes an `admin` directory for administrative functionality.

The administration section can be used for restaurant-system management tasks such as:

* Managing restaurants
* Managing food items
* Managing orders
* Managing users
* Updating restaurant information

---

## 🧰 Technologies Used

| Technology       | Purpose                   |
| ---------------- | ------------------------- |
| **PHP**          | Server-side programming   |
| **MySQL**        | Database management       |
| **HTML5**        | Page structure            |
| **CSS3**         | Styling                   |
| **JavaScript**   | Client-side functionality |
| **Bootstrap**    | Responsive UI             |
| **Font Awesome** | Icons                     |
| **jQuery**       | Front-end scripting       |
| **Apache/XAMPP** | Local web server          |

The repository contains dedicated folders for CSS, JavaScript, images, fonts, SCSS, database files, connection code, and administration functionality.

---

## 📂 Project Structure

```text
Restaurant-Management/
│
├── admin/
│   └── Admin panel files
│
├── connection/
│   └── connect.php
│
├── css/
│   ├── Bootstrap styles
│   ├── Main styles
│   ├── Login styles
│   └── Animation styles
│
├── fonts/
│   └── Font resources
│
├── images/
│   ├── Restaurant images
│   ├── Food images
│   ├── Icons
│   └── Payment images
│
├── js/
│   └── JavaScript files
│
├── scss/
│   └── SCSS source files
│
├── Mail/
│   └── Email-related files
│
├── DATABASE FILE/
│   └── Database files
│
├── index.php
├── login.php
├── registration.php
├── logout.php
├── restaurants.php
├── dishes.php
├── product-action.php
├── checkout.php
├── your_orders.php
├── delete_orders.php
├── verification.php
│
└── README.md
```

The repository currently contains the major customer-facing PHP files including `index.php`, `login.php`, `registration.php`, `restaurants.php`, `dishes.php`, `checkout.php`, `your_orders.php`, and order/product action files.

---

## 🔄 Application Workflow

```text
                    ┌──────────────────┐
                    │      Home        │
                    │    index.php     │
                    └────────┬─────────┘
                             │
               ┌─────────────┼─────────────┐
               │             │             │
               ▼             ▼             ▼
        ┌────────────┐ ┌────────────┐ ┌────────────┐
        │   Login    │ │ Register   │ │ Restaurants│
        │ login.php  │ │registration│ │restaurants │
        └─────┬──────┘ └────────────┘ └─────┬──────┘
              │                              │
              │                              ▼
              │                       ┌────────────┐
              │                       │   Dishes   │
              │                       │ dishes.php │
              │                       └─────┬──────┘
              │                             │
              │                             ▼
              │                       ┌────────────┐
              │                       │   Order    │
              │                       │   Cart     │
              │                       └─────┬──────┘
              │                             │
              │                             ▼
              │                       ┌────────────┐
              │                       │  Checkout  │
              │                       │checkout.php│
              │                       └─────┬──────┘
              │                             │
              │                             ▼
              │                       ┌────────────┐
              │                       │ My Orders  │
              │                       │your_orders │
              │                       └────────────┘
              │
              ▼
       Session Authentication
```

---

## 🔐 Authentication

The application uses PHP sessions to maintain logged-in users.

The login process includes:

1. User enters username.
2. User enters password.
3. User enters CAPTCHA.
4. Credentials are checked against the database.
5. A user session is created after successful authentication.
6. The user is redirected to the home page.
7. The user can access their order history.
8. Logout destroys the active session.

The current login implementation stores the authenticated user's ID in `$_SESSION["user_id"]`.

> **Security note:** The current code uses MD5 for password verification. MD5 is not recommended for password storage in modern applications. For production use, replace it with PHP's `password_hash()` and `password_verify()` functions.

---

## 🗄️ Database

The application uses **MySQL** as its database system.

Database connectivity is handled through:

```text
connection/connect.php
```

The database files are provided in the repository under:

```text
DATABASE FILE/
```

The application connects to the database before performing operations such as user authentication, restaurant retrieval, food/product operations, and order processing.

---

## 🛠️ Installation & Setup

### 1. Install XAMPP

Download and install **XAMPP** with:

* Apache
* MySQL
* phpMyAdmin
* PHP

### 2. Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/Mangeshcoding/Restaurant-Management.git
```

Move into the project directory:

```bash
cd Restaurant-Management
```

### 3. Move Project to XAMPP

Copy the project into:

```text
C:\xampp\htdocs\
```

The final location should look like:

```text
C:\xampp\htdocs\Restaurant-Management\
```

### 4. Start XAMPP

Open XAMPP Control Panel and start:

```text
Apache
MySQL
```

### 5. Create the Database

Open:

```text
http://localhost/phpmyadmin
```

Create the required MySQL database and import the SQL/database file provided inside:

```text
DATABASE FILE/
```

### 6. Configure Database Connection

Open:

```text
connection/connect.php
```

Update the database credentials according to your local MySQL configuration.

Example:

```php
<?php

$db = mysqli_connect(
    "localhost",
    "root",
    "",
    "your_database_name"
);

if (!$db) {
    die("Database connection failed: " . mysqli_connect_error());
}
?>
```

> Replace `your_database_name` with the actual database name used by the SQL file.

### 7. Run the Project

Open your browser and visit:

```text
http://localhost/Restaurant-Management/
```

---

## 👨‍💻 Main Pages

| File                     | Purpose                            |
| ------------------------ | ---------------------------------- |
| `index.php`              | Home page                          |
| `login.php`              | User login                         |
| `registration.php`       | New user registration              |
| `logout.php`             | User logout                        |
| `restaurants.php`        | Restaurant listing                 |
| `dishes.php`             | Restaurant food/menu listing       |
| `product-action.php`     | Product/order-related actions      |
| `checkout.php`           | Order checkout                     |
| `your_orders.php`        | User order history                 |
| `delete_orders.php`      | Order deletion functionality       |
| `verification.php`       | Verification-related functionality |
| `admin/`                 | Administration panel               |
| `connection/connect.php` | Database connection                |

The main navigation in `index.php` links users to Home, Restaurants, Login/Register or My Orders/Logout depending on the current session state.

---

## 🛒 Ordering Process

A typical customer order follows this process:

```text
Register/Login
      ↓
Browse Restaurants
      ↓
Select Restaurant
      ↓
Browse Dishes
      ↓
Select Food
      ↓
Add Product / Order
      ↓
Checkout
      ↓
Order Confirmation
      ↓
View My Orders
```

The repository contains dedicated pages for restaurant browsing, dishes, checkout, order history, and product/order actions.

---

## 🎨 User Interface

The project uses:

* Bootstrap
* Custom CSS
* Font Awesome
* Responsive layouts
* Restaurant and food images
* Animated UI components
* Login-specific styling

The home page includes a restaurant/food-ordering presentation and guides users through selecting a restaurant and ordering food.

---

## 🔒 Security Considerations

The current project is suitable as a learning/academic project, but several areas should be improved before production deployment.

### Recommended Improvements

* Replace MD5 password hashing with `password_hash()`.
* Use prepared statements instead of directly concatenating user input into SQL.
* Validate and sanitize all incoming data.
* Add CSRF protection to forms.
* Store database credentials outside publicly accessible project files.
* Disable detailed PHP errors in production.
* Improve session security.
* Validate uploaded files if file uploads are introduced.
* Use HTTPS in production.
* Add role-based authorization for administrative pages.

For example, instead of:

```php
$password = md5($password);
```

use:

```php
$password = password_hash($password, PASSWORD_DEFAULT);
```

And verify it using:

```php
password_verify($password, $storedHash);
```

---

## 🎓 Project Purpose

This project can be used as a **college/academic project** for demonstrating concepts such as:

* PHP web development
* MySQL database integration
* CRUD operations
* Session management
* Authentication
* Form handling
* E-commerce/order workflow
* Front-end web design
* Server-side programming

---

## 🤝 Contributing

Contributions are welcome.

To contribute:

```bash
git clone https://github.com/Mangeshcoding/Restaurant-Management.git
```

Create a new branch:

```bash
git checkout -b feature/new-feature
```

Make your changes and commit them:

```bash
git add .
git commit -m "Add new feature"
```

Push the branch:

```bash
git push origin feature/new-feature
```

Then create a Pull Request.

---

## 📄 License

No explicit license is currently specified in the repository. If you intend to make the project open source for reuse, add an appropriate license file such as MIT after confirming the licensing terms for the project's existing assets/code.

---

## 👨‍💻 Author

**Mangeshcoding**

GitHub Repository:

https://github.com/Mangeshcoding/Restaurant-Management

---

## ⭐ Support

If you find this project useful for learning PHP, MySQL, or restaurant-management system development, consider giving the repository a ⭐ on GitHub.

---

## 📚 Project Summary

**Restaurant Management System** is a PHP/MySQL-based web application that provides an online restaurant and food-ordering workflow.

### Core Technologies

```text
Frontend
 ├── HTML
 ├── CSS
 ├── Bootstrap
 └── JavaScript / jQuery

Backend
 └── PHP

Database
 └── MySQL

Server
 └── Apache / XAMPP
```

### Core Modules

```text
User Authentication
        ↓
Restaurant Management
        ↓
Food/Menu Management
        ↓
Product Selection
        ↓
Order Management
        ↓
Checkout
        ↓
Order History
        ↓
Administration
```

The repository is currently a small PHP/MySQL project with the main application and supporting directories contained directly in the repository.
