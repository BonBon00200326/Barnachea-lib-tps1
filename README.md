# University Library Management System

#### Description / Overview
The University Library Management System is a comprehensive web-based application developed using the Laravel framework to streamline and automate library operations. This enterprise-grade solution provides an intuitive interface for managing book inventories and tracking borrowing activities in real-time.
The system implements a modern Model-View-Controller (MVC) architecture with a responsive, gradient purple-to-blue user interface that makes library management efficient and user-friendly. Built with MySQL database integration, it ensures data integrity through transaction-safe operations and maintains comprehensive audit trails for all library transactions.
This midterm project demonstrates practical implementation of web development concepts including CRUD operations, database relationships, form validation, RESTful routing, and responsive design principles using Laravel's powerful ecosystem.

#### Objectives
The main goals and learning outcomes of this project include:
Technical Objectives

Master Laravel Framework: Implement a full-stack application using Laravel 10.x with Eloquent ORM
Database Design: Create normalized database schema with proper relationships and constraints
RESTful Architecture: Build RESTful API endpoints following industry best practices
Data Validation: Implement comprehensive server-side validation and sanitization
Authentication & Security: Apply CSRF protection, input validation, and SQL injection prevention

#### Functional Objectives

Efficient Book Management: Develop a centralized system for complete book lifecycle management (Create, Read, Update, Delete)
Borrowing Workflow Automation: Implement automated borrowing processes with due date calculations and status tracking
Real-time Analytics: Provide dashboard metrics for operational insights and decision-making
Data Integrity: Ensure referential integrity and maintain accurate inventory counts
User Experience: Deliver an intuitive, responsive interface that simplifies library operations

#### Learning Outcomes

Understanding of MVC design pattern in Laravel
Proficiency in MySQL database operations and migrations
Knowledge of Blade templating engine and component-based UI
Experience with Git version control and GitHub workflows
Ability to deploy and maintain production web applications

#### Features / Functionality
### **Managing Books**
Adding a New Book
Step-by-Step Process:

Navigate to Books Page

Click "Books" in the main navigation menu
You'll see the Books Management dashboard

<img width="1919" height="911" alt="Screenshot 2025-11-19 085007" src="https://github.com/user-attachments/assets/25f60bd2-e6de-4132-a651-4e92ec975cfb" />


Open Add Book Form

Click the "+ Add New Book" button (top-right corner)
A form modal or page will appear


Fill in Book Information
Example 1: Adding a Programming Book

   Title:              Python Programming for Beginners
   Author:             Ramir Santos
   Category:           Programming
   ISBN:               9783462452746
   Publication Year:   2022
   Total Copies:       5
Example 2: Adding a Classic Literature Book
   Title:              To Kill a Mockingbird
   Author:             Harper Lee
   Category:           Fiction
   ISBN:               9780061120084
   Publication Year:   1960
   Total Copies:       3
<img width="1318" height="662" alt="Screenshot 2025-11-19 084819" src="https://github.com/user-attachments/assets/351f2997-7352-487f-90dc-be2bfc1e7960" />

Validation Check

System automatically validates:

✅ ISBN is exactly 13 digits
✅ ISBN is unique (not already in database)
✅ Publication year is between 1901-2025
✅ All required fields are filled




Submit the Form

Click "Save Book" button
Success message appears: "Book added successfully!"
New book appears in the books list
Dashboard metrics update automatically
<img width="1919" height="915" alt="Screenshot 2025-11-19 084921" src="https://github.com/user-attachments/assets/d5c4b2a6-61aa-47a8-b671-63f00095dcbf" />


Viewing Book Details
What You'll See:
The books list displays in a clean table format:

Understanding the Status Badges:

🟢 Available (Green): Books ready for borrowing
🔴 Out of Stock (Red): All copies are currently borrowed
Copy count shows: Available/Total (e.g., "2/2 copies" = 2 available out of 2 total)
<img width="1919" height="973" alt="Screenshot 2025-11-19 091803" src="https://github.com/user-attachments/assets/8d38801b-93e6-41db-8a16-16427cc3a6de" />


Editing a Book
Scenario: You discovered that a book's copy count is incorrect or you need to update the category.
Process:

Locate the Book

Find the book in the books list
Use search or scroll to locate it


Click Edit Icon (✏️ pencil icon)

Edit form appears with current data pre-filled
<img width="1917" height="974" alt="Screenshot 2025-11-19 091601" src="https://github.com/user-attachments/assets/966d6d76-4e33-4879-9282-97fb66d084ee" />
<img width="1909" height="954" alt="Screenshot 2025-11-19 091621" src="https://github.com/user-attachments/assets/6bba047e-ec78-4b09-8abc-08e54ef4abbc" />


Modify Fields

   Original:
   Title: Python Proggraming for Beginners
   Total Copies: 5
   Available Copies: 5
   <img width="1919" height="915" alt="Screenshot 2025-11-19 084921" src="https://github.com/user-attachments/assets/5d5a1384-34e5-4f18-9cfc-33aeef3fcdc1" />

   Updated:
   Title: Python Programming
   Total Copies: 2
   Available Copies: 2
<img width="1919" height="973" alt="Screenshot 2025-11-19 091803" src="https://github.com/user-attachments/assets/5b4b0ab4-05d7-456a-b52a-d0e950bb47c8" />

Save Changes

Click "Save Book"
Confirmation message appears
Updated information displays immediately




Deleting a Book
Important: You can only delete books that are not currently borrowed!
Process:

Click Delete Icon (🗑️ trash bin icon)
Confirmation Dialog Appears

   Are you sure you want to delete "Python Programming"?
   This action cannot be undone.
   
   [Cancel]  [Delete]

Confirm Deletion

Click "Delete"
Book is removed from system
Dashboard metrics update
<img width="1916" height="823" alt="Screenshot 2025-11-19 091851" src="https://github.com/user-attachments/assets/f58cdb5e-beb8-49b2-9da0-04f23f31d574" />


What Happens:

If book has active borrowings → ❌ Error: "Cannot delete book with active borrowings"
If book is available → ✅ Book deleted successfully


### **Managing Borrowings**
###### **Creating a New Borrowing**

<img width="1919" height="970" alt="Screenshot 2025-11-19 092132" src="https://github.com/user-attachments/assets/f66eddda-9ebc-4783-bd2c-a078c59a93b5" />

Navigate to Borrowings Page

Click "Borrowings" in main menu
View Borrowings Management dashboard


Click "+ New Borrowing"

Borrowing form appears
<img width="1919" height="970" alt="Screenshot 2025-11-19 092157" src="https://github.com/user-attachments/assets/c00cffd3-8111-42bb-aae7-f0c2384bab94" />


Fill in Borrowing Details
Example:

   Select Book:          Python Programming by Ramir
   
   Borrower Name:        Jhon Bon Barnachea
   Borrower Email:       barnacheajhonbon00@gmail.com
   
   Borrowed Date:        11/19/2025 (today)
   Due Date:             12/03/2025 (automatically calculated: +14 days)

System Verification

✅ Checks if book is available
✅ Validates email format
✅ Calculates due date (14 days from borrowed date)


Submit Borrowing

Click "Create Borrowing"
Success message: "Book borrowed successfully!"
Email confirmation sent (if configured)
<img width="1919" height="976" alt="Screenshot 2025-11-19 092221" src="https://github.com/user-attachments/assets/31807e80-892c-4da5-9ce2-f84d9fbf567f" />

What Happens Automatically:
Before:
Python Programming - Available: 2/2 copies
<img width="1919" height="973" alt="Screenshot 2025-11-19 091803" src="https://github.com/user-attachments/assets/8211abe8-e470-49a8-b9ac-6a2e9cec65a3" />

After Borrowing:
Python Programming - Available: 1/2 copies
<img width="1919" height="973" alt="Screenshot 2025-11-19 092318" src="https://github.com/user-attachments/assets/79a09a11-58f0-4f7e-bea2-7274ccb787e5" />

Borrowing Record Created:
Status: Active
Due Date: December 3, 2025

Viewing Borrowing Records
The borrowing list shows complete transaction details:

🟡 Active (Yellow): Currently borrowed, not yet returned
🟢 Returned (Green): Successfully returned on time
🔴 Overdue (Red): Past due date, not yet returned

<img width="1919" height="973" alt="Screenshot 2025-11-19 091803" src="https://github.com/user-attachments/assets/422cdaa8-9b98-4021-91af-3a07ab6fb173" />

Returning a Book
Scenario: Student returns "Python Programming" after finishing their assignment.
Process:
<img width="1919" height="971" alt="Screenshot 2025-11-19 092545" src="https://github.com/user-attachments/assets/aa8c4fbc-e224-47c7-9902-1b1e7d1c39d6" />
<img width="1919" height="986" alt="Screenshot 2025-11-19 092620" src="https://github.com/user-attachments/assets/a9337ce1-ae33-488d-8bc7-30363eb864ad" />


Locate the Borrowing Record

Find the active borrowing in the list
Look for 🟡 "Active" status


Click "Return" Button or checkmark icon (✅)

Confirmation may appear

System Processes Return:

   Automated Actions:
   ✅ Records current date as return date
   ✅ Changes status from "Active" to "Returned"
   ✅ Increases available copies count
   ✅ Checks if return is late
   
   If Returned On Time:
   Status: 🟢 Returned
   
   If Returned Late:
   Status: 🔴 Overdue (with late fee calculation if applicable)
<img width="1919" height="973" alt="Screenshot 2025-11-19 092714" src="https://github.com/user-attachments/assets/ed53e857-1929-4531-85a8-602fdf8f896c" />


Updated Display:

   Before:
   Python Programming - Available: 1/2 copies
   Status: Active
   <img width="1919" height="973" alt="Screenshot 2025-11-19 092318" src="https://github.com/user-attachments/assets/abf53e85-9697-4a35-b525-da396f48c048" />

   After:
   Python Programming - Available: 2/2 copies
   Status: Returned
   Returned: November 19, 2025
   <img width="1919" height="973" alt="Screenshot 2025-11-19 091803" src="https://github.com/user-attachments/assets/055a11f6-43de-4d3e-8e7c-474a676d108e" />

Deleting a Borrowing Record
When to Delete:

Cleaning up old completed transactions
Removing test records
Correcting erroneous entries

Process:

Click delete icon (🗑️) next to borrowing
Confirm deletion
Record permanently removed

Note: Deleting a borrowing record does NOT affect book availability if it was already returned.
<img width="1919" height="970" alt="Screenshot 2025-11-19 092839" src="https://github.com/user-attachments/assets/05fa5ef4-ef9e-4c9d-9f0d-2c67682b03f2" />

### **Code Snippets**
Book Model (Eloquent ORM)
php<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Model;
use Illuminate\Database\Eloquent\SoftDeletes;

class Book extends Model
{
    use SoftDeletes;

    /**
     * The attributes that are mass assignable.
     */
    protected $fillable = [
        'title',
        'author',
        'isbn',
        'category',
        'publication_year',
        'total_copies',
        'available_copies',
    ];

    /**
     * The attributes that should be cast.
     */
    protected $casts = [
        'publication_year' => 'integer',
        'total_copies' => 'integer',
        'available_copies' => 'integer',
    ];

    /**
     * Get all borrowings for this book.
     */
    public function borrowings()
    {
        return $this->hasMany(Borrowing::class);
    }

    /**
     * Check if book is available for borrowing.
     */
    public function isAvailable(): bool
    {
        return $this->available_copies > 0;
    }

    /**
     * Decrement available copies when borrowed.
     */
    public function borrow(): void
    {
        if ($this->available_copies > 0) {
            $this->decrement('available_copies');
        }
    }

    /**
     * Increment available copies when returned.
     */
    public function returnBook(): void
    {
        if ($this->available_copies < $this->total_copies) {
            $this->increment('available_copies');
        }
    }
}

Borrowing Model
php<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Model;
use Carbon\Carbon;

class Borrowing extends Model
{
    protected $fillable = [
        'book_id',
        'borrower_name',
        'borrower_email',
        'borrowed_date',
        'due_date',
        'returned_date',
        'status',
    ];

    protected $casts = [
        'borrowed_date' => 'date',
        'due_date' => 'date',
        'returned_date' => 'date',
    ];

    /**
     * Get the book that was borrowed.
     */
    public function book()
    {
        return $this->belongsTo(Book::class);
    }

    /**
     * Check if borrowing is overdue.
     */
    public function isOverdue(): bool
    {
        return $this->status === 'active' 
            && Carbon::now()->greaterThan($this->due_date);
    }

    /**
     * Calculate days overdue.
     */
    public function daysOverdue(): int
    {
        if (!$this->isOverdue()) {
            return 0;
        }
        
        return Carbon::now()->diffInDays($this->due_date);
    }

    /**
     * Mark as returned.
     */
    public function markAsReturned(): void
    {
        $this->update([
            'returned_date' => Carbon::now(),
            'status' => 'returned',
        ]);
        
        $this->book->returnBook();
    }
}

Database Migration - Books Table
php<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    public function up(): void
    {
        Schema::create('books', function (Blueprint $table) {
            $table->id();
            $table->string('title');
            $table->string('author');
            $table->string('isbn', 13)->unique();
            $table->string('category', 100);
            $table->year('publication_year');
            $table->unsignedInteger('total_copies')->default(1);
            $table->unsignedInteger('available_copies')->default(1);
            $table->timestamps();
            $table->softDeletes();

            // Indexes for performance
            $table->index('isbn');
            $table->index('category');
            $table->index('title');
        });
    }

    public function down(): void
    {
        Schema::dropIfExists('books');
    }
};

Database Migration - Borrowings Table
php<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    public function up(): void
    {
        Schema::create('borrowings', function (Blueprint $table) {
            $table->id();
            $table->foreignId('book_id')->constrained()->onDelete('cascade');
            $table->string('borrower_name');
            $table->string('borrower_email');
            $table->date('borrowed_date');
            $table->date('due_date');
            $table->date('returned_date')->nullable();
            $table->enum('status', ['active', 'returned', 'overdue'])->default('active');
            $table->timestamps();

            // Indexes
            $table->index('status');
            $table->index('borrower_email');
            $table->index('due_date');
        });
    }

    public function down(): void
    {
        Schema::dropIfExists('borrowings');
    }
};

BookController - CRUD Operations
php<?php

namespace App\Http\Controllers;

use App\Models\Book;
use Illuminate\Http\Request;

class BookController extends Controller
{
    /**
     * Display a listing of books.
     */
    public function index()
    {
        $books = Book::paginate(10);
        
        $statistics = [
            'total' => Book::count(),
            'available' => Book::where('available_copies', '>', 0)->count(),
            'borrowed' => Book::where('available_copies', '<', 'total_copies')->count(),
            'categories' => Book::distinct('category')->count(),
        ];
        
        return view('books.index', compact('books', 'statistics'));
    }

    /**
     * Store a newly created book.
     */
    public function store(Request $request)
    {
        $validated = $request->validate([
            'title' => 'required|max:255',
            'author' => 'required|max:255',
            'isbn' => 'required|digits:13|unique:books,isbn',
            'category' => 'required|max:100',
            'publication_year' => 'required|integer|min:1901|max:2025',
            'total_copies' => 'required|integer|min:1',
        ]);

        $validated['available_copies'] = $validated['total_copies'];

        $book = Book::create($validated);

        return redirect()->route('books.index')
            ->with('success', 'Book added successfully!');
    }

    /**
     * Update the specified book.
     */
    public function update(Request $request, Book $book)
    {
        $validated = $request->validate([
            'title' => 'required|max:255',
            'author' => 'required|max:255',
            'isbn' => 'required|digits:13|unique:books,isbn,' . $book->id,
            'category' => 'required|max:100',
            'publication_year' => 'required|integer|min:1901|max:2025',
            'total_copies' => 'required|integer|min:1',
        ]);

        $book->update($validated);

        return redirect()->route('books.index')
            ->with('success', 'Book updated successfully!');
    }

    /**
     * Remove the specified book.
     */
    public function destroy(Book $book)
    {
        // Check if book has active borrowings
        if ($book->borrowings()->where('status', 'active')->exists()) {
            return back()->with('error', 'Cannot delete book with active borrowings!');
        }

        $book->delete();

        return redirect()->route('books.index')
            ->with('success', 'Book deleted successfully!');
    }
}

BorrowingController - Transaction Management
php<?php

namespace App\Http\Controllers;

use App\Models\Book;
use App\Models\Borrowing;
use Illuminate\Http\Request;
use Carbon\Carbon;

class BorrowingController extends Controller
{
    /**
     * Display borrowings dashboard.
     */
    public function index()
    {
        $borrowings = Borrowing::with('book')
            ->latest()
            ->paginate(10);
        
        $statistics = [
            'total' => Borrowing::count(),
            'active' => Borrowing::where('status', 'active')->count(),
            'overdue' => Borrowing::where('status', 'overdue')->count(),
            'returned' => Borrowing::where('status', 'returned')->count(),
        ];
        
        return view('borrowings.index', compact('borrowings', 'statistics'));
    }

    /**
     * Store a new borrowing transaction.
     */
    public function store(Request $request)
    {
        $validated = $request->validate([
            'book_id' => 'required|exists:books,id',
            'borrower_name' => 'required|max:255',
            'borrower_email' => 'required|email|max:255',
            'borrowed_date' => 'required|date',
            'due_date' => 'required|date|after:borrowed_date',
        ]);

        $book = Book::findOrFail($validated['book_id']);

        // Check availability
        if (!$book->isAvailable()) {
            return back()->with('error', 'Book is currently unavailable!');
        }

        // Create borrowing
        $borrowing = Borrowing::create($validated);

        // Update book availability
        $book->borrow();

        return redirect()->route('borrowings.index')
            ->with('success', 'Book borrowed successfully!');
    }

    /**
     * Mark borrowing as returned.
     */
    public function return(Borrowing $borrowing)
    {
        if ($borrowing->status === 'returned') {
            return back()->with('error', 'Book already returned!');
        }

        $borrowing->markAsReturned();

        return redirect()->route('borrowings.index')
            ->with('success', 'Book returned successfully!');
    }

    /**
     * Delete borrowing record.
     */
    public function destroy(Borrowing $borrowing)
    {
        $borrowing->delete();

        return redirect()->route('borrowings.index')
            ->with('success', 'Borrowing record deleted!');
    }
}

Form Validation Example (JavaScript)
javascript// Client-side ISBN validation
function validateISBN(isbn) {
    // Remove any hyphens or spaces
    isbn = isbn.replace(/[-\s]/g, '');
    
    // Check if exactly 13 digits
    if (!/^\d{13}$/.test(isbn)) {
        return {
            valid: false,
            message: 'ISBN must be exactly 13 digits'
        };
    }
    
    // Calculate ISBN-13 checksum
    let sum = 0;
    for (let i = 0; i < 12; i++) {
        const digit = parseInt(isbn[i]);
        sum += (i % 2 === 0) ? digit : digit * 3;
    }
    
    const checksum = (10 - (sum % 10)) % 10;
    const providedChecksum = parseInt(isbn[12]);
    
    if (checksum !== providedChecksum) {
        return {
            valid: false,
            message: 'Invalid ISBN checksum'
        };
    }
    
    return { valid: true };
}

// Publication year validation
function validatePublicationYear(year) {
    const currentYear = new Date().getFullYear();
    const minYear = 1901;
    
    if (year < minYear || year > currentYear) {
        return {
            valid: false,
            message: `Year must be between ${minYear} and ${currentYear}`
        };
    }
    
    return { valid: true };
}

// Form submission with validation
document.getElementById('bookForm').addEventListener('submit', function(e) {
    const isbn = document.getElementById('isbn').value;
    const year = parseInt(document.getElementById('publication_year').value);
    
    // Validate ISBN
    const isbnValidation = validateISBN(isbn);
    if (!isbnValidation.valid) {
        e.preventDefault();
        alert(isbnValidation.message);
        return false;
    }
    
    // Validate year
    const yearValidation = validatePublicationYear(year);
    if (!yearValidation.valid) {
        e.preventDefault();
        alert(yearValidation.message);
        return false;
    }
    
    return true;
});

Blade Template Example (Books Index)
blade@extends('layouts.app')

@section('content')
<div class="container">
    <!-- Header -->
    <div class="header-section">
        <div>
            <h1>📚 Books Management</h1>
            <p>Manage your library's book collection</p>
        </div>
        <a href="{{ route('books.create') }}" class="btn btn-primary">
            + Add New Book
        </a>
    </div>

    <!-- Statistics Dashboard -->
    <div class="statistics-grid">
        <div class="stat-card">
            <div class="stat-icon">📚</div>
            <div class="stat-value">{{ $statistics['total'] }}</div>
            <div class="stat-label">Total Books</div>
        </div>
        
        <div class="stat-card">
            <div class="stat-icon">✅</div>
            <div class="stat-value">{{ $statistics['available'] }}</div>
            <div class="stat-label">Available</div>
        </div>
        
        <div class="stat-card">
            <div class="stat-icon">⏰</div>
            <div class="stat-value">{{ $statistics['borrowed'] }}</div>
            <div class="stat-label">Borrowed</div>
        </div>
        
        <div class="stat-card">
            <div class="stat-icon">🏷️</div>
            <div class="stat-value">{{ $statistics['categories'] }}</div>
            <div class="stat-label">Categories</div>
        </div>
    </div>

    <!-- Books Table -->
    <div class="table-container">
        <table class="books-table">
            <thead>
                <tr>
                    <th>Book Details</th>
                    <th>Author</th>
                    <th>Category</th>
                    <th>Status</th>
                    <th>Actions</th>
                </tr>
            </thead>
            <tbody>
                @foreach($books as $book)
                <tr>
                    <td>
                        <div class="book-avatar">{{ substr($book->title, 0, 1) }}</div>
                        <div>
                            <strong>{{ $book->title }}</strong><br>
                            <small>Published: {{ $book->publication_year }}</small><br>
                            <small>ISBN: {{ $book->isbn }}</small>
                        </div>
                    </td>
                    <td>{{ $book->author }}</td>
                    <td>
                        <span class="badge badge-category">{{ $book->category }}</span>
                    </td>
                    <td>
                        @if($book->available_copies > 0)
                            <span class="badge badge-success">Available</span>
                            <small>{{ $book->available_copies }}/{{ $book->total_copies }} copies</small>
                        @else
                            <span class="badge badge-danger">Out of Stock</span>
                            <small>{{ $book->total_copies }} total copies</small>
                        @endif
                    </td>
                    <td class="actions">
                        <a href="{{ route('books.show', $book) }}" title="View">👁️</a>
                        <a href="{{ route('books.edit', $book) }}" title="Edit">✏️</a>
                        @if($book->available_copies > 0)
                            <a href="{{ route('borrowings.create', ['book_id' => $book->id]) }}" title="Borrow">📚</a>
                        @endif
                        <form action="{{ route('books.destroy', $book) }}" method="POST" style="display:inline;">
                            @csrf
                            @method('DELETE')
                            <button type="submit" onclick="return confirm('Are you sure?')" title="Delete">🗑️</button>
                        </form>
                    </td>
                </tr>
                @endforeach
            </tbody>
        </table>
    </div>

    <!-- Pagination -->
    <div class="pagination">
        {{ $books->links() }}
    </div>
</div>
@endsection

**Contributors**
Jhon Bon Barnachea 

 **Email: barnacheajhonbon00@gmail.com**
 **GitHub: @BonBon00200326**

