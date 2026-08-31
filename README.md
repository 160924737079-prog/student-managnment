🎓 Student Management & CGPA Dashboard

A simple and interactive Student Management & CGPA Dashboard built using Python, Streamlit, SQLite, and Pandas.

This project allows users to manage student information, add subject-wise marks, calculate grades and SGPA, and view academic performance through an interactive dashboard.

📌 Features
👨‍🎓 Add new students
📋 View all registered students
🗑️ Delete students
📚 Add subject-wise marks
🎯 Automatically calculate grades
🧮 Calculate SGPA based on subject credits
🗑️ Delete subject marks
📊 View class average SGPA
🏆 View highest SGPA
📉 View lowest SGPA
📈 View SGPA distribution
💾 Store data using SQLite
🖥️ Interactive Streamlit interface
🛠️ Technologies Used
Technology	Purpose
🐍 Python	Application development
🎈 Streamlit	Web interface
🗄️ SQLite	Database management
🐼 Pandas	Data processing and display

📂 Project Structure
student-management-system/
│
├── app.py
├── database.py
├── calculations.py
├── requirements.txt
├── students.db
└── README.md

📄 File Description
File	Description
app.py	Main Streamlit application
database.py	Handles SQLite database operations
calculations.py	Handles grade and SGPA calculations
requirements.txt	Contains required Python packages
students.db	SQLite database created automatically
README.md	Project documentation

Note: students.db is automatically created when the application is run.

⚙️ Requirements

Before running the project, make sure you have:

Python 3.8 or higher
pip
VS Code
A web browser

SQLite comes included with Python.

📦 Installation
1. Open the Project in VS Code

Open the project folder in VS Code.

2. Open the VS Code Terminal

Go to:

Terminal → New Terminal

3. Create a Virtual Environment
Windows
python -m venv venv


Activate it:

venv\Scripts\activate

macOS / Linux
python3 -m venv venv


Activate it:

source venv/bin/activate

📥 Install Dependencies

Run:

pip install streamlit pandas


Or, if you have a requirements.txt file:

pip install -r requirements.txt

🚀 Run the Application

In the VS Code terminal, run:

streamlit run app.py


After running the command, Streamlit will start the application.

You should see something similar to:

Local URL: http://localhost:8501


Open the URL in your browser.

🖥️ Application Pages

The application contains three main sections.

📊 Dashboard

The Dashboard provides an overview of student performance.

It displays:

Total number of students
Class average SGPA
Highest SGPA
Lowest SGPA
Student performance table
SGPA distribution chart
👨‍🎓 Students

The Students page allows you to manage student records.

Add Student

You can enter:

Student Name
Email
Course
Semester

Available courses:

BBA
IT
BCA
B.Com
B.Sc
MBA
MCA
View Students

Displays all registered students in a table.

Delete Student

Allows you to delete a student.

When a student is deleted, their associated marks are also deleted.

📚 Marks & CGPA

The Marks & CGPA page allows you to:

Select a student
Add subjects
Enter marks
Enter credits
View grades
Calculate SGPA
Delete subject records
🎯 Grading System

The application uses the following grading system:

Marks	Grade	Grade Point
90 – 100	A+	10
80 – 89	A	9
70 – 79	B+	8
60 – 69	B	7
50 – 59	C	6
40 – 49	D	5
0 – 39	F	0
🧮 SGPA Calculation

SGPA is calculated using the credit-weighted grade points.

Formula
SGPA = Σ(Grade Point × Credits) / Σ(Credits)

Example
Subject	Marks	Grade Point	Credits
Mathematics	85	9	4
Programming	92	10	3
Database	75	8	3

Calculation:

SGPA = ((9 × 4) + (10 × 3) + (8 × 3)) / (4 + 3 + 3)

SGPA = 90 / 10

SGPA = 9.00

🗄️ Database

The project uses SQLite to store student and marks information.

Students Table

The students table contains:

Column	Type	Description
id	INTEGER	Unique student ID
name	TEXT	Student name
email	TEXT	Student email
course	TEXT	Student course
semester	INTEGER	Student semester
Marks Table

The marks table contains:

Column	Type	Description
id	INTEGER	Unique marks ID
student_id	INTEGER	Associated student ID
subject	TEXT	Subject name
marks	REAL	Marks obtained
credits	INTEGER	Subject credits
Database