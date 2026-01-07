# Hostel Allocation System

## Overview
The Hostel Allocation System is a C++ application designed to automate the room assignment process for university accommodation. It allocates rooms (1-seater, 2-seater, or 3-seater) based on a strict meritocracy system using Cumulative Grade Point Average (CGPA) and student preferences.

The system utilizes custom data structures to manage student records dynamically, ensuring that allocations are processed efficiently according to rank and inventory availability.

## Features
* **Merit-Based Allocation Algorithm:** Implements a priority-based logic where students with higher CGPA scores are processed first, ensuring fairness.
* **Dynamic Preference Handling:** Allows students to submit a prioritized list of room types. The system attempts to fulfill the highest priority preference before moving to alternatives.
* **Custom Data Structures:** Utilizes a custom Singly Linked List implementation to maintain a sorted record of students, optimizing the allocation sequence without external sorting libraries.
* **Inventory Management:** Supports dynamic input for total room capacity across different room categories.
* **Allocation Reporting:** Generates a comprehensive report detailing successful allocations by room type and identifying unallocated students.

## Technical Architecture

### Data Structures
* **Linked List:** Used to store `Student` objects. The list is maintained in descending order of CGPA upon insertion, reducing the time complexity of the allocation phase to O(N).
* **Vectors:** Used for managing room inventory counts and storing individual student preferences.

### Core Classes
1. **`Student`**: Encapsulates student data including Registration Number, Name, CGPA, Preferences, and Allocation Status.
2. **`HostelAllocationSystem`**: Manages the core logic, including:
    * `addStudent`: Inserts a new student into the sorted Linked List.
    * `allocateRooms`: Iterates through the sorted list to assign rooms based on inventory.
    * `displayAllocatedRooms`: Outputs the final status of allocations.

## Building and Running

### Prerequisites
* A C++ Compiler (GCC, Clang, or MSVC)
* Standard Template Library (STL) support

### Compilation Instructions
To compile the source code, use the following command in your terminal:

```bash
g++ main.cpp -o hostel_allocation

Execution
Run the compiled executable:

Linux/macOS:

Bash

./hostel_allocation
Windows:

DOS

hostel_allocation.exe
Usage Example
Input: The system will prompt for room inventory and student details.

Plaintext

Enter the total number of 1-seater rooms: 1
Enter the total number of 2-seater rooms: 1
Enter the total number of 3-seater rooms: 0
Enter the number of students: 2

Enter details for student 1:
Registration No: 101
Name: John Doe
CGPA: 8.5
Preference for 1-seater, 2-seater, 3-seater (in order): 1 2 3

Enter details for student 2:
Registration No: 102
Name: Jane Smith
CGPA: 9.2
Preference for 1-seater, 2-seater, 3-seater (in order): 1 2 3
Output: The system sorts by CGPA (Jane Smith > John Doe) and allocates accordingly.

Plaintext

Allocated rooms:
1-seater rooms:
Registration No: 102, Name: Jane Smith, CGPA: 9.2

2-seater rooms:
Registration No: 101, Name: John Doe, CGPA: 8.5

Future Scope

Frontend
Adding an UI to interact 

Backend
File Persistence: Integration of file handling to save allocation records to CSV or text files.

Exception Handling: Robust input validation to handle non-numeric inputs or invalid preference codes.

Authentication: Adding a login layer for administrators to manage inventory securely.

License
This project is available under the MIT License.
