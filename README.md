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

Input book title, author, and category
Enter 13-digit ISBN for unique identification
Set publication year (Range: 1901-2025)
Define total number of copies available
Form validation for required fields


View Book Details

Display complete book information including title, author, ISBN, and publication year
Visual status indicators (Available/Out of Stock)
Show current availability (e.g., "2/2 copies", "5/5 copies")
Category labels for easy classification


Edit Book Information

Modify existing book details
Update author, category, or copy count
Change publication information


Delete Books

Remove books from the library database
Permanent deletion with confirmation


Dashboard Statistics

Total Books: 5
Available Books: 4
Borrowed Books: 1
Total Categories: 4



Borrowings Management Module

Create New Borrowing

Select book from dropdown menu
Enter borrower name and email
Set borrowed date and due date
Standard loan period: 14 days
Automatic due date calculation


View Borrowing Records

Complete timeline display (Borrowed, Due, Returned dates)
Borrower information (name and email)
Book title and author details
Status tracking (Active/Returned/Overdue)


Borrowing Statistics Dashboard

Total Borrowings: 5
Active Borrowings: 0
Overdue Items: 1
Returned Books: 4


Delete Borrowing Records

Remove borrowing history entries
Clean up completed transactions



Installation Instructions
Prerequisites

Modern web browser (Chrome, Firefox, Safari, or Edge)
Text editor or IDE (VS Code, Sublime Text, etc.)
Basic knowledge of HTML, CSS, and JavaScript
Local web server (optional, can use browser directly)

Setup Steps

Clone or Download the Project

bash   git clone https://github.com/yourusername/library-management-system.git
   cd library-management-system

Project Structure

   library-management-system/
   ├── index.html
   ├── books.html
   ├── borrowings.html
   ├── css/
   │   └── styles.css
   ├── js/
   │   ├── books.js
   │   └── borrowings.js
   └── README.md

Open the Application

Option 1: Double-click index.html to open in browser
Option 2: Use a local server:



bash     # Using Python 3
     python -m http.server 8000
     
     # Using PHP
     php -S localhost:8000

Navigate to http://localhost:8000 in your browser


Database Configuration

The system uses browser localStorage for data persistence
No additional database setup required for basic functionality



Usage
Managing Books
To Add a New Book:

Navigate to the Books page
Click the "+ Add New Book" button
Fill in the form:

Title: Enter the book title (e.g., "Python")
Author: Enter author name (e.g., "Ramir")
Category: Enter category (e.g., "3" or category name)
ISBN: Enter 13-digit ISBN (e.g., "3462452746209")
Publication Year: Enter year between 1901-2025 (e.g., "1901")
Total Copies: Enter number of copies (e.g., "4")


Click "Save Book"

To View Book Details:

Books are displayed in a table format showing all information
Status badges indicate availability (Green = Available, Red = Out of Stock)
Copy information shows current availability (e.g., "2/2 copies")

To Edit a Book:

Click the yellow edit icon (pencil) next to the book
Modify the desired fields
Click "Save Book" to confirm changes

To Delete a Book:

Click the red delete icon (trash bin)
Confirm deletion when prompted

Managing Borrowings
To Create a New Borrowing:

Navigate to the Borrowings page
Click the "+ New Borrowing" button
Fill in the borrowing form:

Select Book: Choose from dropdown
Borrower Name: Enter name (e.g., "Jhon Bon Barnachea")
Borrower Email: Enter email (e.g., "barnacheajhonbon00@gmail.com")
Borrowed Date: Select date (default: today)
Due Date: Select return date (default: 14 days later)


Click "Create Borrowing"

To View Borrowing Records:

View the timeline showing borrowed, due, and returned dates
Check status badges (Green = Returned, Yellow = Active, Red = Overdue)
See borrower details and book information

To Delete a Borrowing Record:

Click the red delete icon (trash bin) next to the borrowing
Confirm deletion when prompted

Screenshots
Books Management Dashboard
Show Image
Main dashboard showing book statistics and list with 5 total books, 4 available, 1 borrowed, and 4 categories
Add New Book Form
Show Image
Form interface for adding new books with fields for title, author, category, ISBN, publication year, and total copies
Borrowings Management Dashboard
Show Image
Borrowings overview showing 5 total borrowings, 0 active, 1 overdue, and 4 returned with detailed borrowing records
New Borrowing Form
Show Image
Form for creating new borrowing with book selection, borrower details, and date fields showing 14-day standard loan period
Code Snippets
Book Data Structure
javascriptconst book = {
  id: "book_001",
  title: "Python",
  author: "Ramir",
  category: "Programming",
  isbn: "3462452746209",
  publicationYear: 1901,
  totalCopies: 4,
  availableCopies: 4,
  status: "Available"
};
Borrowing Data Structure
javascriptconst borrowing = {
  id: "borrow_001",
  bookTitle: "Java",
  author: "Ramir",
  borrowerName: "Jhon Bon Barnachea",
  borrowerEmail: "barnacheajhonbon00@gmail.com",
  borrowedDate: "2025-09-24",
  dueDate: "2025-09-30",
  returnedDate: "2025-09-24",
  status: "Returned"
};
Form Validation Example
javascriptfunction validateBookForm(formData) {
  const { title, author, isbn, publicationYear, totalCopies } = formData;
  
  // Validate ISBN (13 digits)
  if (!/^\d{13}$/.test(isbn)) {
    return { valid: false, message: "ISBN must be 13 digits" };
  }
  
  // Validate year range
  if (publicationYear < 1901 || publicationYear > 2025) {
    return { valid: false, message: "Year must be between 1901-2025" };
  }
  
  // Validate required fields
  if (!title || !author || !totalCopies) {
    return { valid: false, message: "All fields are required" };
  }
  
  return { valid: true };
}
Contributors

Your Name - Full Stack Developer

Implemented Books Management Module
Designed UI/UX interface
Created borrowing tracking system
Developed form validation logic



License
This project is licensed under the MIT License.
MIT License

Copyright (c) 2025 University Library Management System

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
Additional Notes
Technical Stack

Frontend: HTML5, CSS3, JavaScript (ES6+)
Styling: Custom CSS with gradient backgrounds and modern UI components
Data Storage: Browser localStorage for client-side persistence
Icons: Custom icon set for actions (view, edit, delete, borrowing)

Browser Compatibility

Chrome 90+
Firefox 88+
Safari 14+
Edge 90+

Future Enhancements

Integration with backend database (MySQL/PostgreSQL)
User authentication and role-based access
Email notifications for due dates and overdue books
Advanced search and filtering options
Report generation (PDF/Excel export)
Barcode scanning integration
Mobile responsive design improvements
