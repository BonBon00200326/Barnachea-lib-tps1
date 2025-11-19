University Library Management System
Description / Overview
The University Library Management System is a comprehensive web-based application designed to streamline library operations. This system provides an intuitive interface for managing books and tracking borrowing activities. It features a modern, responsive design with a gradient purple-to-blue interface that makes library management efficient and user-friendly.
Objectives

Efficient Book Management: Provide a centralized system to add, edit, view, and delete books from the library collection
Borrowing Tracking: Monitor all book borrowings, returns, and overdue items in real-time
Data Organization: Categorize books and maintain accurate records with ISBN tracking
User Experience: Deliver an intuitive interface that simplifies library operations
Inventory Control: Track book availability and total copies to prevent stock issues
Timeline Management: Maintain clear records of borrowing dates, due dates, and return dates

Features / Functionality
Books Management Module

Add New Books
<img width="1661" height="813" alt="Screenshot 2025-11-19 072556" src="https://github.com/user-attachments/assets/b97c0caa-2f98-4e9d-8165-7b9114be10c2" />

Input book title, author, and category
Enter 13-digit ISBN for unique identification
Set publication year (Range: 1901-2025)
Define total number of copies available
Form validation for required fields


View Book Details
<img width="1918" height="956" alt="image" src="https://github.com/user-attachments/assets/4146fbd7-1614-488d-8781-efad5c4ce469" />

Display complete book information including title, author, ISBN, and publication year
Visual status indicators (Available/Out of Stock)
Show current availability (e.g., "2/2 copies", "5/5 copies")
Category labels for easy classification


Edit Book Information
<img width="1917" height="914" alt="image" src="https://github.com/user-attachments/assets/68c7c701-0bc6-4eae-a6a0-493fbbdbf89d" />

Modify existing book details
Update author, category, or copy count
Change publication information


Delete Books
<img width="591" height="207" alt="image" src="https://github.com/user-attachments/assets/fc6efab8-3f29-4991-8913-28f2989a48a4" />

Remove books from the library database
Permanent deletion with confirmation


Dashboard Statistics
<img width="1919" height="970" alt="Screenshot 2025-11-19 072515" src="https://github.com/user-attachments/assets/e51c0837-8863-4b7c-9b43-2bc7bbb8f995" />

Total Books: 5
Available Books: 4
Borrowed Books: 1
Total Categories: 4



Borrowings Management Module

Create New Borrowing
<img width="1668" height="641" alt="Screenshot 2025-11-19 073010" src="https://github.com/user-attachments/assets/10a0bd8e-3df1-460c-8ba0-45245328b1e8" />

Select book from dropdown menu
Enter borrower name and email
Set borrowed date and due date
Standard loan period: 14 days
Automatic due date calculation


View Borrowing Records
<img width="1650" height="890" alt="image" src="https://github.com/user-attachments/assets/72108cda-29fc-417f-a78f-ca57ee683cef" />

Complete timeline display (Borrowed, Due, Returned dates)
Borrower information (name and email)
Book title and author details
Status tracking (Active/Returned/Overdue)


Borrowing Statistics Dashboard
<img width="1914" height="975" alt="Screenshot 2025-11-19 072818" src="https://github.com/user-attachments/assets/62a5608e-a5e2-4f79-baeb-80e80014c2fe" />

Total Borrowings: 5
Active Borrowings: 0
Overdue Items: 1
Returned Books: 4


Delete Borrowing Records

<img width="564" height="188" alt="image" src="https://github.com/user-attachments/assets/2f1f981f-1723-43a2-8e05-6ce758c83be0" />
<img width="1639" height="772" alt="image" src="https://github.com/user-attachments/assets/e432704c-3e9f-4587-b27a-c22605de739b" />


Remove borrowing history entries
Clean up completed transactions
<img width="1917" height="901" alt="image" src="https://github.com/user-attachments/assets/e11df0c1-5e5b-4626-85c6-39a2b11d74d4" />



Installation Instructions
Prerequisites

PHP >= 8.1
Composer
MySQL or MariaDB
Node.js and NPM
Laravel >= 10.x
Modern web browser (Chrome, Firefox, Safari, or Edge)
Text editor or IDE (VS Code, PHPStorm, etc.)

Setup Steps

Clone or Download the Project

bash   git clone https://github.com/BonBon00200326/Barnachea-lib-tps1.git
   cd Barnachea-lib-tps1

Install Dependencies

bash   # Install PHP dependencies
   composer install
   
   # Install Node.js dependencies
   npm install

Environment Configuration

bash   # Copy the environment file
   cp .env.example .env
   
   # Generate application key
   php artisan key:generate

Database Configuration

Open .env file and configure your database credentials:



env  DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=library_tps
DB_USERNAME=root
DB_PASSWORD=

Run Database Migrations

bash   # Create database tables
   php artisan migrate
   
   # (Optional) Seed database with sample data
   php artisan db:seed

Build Frontend Assets

bash   # Compile CSS and JavaScript
   npm run dev
   
   # Or for production
   npm run build

Start the Development Server

bash   # Start Laravel development server
   php artisan serve

Navigate to http://localhost:8000 in your browser

Project Structure
Barnachea-lib-tps1/
├── app/
│   ├── Http/
│   │   └── Controllers/
│   │       ├── BookController.php
│   │       └── BorrowingController.php
│   └── Models/
│       ├── Book.php
│       └── Borrowing.php
├── database/
│   ├── migrations/
│   └── seeders/
├── resources/
│   ├── views/
│   │   ├── books/
│   │   └── borrowings/
│   ├── js/
│   └── css/
├── routes/
│   └── web.php
├── .env
├── composer.json
├── package.json
└── README.md
