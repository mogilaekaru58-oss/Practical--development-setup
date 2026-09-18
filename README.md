# Practical Development Setup: Flutter, Python, MySQL, and VS Code Integration

## Task 1: Flutter & Dart Environment Setup

### 1. Terminal Commands & Verification

Run:

    flutter doctor

Flutter Doctor is used to verify the Flutter development environment and required tools.

Example verification:

    [✓] Flutter
    [✓] Android toolchain
    [✓] VS Code
    [✓] Connected device

### 2. Create and Navigate Project

    flutter create my_first_app
    cd my_first_app
    flutter devices

### 3. Hot Reload vs Hot Restart

Hot Reload (r):
- Applies code changes to the running application.
- Rebuilds the widget tree.
- Usually preserves application state.
- Useful for UI and layout changes.

Hot Restart (R):
- Restarts the entire Flutter application.
- Resets application state.
- Useful when changes require a complete application restart.

---

## Task 2: MySQL Database Management

### 1 & 2. SQL Statements Execution

Connect to MySQL:

    mysql -u root -p

Create the database:

    CREATE DATABASE school;
    USE school;

Create the students table:

    CREATE TABLE students (
        id INT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100) NOT NULL,
        email VARCHAR(150) UNIQUE NOT NULL,
        enrolled_on DATE
    );

Insert student records:

    INSERT INTO students (name, email, enrolled_on)
    VALUES
    ('Alice Mwangi', 'alice@example.com', '2026-01-15'),
    ('Brian Ochieng', 'brian@example.com', '2026-01-17');

View the records:

    SELECT * FROM students;

### 3. Security Explanation

Using the MySQL root account directly from an application violates the principle of least privilege. If the application is compromised, an attacker could potentially gain access to other databases and administrative functions.

Create a restricted application user:

    CREATE USER 'appuser'@'localhost'
    IDENTIFIED BY 'StrongPassword123!';

Grant only the required permissions:

    GRANT SELECT, INSERT, UPDATE, DELETE
    ON school.* TO 'appuser'@'localhost';

Then apply the privileges:

    FLUSH PRIVILEGES;

---

## Task 3: Python Environment Setup

### 1, 2 & 3. Terminal Execution

Create and enter the project folder:

    mkdir python_setup_lab
    cd python_setup_lab

Create a virtual environment:

    python3 -m venv venv

Activate the virtual environment on macOS/Linux:

    source venv/bin/activate

For Windows:

    venv\Scripts\activate

Install the requests package:

    pip3 install requests

Verify installed packages:

    pip3 list

Create a requirements file:

    pip3 freeze > requirements.txt

The requirements.txt file records the Python packages and versions used by the project.

---

## Task 4: VS Code Configuration

### 1. Extension Installation

Install these VS Code extensions:

- Flutter
- Dart
- Python
- Pylance
- MySQL

### 2. Interpreter Selection

Open the Command Palette:

    Ctrl+Shift+P

Search for:

    Python: Select Interpreter

Select the Python interpreter from the virtual environment:

    python_setup_lab/venv/bin/python

On Windows:

    venv\Scripts\python.exe

### 3. Workspace Verification

Verify that VS Code shows the selected virtual environment in the status bar.

The integrated terminal should show:

    (venv)

This confirms that the Python virtual environment is active.

---

## Conclusion

This practical setup covers Flutter and Dart, MySQL database management, Python virtual environments, and VS Code configuration. These tools provide a foundation for developing and testing software applications.
