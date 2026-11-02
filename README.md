# Repair Workshop Job Card Manager

**Course:** CAP455 – Object-Oriented Programming using C++  
**Phase:** CA1 – Design & Create  
**Syllabus:** Units I and II  
**Language:** C++  
**Development environment:** Dev-C++ or a standard `g++` compiler

## Student Details

- **Student name:** Santosh Kumar
- **Reg number:** 12627834
- **Programme:** MCA
- **Session:** 2026-27

## 1. Project Overview

Repair Workshop Job Card Manager is a beginner-level, menu-driven C++ console application. It is designed to maintain basic information about repair requests received by a workshop.

Each repair request is represented by an object of the `Job` class. A job card stores a unique job ID, customer name, phone number, repair item, estimated repair cost and job status.

The CA1 version stores records in a fixed-size array of 50 `Job` objects. It provides options to add a job card, display all saved job cards and search for a job card by ID.

## 2. CA1 Features

- Add a new repair job card.
- Display all job cards stored during the current program run.
- Search for a job card using its ID.
- Reject duplicate job IDs.
- Check that the ID is positive.
- Check that customer name, phone number and repair item are not empty.
- Reject a negative repair cost.
- Accept only `P`, `C` or `D` as the job status.
- Limit in-memory storage to 50 records.

### Job Status

| Code | Meaning |
|---|---|
| `P` | Pending |
| `C` | Completed |
| `D` | Delivered |

## 3. C++ Concepts Demonstrated

The CA1 source code demonstrates the following concepts from Units I and II:

- **Class and objects:** `Job` is the main class; individual job cards are objects.
- **Encapsulation:** Job data members are private and are accessed through class functions.
- **Static data member:** `cnt` stores the total number of accepted job cards.
- **Static member function:** `getCount()` returns the shared record count.
- **Inline function:** `setStatus()` assigns the status of a job.
- **Friend function:** `showCount()` displays the private static counter.
- **Array of objects:** `Job arr[50]` stores up to 50 job cards.
- **Pointer to objects:** `Job *ptr = arr` is used to access the array records.
- **`this` pointer:** The `add()` function uses `this` to assign values to the current object.
- **`string`:** Customer name, phone number and repair item are stored as strings.
- **Call by reference:** `search(Job arr[], int &x)` receives the search ID by reference.
- **Control statements:** A `do-while` loop and `switch-case` statement control the menu.

## 4. Menu Options

When the program runs, the user sees these options:

1. Add New Job Card
2. Display All Job Cards
3. Search Job Card By ID
4. Exit

Select an option by entering its menu number.

## 5. Storage and CA1 Limitations

**Important:** CA1 uses in-memory storage only. The program does not save records to a file or database. All job cards are lost when the program is closed.

The maximum capacity is 50 records in one execution. File handling and permanent storage are planned for CA2. Update and Delete operations are not part of the CA1 menu.

The CA1 version does not implement constructors or destructors, file streams, inheritance, operator overloading, dynamic memory allocation, STL containers or exception handling. These topics are reserved for later phases.

## 6. Folder Structure

Use the following repository structure:

```text
Repair-Workshop-Job-Card-Manager/
|
|-- docs/
|   |-- CA1_Proposal.docx
|   |-- UML_Diagram
|   |-- Flowchart
|   |-- Viva_Guide
|
|-- src/
|   |-- main.cpp
|
|-- data/
|
|-- tests/
|   |-- CA1_Test_Cases
|
|-- README.md
```

The `data/` folder is reserved for future phases. The CA1 program does not create or use a data file.

## 7. How to Compile and Run

### Option A: Dev-C++

1. Open Dev-C++.
2. Select **File → New → Source File**.
3. Paste the CA1 source code into the editor.
4. Save the file as `main.cpp` inside the `src` folder.
5. Select **Execute → Compile & Run** (or press `F11`, depending on your Dev-C++ setup).
6. Follow the menu shown in the console window.

### Option B: g++

Open a terminal in the project folder and compile:

```bash
g++ -std=c++11 -Wall -Wextra -pedantic src/main.cpp -o main
```

Run on Windows:

```bash
main.exe
```

Run on Linux or macOS:

```bash
./main
```

## 8. CA1 Test Cases

| Test case | Input / condition | Expected result |
|---|---|---|
| Normal input | Enter a new positive ID and valid job details. | The job card is added and can be displayed. |
| Duplicate ID | Enter an ID that is already stored. | The program rejects the new record and does not increase the record count. |
| Negative / invalid value | Enter a negative ID, non-numeric ID or negative cost. | The program asks for valid input. |
| Empty list read | Select Display All before adding any job card. | The program displays a no-records message. |
| Boundary test | Try to add a 51st job card after storing 50 records. | The program reports that storage is full and does not write outside the array. |

## 9. Planned Development Roadmap

The later phases are planned upgrades to this same project. They are not implemented in the CA1 version.

### CA1 – Design & Create (Day 7, Units I–II)

- Create the `Job` entity class.
- Use static, inline and friend functions.
- Use an array of objects, object pointers, the `this` pointer and reference parameters.
- Implement in-memory Create and Read operations.
- Prevent duplicate job IDs.

### CA2 – Constructors and File Handling (Day 14, Unit III)

- Add default, parameterized and copy constructors.
- Add a destructor.
- Add binary file handling using `fstream`.
- Use `seekg` for searching and `seekp` for updating records.
- Make records available after the program is restarted.

### CA3 – Advanced OOP (Day 28, Units IV–V)

- Add a base class and two derived classes.
- Implement operator overloading, including `<<`, `>>`, `==`, `<` and one additional operator.
- Demonstrate type conversion.
- Use `new` and `delete`.
- Add virtual functions and a virtual destructor.
- Implement Update and Delete with user confirmation.

### CA4 – Advanced C++ (Day 42, Unit VI)

- Complete the CRUD menu.
- Add `try`, `catch`, `throw` and a custom exception class.
- Demonstrate function and class templates.
- Use STL `vector` and `list` with algorithms such as `sort`, `find_if` and `count_if`.
- Add CSV export and backup functionality.

## 10. Academic Integrity and AI Assistance

This is an individual academic project. The student is responsible for understanding, testing and being able to explain every line of the submitted program during the viva and demonstration.

AI assistance may be used for learning, clarification and drafting only where permitted by the course instructions. Any AI assistance or external reference used must be disclosed in the format required by the faculty. The student should review and independently verify the source code, make any required changes, and never claim to have implemented features that are not present in the submitted version.

## 11. Build and Test Checklist

- [ ] Confirm the student name and roll number in the project documents.
- [ ] Save the source code as `src/main.cpp`.
- [ ] Compile the program without errors.
- [ ] Test adding a valid job card.
- [ ] Test duplicate ID rejection.
- [ ] Test invalid and negative inputs.
- [ ] Test displaying an empty list.
- [ ] Test searching for an existing and a missing ID.
- [ ] Test the 50-record capacity limit.
- [ ] Be prepared to explain the class, static member, inline function, friend function, pointers, `this` pointer and duplicate-checking loop.

---

**Project:** Repair Workshop Job Card Manager  
**Course:** CAP455 – Object-Oriented Programming using C++  
**Current phase:** CA1 – Design & Create
