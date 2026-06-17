# 📚 Library Management System

![Python](https://img.shields.io/badge/Python-3.7%2B-blue?logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-informational)
![License](https://img.shields.io/badge/License-MIT-green)

A desktop **Library Management System** built with Python and Tkinter. It supports two roles — **Admin** and **Borrower** — and handles a full book lifecycle: browsing, borrowing, and returning, with all data persisted to CSV files.

---

## ✨ Features

| Feature | Admin | Borrower |
|---|:---:|:---:|
| Login / Logout | ✅ | ✅ |
| Browse book catalogue | ✅ | ✅ |
| Search by title or author | ✅ | ✅ |
| Filter borrowed-only books | ✅ | ✅ |
| Borrow a book | ✅ | ✅ |
| Return a book | ✅ | ✅ (own books only) |
| Add a book | ✅ | ❌ |
| Remove a book | ✅ | ❌ |
| Register new borrowers | ✅ | ✅ (self-register) |
| Change own password | ✅ | ✅ |

---

## 🗂️ Project Structure

```
library-management-system/
├── main.py           # Entry point — launches the Tkinter window
├── ui.py             # All GUI screens and user interactions (LibraryUI)
├── book.py           # Book data model
├── user.py           # User & UserManager (auth, persistence)
├── file_manager.py   # CSV read/write for the book catalogue
├── books.csv         # Book catalogue (persisted data)
├── requirements.txt  # No third-party dependencies (stdlib only)
├── LICENSE
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.7 or higher** — [Download here](https://www.python.org/downloads/)
- `tkinter` is included with most Python distributions. If it's missing on Linux:
  ```bash
  sudo apt-get install python3-tk   # Debian/Ubuntu
  sudo dnf install python3-tkinter  # Fedora
  ```

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/library-management-system.git
cd library-management-system

# 2. (Optional) Create a virtual environment
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

# 3. No extra packages needed — run directly
python main.py
```

---

## 🔑 Default Credentials

An admin account is created automatically on first launch.

| Role | Username | Password |
|---|---|---|
| Admin | `admin` | `adminpass` |

> **⚠️ Security Note:** Change the default admin password after first login via the **Change Password** button.

New borrower accounts can be registered from the login screen using **Add Borrower**.

---

## 🖥️ Usage

1. **Login** with an existing account or register a new borrower.
2. **Browse** the catalogue — the left panel shows book details, the right panel shows availability.
3. **Search** by title or author using the search bar.
4. **Filter** borrowed books using the *Borrowed Only* checkbox.
5. **Borrow / Return** a book by selecting it in the list and clicking the corresponding button.
6. **Admin only** — Add or remove books from the catalogue.

---

## 🛠️ How It Works

- **Data persistence** is handled via CSV files (`books.csv`, `users.csv`).  
  `books.csv` is bundled with the repo (the catalogue). `users.csv` is generated at runtime and is excluded from version control.
- **Authentication** is handled in [`user.py`](user.py) — passwords are stored in plain text in `users.csv` (suitable for a local demo; see [Contributing](#-contributing) for improvement ideas).
- **Role-based access** is enforced throughout the UI in [`ui.py`](ui.py).

---

## 🤝 Contributing

Contributions are welcome! Here are some ideas for improvements:

- [ ] Hash passwords (e.g., using `bcrypt` or `hashlib`)
- [ ] Add due-date tracking and overdue alerts
- [ ] Migrate from CSV to a SQLite database
- [ ] Add unit tests (`pytest`)
- [ ] Paginate the book list for large catalogues

To contribute:
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
