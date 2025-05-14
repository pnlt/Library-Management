# 📚 Library Management System

[![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

> A comprehensive web-based library management solution developed using PHP and MySQL that efficiently handles all library operations in a college setting.

## 🌟 Features

### For Administrators

- **Dashboard Analytics** - Comprehensive overview of library statistics
- **Book Management** - Complete CRUD operations for book inventory
- **User Management** - Add and manage library users
- **Circulation Control** - Track book issues, returns and fines
- **Catalog Management** - Organize books with categories, authors, and rack locations

### For Users

- **Book Search** - Find books quickly using various parameters
- **Loan History** - Track personal borrowing history
- **Profile Management** - Update personal information

## 📋 Table of Contents

- [Screenshots](#screenshots)
- [System Requirements](#system-requirements)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Database Structure](#database-structure)
- [Functional Specifications](#functional-specifications)
- [Demo Credentials](#demo-credentials)
- [Development Team](#development-team)
- [License](#license)

## 📸 Screenshots

### Admin Interface

<details>
<summary>Admin Dashboard</summary>
<img src="https://user-images.githubusercontent.com/72748315/179931989-f2521673-2141-426d-a855-05df2df4c168.png" alt="Admin Dashboard" width="600">
</details>

<details>
<summary>Book Management</summary>
<img src="https://user-images.githubusercontent.com/72748315/179932166-0945f3f4-f129-459e-aa01-8bf98ace2326.png" alt="Book Management" width="600">
</details>

### User Interface

<details>
<summary>Login Screen</summary>
<img src="https://user-images.githubusercontent.com/72748315/179929983-c25d852c-0f5c-4319-a095-73b0b6bff19f.png" alt="Login Screen" width="600">
</details>

<details>
<summary>User Dashboard</summary>
<img src="https://user-images.githubusercontent.com/72748315/179931190-a7520afc-c463-4b1f-9ed9-498849fdc1d5.png" alt="User Dashboard" width="600">
</details>

<details>
<summary>Book Search</summary>
<img src="https://user-images.githubusercontent.com/72748315/179931354-65088b7d-bca6-4c3d-89fb-1a94c093dbbd.png" alt="Book Search" width="600">
</details>

<details>
<summary>Loan History</summary>
<img src="https://user-images.githubusercontent.com/72748315/179931772-e8179bfd-dc39-4fbc-b13d-0a788c213e6a.png" alt="Loan History" width="600">
</details>

## 💻 System Requirements

- **Web Server**: Apache 2.4+
- **PHP**: 7.4+ with MySQLi extension
- **Database**: MySQL 5.7+ or MariaDB 10.3+
- **Memory**: 512MB minimum
- **Disk Space**: 100MB for application files

## 🔧 Technology Stack

- **Backend**: PHP 7.4
- **Database**: MySQL
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 4
- **Additional Libraries**: jQuery, DataTables, Chart.js

## ⚙️ Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/library-management-system.git
   cd library-management-system
   ```

2. **Database setup**
   - Create a MySQL database named `library_management`
   - Import the SQL file from `database/library_management.sql`

3. **Configuration**
   - Rename `config.sample.php` to `config.php`
   - Update database credentials in `config.php`

4. **Web server configuration**
   - Point your web server to the project's root directory
   - Ensure `mod_rewrite` is enabled if using Apache

5. **Access the application**
   - Admin: <http://your-domain/admin>
   - User: <http://your-domain>

## 🗄️ Database Structure

```
┌─────────────┐       ┌─────────────┐       ┌─────────────┐
│    users    │       │    books    │       │   issues    │
├─────────────┤       ├─────────────┤       ├─────────────┤
│ id          │       │ id          │       │ id          │
│ name        │       │ isbn        │◄─────►│ book_id     │
│ email       │       │ title       │       │ user_id     │
│ password    │       │ author_id   │◄───┐  │ issue_date  │
│ user_type   │◄─────►│ category_id │    │  │ return_date │
│ created_at  │       │ rack_id     │◄┐  │  │ status      │
└─────────────┘       │ status      │ │  │  │ fine_amount │
                      └─────────────┘ │  │  └─────────────┘
                                      │  │
┌─────────────┐       ┌─────────────┐ │  │  ┌─────────────┐
│  categories │       │   authors   │ │  └─►│    racks    │
├─────────────┤       ├─────────────┤ │     ├─────────────┤
│ id          │       │ id          │ │     │ id          │
│ name        │◄─────►│ name        │ └────►│ location    │
│ status      │       │ status      │       │ status      │
└─────────────┘       └─────────────┘       └─────────────┘
```

## 📝 Functional Specifications

### 1. Administrator Features

#### 1.1. Authentication

- FR1.1.1: Admin login with email and password
- FR1.1.2: Admin logout functionality

#### 1.2. Dashboard

- FR1.2.1: Display comprehensive statistics including:
  - Total books issued
  - Total books returned
  - Total books not returned
  - Total fines received
  - Total books, authors, categories, and rack counts

#### 1.3. Category Management

- FR1.3.1: Add new book categories
- FR1.3.2: Update category information
- FR1.3.3: Delete categories

#### 1.4. Author Management

- FR1.4.1: Add new authors
- FR1.4.2: Update author information
- FR1.4.3: Delete authors

#### 1.5. Rack Location Management

- FR1.5.1: Add new rack locations
- FR1.5.2: Update rack information
- FR1.5.3: Delete rack locations

#### 1.6. Book Management

- FR1.6.1: Add new books with detailed information (ISBN, title, author, category, rack location)
- FR1.6.2: Update book information
- FR1.6.3: Delete books

#### 1.7. User Management

- FR1.7.1: Add new user accounts
- FR1.7.2: Delete users from the system

#### 1.8. Book Circulation Management

- FR1.8.1: Issue books to users by entering user ID and book ISBN
- FR1.8.2: View list of currently issued books
- FR1.8.3: Confirm book returns

### 2. User Features

#### 2.1. Authentication

- FR2.1.1: User login with email and password
- FR2.1.2: User logout functionality

#### 2.2. Book Loan Information

- FR2.2.1: View list of borrowed books, issue dates, return deadlines, and status

#### 2.3. Book Search

- FR2.3.1: Search books by title, author, category, or ISBN

#### 2.4. Profile Management

- FR2.4.1: Edit personal information including name, email, phone number, password

### 3. Non-Functional Requirements

- NFR1: User-friendly interface with responsive design
- NFR2: Support for at least 100 concurrent users
- NFR3: Password security with hashing
- NFR4: CRUD operation response times under 2 seconds
- NFR5: Logging of important operations (book additions/deletions, loans/returns)
- NFR6: Implementation using PHP with MySQL database
- NFR7: Daily data backup

## 🔑 Demo Credentials

### Admin Access

- **Email**: <admin@gmail.com>
- **Password**: admin

### User Access

- **Email**: <demo@gmail.com>
- **Password**: demo

## 👥 Development Team

This project was developed as part of our Agile Scrum final project by:

- [Team Member 1](https://github.com/NinITWB) - Backend Developer
- [Team Member 2](#) - Frontend Developer
- [Team Member 3](https://github.com/pnlt) - Database Engineer
- [Team Member 4](https://github.com/phamkhoa1373) - Product Owner
- [Team Member 5](https://github.com/Dusklb) - Scrum Master

## 📈 Development Process

This project was developed using Agile Scrum methodology with:

- 1 sprint of weeks each
- Daily stand-up meetings
- Bi-weekly sprint reviews and retrospectives
- Task management through ClickUp

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  Developed with ❤️ by Team MPPKK
</p>
