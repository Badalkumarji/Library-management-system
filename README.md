# 📚 Library Management System (DAA Project)

A desktop application built using **Python** and **Tkinter** to manage book borrowing and returning in a small-scale library. This project is a part of the **Design and Analysis of Algorithms Lab (24CAP-612)** and demonstrates the practical use of **stack and queue** data structures.

---

## 🧠 Project Overview

This Library Management System allows users to:
- Borrow and return books
- View lists of borrowed and returned books
- Search the status of a book
- Undo the last action using stack
- Use a queue-like concept for returned books

The GUI is built with **Tkinter** and styled using basic ttk elements to make it more user-friendly.

---

## 🎯 Objectives

- Simplify the borrowing and returning of books
- Use stack to implement undo functionality
- Simulate queue behavior for returned books
- Provide a simple, intuitive interface for users
- Introduce DAA concepts like stacks and queues through real-world application

---

## 💻 System Requirements

### Hardware
- Processor: Dual-core or higher
- RAM: 4 GB minimum
- Storage: 100 MB free space

### Software
- Python 3.x
- Tkinter (comes pre-installed with Python)
- OS: Windows, Linux, or macOS

---

## 🛠️ Technologies Used

| Component     | Technology       |
|---------------|------------------|
| Programming   | Python            |
| GUI Library   | Tkinter, TTK      |
| Dialog/Alerts | messagebox, simpledialog |
| Platform      | Cross-platform    |

---

## ⚙️ Functionalities

- 📕 **Borrow Book** – Mark a book as borrowed and track it
- 📘 **Return Book** – Update book status to available
- 🧾 **View Borrowed/Returned** – Display categorized lists
- 🔙 **Undo Last Action** – Use stack to reverse last operation
- 🔍 **Search Book Status** – Check availability of a book
- 🎨 **Interactive GUI** – Tkinter-based UI with buttons and status bar

---

## 💡 Core Concepts

### 🔁 Stack
Used to implement **Undo** feature for borrow and return actions.

### 🔃 Queue (Conceptual)
Returned books are displayed in the order they were returned, simulating a queue.

---

## 🧪 Sample Code Snippet

```python
# Undo Last Action Example
def undo_last_action(self):
    if not self.last_action_stack:
        messagebox.showinfo("Undo", "No actions to undo.")
        return

    action, book = self.last_action_stack.pop()
    if action == "borrow":
        self.borrowed_books.remove(book)
        self.book_status.pop(book, None)
    elif action == "return":
        self.returned_books.remove(book)
        self.book_status[book] = "Borrowed"
