🎓 # Student Management & CGPA Dashboard

A simple Student Management System built with Python, Streamlit, SQLite, and Pandas.

The application allows you to manage student information, add subject marks, calculate SGPA based on credits, and view overall student performance through an interactive dashboard.

📌 Features
👨‍🎓 Add new students
📋 View all registered students
🗑️ Delete students
📚 Add subject-wise marks
🎯 Automatically calculate grades
📊 Calculate SGPA using subject credits
🗑️ Delete subject marks
📈 View SGPA distribution
📊 View class average, highest SGPA, and lowest SGPA
💾 Store all data locally using SQLite
🖥️ Simple and interactive Streamlit interface
🛠️ Technologies Used
Python – Application development
Streamlit – Web-based user interface
SQLite – Database management
Pandas – Data handling and display
📂 Project Structure
student-management-system/
│
├── app.py
├── database.py
├── calculations.py
├── students.db
└── README.md

Files Description
File	Description
app.py	Main Streamlit application
database.py	SQLite database operations
calculations.py	Grade and SGPA calculation functions
students.db	SQLite database file, created automatically
README.md	Project documentation
⚙️ Requirements

Make sure Python is installed on your system.

Install the required Python packages:

pip install streamlit pandas


SQLite is included with Python, so no separate SQLite installation is normally required.

🚀 How to Run
1. Clone or download the project

Download the project files to your computer.

2. Open the project directory
cd student-management-system

3. Install dependencies
pip install streamlit pandas

4. Start the application
streamlit run app.py


The application will open in your browser.

If it does not open automatically, Streamlit will display a local URL in the terminal.

🗄️ Database

The application uses SQLite to store data.

Two tables are created automatically:

students

Stores student information.

Column	Type	Description
id	INTEGER	Unique student ID
name	TEXT	Student name
email	TEXT	Student email
course	TEXT	Student course
semester	INTEGER	Current semester
marks

Stores subject-wise academic information.

Column	Type	Description
id	INTEGER	Unique marks ID
student_id	INTEGER	Associated student ID
subject	TEXT	Subject name
marks	REAL	Marks obtained
credits	INTEGER	Subject credits

The database is automatically created when the application starts.

🎯 Grading System

The application uses the following grading scale:

Marks	Grade	Grade Point
90–100	A+	10
80–89	A	9
70–79	B+	8
60–69	B	7
50–59	C	6
40–49	D	5
Below 40	F	0
🧮 SGPA Calculation

SGPA is calculated using subject credits:

SGPA = Σ(Grade Point × Credits) / Σ(Credits)


For example:

Subject	Marks	Grade Point	Credits
Mathematics	85	9	4
Programming	92	10	3
Database	75	8	3

The application calculates the weighted SGPA automatically based on these values.

🖥️ Application Pages
Dashboard

The dashboard displays:

Total number of students
Class average SGPA
Highest SGPA
Lowest SGPA
Student performance table
SGPA distribution chart
Students

The Students section provides:

Add Student – Add student details
View Students – Display all students
Delete Student – Remove a student and their associated marks
Marks & CGPA

The Marks & CGPA section allows you to:

Select a student
Add subject marks
Enter subject credits
View grades
Calculate current SGPA
Delete subject records
🔐 Data Storage

All information is stored locally in the students.db SQLite database.

The application uses parameterized SQL queries such as:

cursor.execute(
    "DELETE FROM marks WHERE id = ?",
    (mark_id,)
)


This helps prevent SQL injection when working with user-provided values.

📸 Usage Workflow
Start the Streamlit application.
Open the Students page.
Add a student.
Open Marks & CGPA.
Select the student.
Add subjects, marks, and credits.
View automatically calculated grades and SGPA.
Open the Dashboard to view overall performance.
🔮 Future Improvements

Possible improvements include:

✏️ Edit student details through the UI
✏️ Edit existing marks
🔎 Search and filter students
📥 Export student data to Excel/CSV
📄 Generate student report cards
🔐 Add login and authentication
📊 Add course-wise and semester-wise analytics
📈 Add CGPA calculation across multiple semesters
📱 Improve mobile responsiveness
☁️ Deploy the application online
👨‍💻 Author

Student Management & CGPA Dashboard

Built using Python, Streamlit, SQLite, and Pandas.

📄 License

This project is intended for educational and personal use. You may modify and extend it according to your requirements.