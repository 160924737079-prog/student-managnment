# 🎓 Student Management & CGPA Dashboard

A modern and interactive **Student Management & CGPA Dashboard** built with **Python, Streamlit, SQLite, and Pandas**.

The application provides a centralized platform for managing student records, storing subject-wise marks, automatically calculating grades and SGPA, and visualizing overall academic performance through an intuitive dashboard.

---

## 📌 Overview

The **Student Management & CGPA Dashboard** is designed to simplify academic record management and performance analysis.

Administrators or faculty members can:

* 👨‍🎓 Register and manage students
* 📚 Add subject-wise academic marks
* 🎯 Automatically calculate grades and grade points
* 🧮 Calculate credit-based SGPA
* 📊 Analyze class performance
* 🏆 Identify highest and lowest SGPA
* 📈 Visualize SGPA distribution
* 🗑️ Delete students and subject records
* 💾 Persist data using SQLite

The project combines a lightweight database with an interactive Streamlit interface, making it easy to run locally without requiring a separate database server.

---

## ✨ Key Features

### 👨‍🎓 Student Management

* Add new students
* Store student name, email, course, and semester
* View all registered students
* Delete student records
* Automatically remove associated academic records when a student is deleted

### 📚 Marks & Academic Records

* Select a registered student
* Add subject-wise marks
* Enter subject credits
* Automatically determine grades
* Calculate grade points
* Delete individual subject records

### 🧮 SGPA Calculation

SGPA is calculated using a **credit-weighted grade point formula**:

> **SGPA = Σ(Grade Point × Credits) / Σ(Credits)**

This ensures that subjects with higher credits have a proportionally greater impact on the student's SGPA.

### 📊 Academic Dashboard

The dashboard provides a quick overview of class performance, including:

* Total number of students
* Class average SGPA
* Highest SGPA
* Lowest SGPA
* Student performance table
* SGPA distribution visualization

### 💾 Database Management

Student and academic information is stored locally using **SQLite**, eliminating the need for an external database server.

---

## 🖥️ Application Modules

The application is organized into three primary sections.

### 📊 1. Dashboard

Provides an overall summary of academic performance.

**Displays:**

* Total Students
* Average SGPA
* Highest SGPA
* Lowest SGPA
* Student performance
* SGPA distribution

---

### 👨‍🎓 2. Students

Used to manage student information.

#### Add Student

The following information can be entered:

| Field        | Description           |
| ------------ | --------------------- |
| Student Name | Name of the student   |
| Email        | Student email address |
| Course       | Academic program      |
| Semester     | Current semester      |

#### Available Courses

* BBA IT
* BCA
* B.Com
* B.Sc
* MBA
* MCA

#### View Students

Displays all registered students in an interactive table.

#### Delete Student

Allows administrators to remove a student.

When a student is deleted, their associated subject and marks records are also removed.

---

### 📚 3. Marks & CGPA

This module manages academic performance.

Users can:

1. Select a student
2. Add subjects
3. Enter marks
4. Enter subject credits
5. Automatically calculate grades
6. Calculate SGPA
7. View subject-wise academic records
8. Delete subject records

---

## 🎯 Grading System

The application uses the following grading scale:

|    Marks | Grade | Grade Point |
| -------: | :---: | ----------: |
| 90 – 100 |   A+  |          10 |
|  80 – 89 |   A   |           9 |
|  70 – 79 |   B+  |           8 |
|  60 – 69 |   B   |           7 |
|  50 – 59 |   C   |           6 |
|  40 – 49 |   D   |           5 |
|   0 – 39 |   F   |           0 |

---

## 🧮 SGPA Calculation

The application calculates SGPA using the credit-weighted grade point method.

### Formula

```text
SGPA = Σ(Grade Point × Credits) / Σ(Credits)
```

### Example

| Subject     | Marks | Grade Point | Credits |
| ----------- | ----: | ----------: | ------: |
| Mathematics |    85 |           9 |       4 |
| Programming |    92 |          10 |       3 |
| Database    |    75 |           8 |       3 |

Calculation:

```text
SGPA = ((9 × 4) + (10 × 3) + (8 × 3)) / (4 + 3 + 3)

SGPA = (36 + 30 + 24) / 10

SGPA = 90 / 10

SGPA = 9.00
```

**Final SGPA: 9.00**

---

## 🛠️ Technology Stack

| Technology   | Purpose                             |
| ------------ | ----------------------------------- |
| 🐍 Python    | Application development             |
| 🎈 Streamlit | Interactive web interface           |
| 🗄️ SQLite   | Local database management           |
| 🐼 Pandas    | Data processing and tabular display |

---

## 📂 Project Structure

```text
student-management-system/
│
├── app.py
├── database.py
├── calculations.py
├── requirements.txt
├── students.db
└── README.md
```

### 📄 File Description

| File               | Description                                 |
| ------------------ | ------------------------------------------- |
| `app.py`           | Main Streamlit application                  |
| `database.py`      | Handles SQLite database operations          |
| `calculations.py`  | Handles grade and SGPA calculations         |
| `requirements.txt` | Contains required Python packages           |
| `students.db`      | SQLite database containing application data |
| `README.md`        | Project documentation                       |

> **Note:** `students.db` is created automatically when the application is initialized.

---

## 🗄️ Database Structure

The application uses SQLite to store student and marks information.

### Students Table

| Column     | Type    | Description       |
| ---------- | ------- | ----------------- |
| `id`       | INTEGER | Unique student ID |
| `name`     | TEXT    | Student name      |
| `email`    | TEXT    | Student email     |
| `course`   | TEXT    | Student course    |
| `semester` | INTEGER | Student semester  |

### Marks Table

| Column       | Type    | Description           |
| ------------ | ------- | --------------------- |
| `id`         | INTEGER | Unique marks ID       |
| `student_id` | INTEGER | Associated student ID |
| `subject`    | TEXT    | Subject name          |
| `marks`      | REAL    | Marks obtained        |
| `credits`    | INTEGER | Subject credits       |

The `student_id` establishes the relationship between student records and their academic marks.

---

## ⚙️ Requirements

Before running the project, make sure you have:

* Python **3.8 or higher**
* pip
* VS Code
* A modern web browser

SQLite is included with standard Python installations.

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/student-management-system.git
```

Navigate into the project:

```bash
cd student-management-system
```

---

### 2. Create a Virtual Environment

#### Windows

```bash
python -m venv venv
```

Activate the environment:

```bash
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
```

Activate the environment:

```bash
source venv/bin/activate
```

---

### 3. Install Dependencies

Using `requirements.txt`:

```bash
pip install -r requirements.txt
```

Or install the packages manually:

```bash
pip install streamlit pandas
```

---

## 🚀 Running the Application

Start the Streamlit application using:

```bash
streamlit run app.py
```

After starting the application, Streamlit will provide a local URL similar to:

```text
Local URL: http://localhost:8501
```

Open the URL in your browser to access the dashboard.

---

## 🔄 Application Workflow

```text
                 ┌─────────────────────┐
                 │      Start App      │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   Student Records  │
                 └──────────┬──────────┘
                            │
                    Add / Manage Student
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Subject-wise Marks  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Grade Calculation   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   SGPA Calculation  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Performance         │
                 │ Dashboard           │
                 └─────────────────────┘
```

---

## 📸 Screenshots

Add screenshots of your application here to showcase the interface.

### Dashboard

```text
Add your dashboard screenshot here
```

### Student Management

```text
Add your student management screenshot here
```

### Marks & SGPA

```text
Add your marks and SGPA screenshot here
```

> **Tip:** Upload screenshots to a `screenshots/` folder and reference them using Markdown.

Example:

```markdown
![Dashboard](screenshots/dashboard.png)
```

---

## 🔐 Data Storage

This project uses a local SQLite database.

The database file:

```text
students.db
```

is used to store:

* Student information
* Subject records
* Marks
* Credits

No external database server is required.

For production deployment, sensitive or persistent database configuration should be handled appropriately.

---

## 🧪 Example Use Case

A faculty member can use the system to:

1. Register a student.
2. Select the student's course and semester.
3. Add all enrolled subjects.
4. Enter marks and credits.
5. Allow the system to calculate grades automatically.
6. Calculate the student's SGPA.
7. Review the student's academic performance.
8. Compare performance through the dashboard.

---

## 🔮 Future Enhancements

Potential improvements include:

* 📄 Generate student report cards as PDF
* 📊 Add CGPA calculation across multiple semesters
* 📥 Export student records to Excel/CSV
* 📧 Email student reports
* 🔐 Add authentication and role-based access
* 👨‍🏫 Faculty management
* 📱 Improve mobile responsiveness
* 📈 Add semester-wise performance analytics
* ☁️ Deploy the application online
* 🌐 Add cloud database support
* 🌓 Add dark/light theme support
* 🔍 Add advanced student search and filtering

---

## 🤝 Contributing

Contributions are welcome!

If you would like to improve this project:

1. Fork the repository.
2. Create a new branch.

```bash
git checkout -b feature/new-feature
```

3. Make your changes.
4. Commit your changes.

```bash
git add .
git commit -m "Add new feature"
```

5. Push the branch.

```bash
git push origin feature/new-feature
```

6. Open a Pull Request.

---

## 📜 License

This project is intended for **educational and academic purposes**.

You are free to modify and extend the project according to your requirements.

---

## 👨‍💻 Author

**Your Name**

Student Management & CGPA Dashboard
Built with ❤️ using **Python, Streamlit, SQLite & Pandas**

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

Your support helps motivate further development and improvements.

---

### 📌 Quick Start

```bash
git clone https://github.com/YOUR-USERNAME/student-management-system.git
cd student-management-system
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
streamlit run app.py
```

**Student Management & CGPA Dashboard — Simple. Interactive. Academic.**
