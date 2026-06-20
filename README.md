# library-management-oop
An automated, command-line Library Management System built in Python to demonstrate core Object-Oriented Programming (OOP) concepts.
# Academic Project: Object-Oriented Library Management System

## Project Overview
This repository contains a CLI-based Library Management System built from scratch to demonstrate advanced Object-Oriented Programming (OOP) architectures in Python. The system models realistic library policies, including tier-based user limits, transaction tracking, dynamic overdue fine calculations, and hold queues for high-demand book copies.

## Core OOP Concepts Applied

### 1. Robust Class Inheritance & Polymorphism
* **Member Hierarchies:** A base `Member` class is specialized into `StudentMember`, `FacultyMember`, and `GuestMember` types. Each class overrides parameters to dictate specific operational boundaries:
  * **Students:** Limit of 5 active borrows, 14 loan days, 1 renewal allowed.
  * **Faculty:** Limit of 10 active borrows, 28 loan days, 2 renewals allowed.
  * **Guests:** Limit of 2 active borrows, 7 loan days, renewals restricted.
* **Librarian Override:** Features a specialized `Librarian` user configuration with administration access to handle structural data approval loops and unlock restricted accounts.

### 2. Encapsulation & Security Automation
* **Data Privacy:** Internal structures utilize private variables for sensitive user properties (IDs, contact details, account PINs) to safeguard entity states from outside mutation.
* **Account Locking System:** Enforces a secure automated state machine that counts incorrect validation tokens, automatically flipping an account to a locked status after 3 consecutive failures until an administrator resets the log.

### 3. State Management & Coordination Logic
* **Dynamic Copies System:** Tracks individual book units using a decoupled `BookCopy` structure, allowing the system to isolate distinct shelves while evaluating composite catalog balances.
* **Controller Pattern:** Dispatches specialized `LoanManager` and `ReservationManager` instances to regulate borrowing checkouts, block checkouts when limits are exceeded, verify hold priorities during renewals, and construct waitlists for occupied book titles.

### 4. Data Persistence & File Handling
* Uses Python's native `json` and file I/O libraries to serialize database state configurations safely to `members.json` and `books.json`.
* Appends a comma-delimited `transactions.txt` log file in real-time, archiving clear audit trail snapshots of user checkouts, check-ins, fines, and system sessions.

## Project Structure
* `LMS OOP PROJECT.ipynb`: Contains the complete source code implementation including data models, automation controllers, and input parsing loops.

## How to Run
1. Open the `.ipynb` notebook file in a Jupyter environment or Google Colab.
2. Run the application blocks sequentially to trigger the terminal CLI system.
3. Use the contextual interactive menu to test member enrollment, catalog updates, inventory loans, or view operational audit summaries.
