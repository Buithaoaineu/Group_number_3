markdown
#  Employee Information Manager v1.0.0

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0%2B-orange)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

##  Table of Contents
- [Project Overview](#project-overview)
- [Installation & Setup](#installation--setup)
- [Running in VS Code](#running-the-vs-code)
- [Project Structure](#project-structure)
- [🔗 Quick Links](#-quick-links)

##  Project Overview

**Employee Information Manager** is a comprehensive database application developed as part of the **Introduction to Databases** course at **National Economics University**. The project addresses real-world HR data management problems by transforming unnormalized employee data into a robust **3NF database schema** with an intuitive **Python GUI application**.

##  Installation & Setup

### **Prerequisites**
- Python 
- MySQL Server 8.0 
- VS Code with Python extension
- Git

### **Step 1: Cd to the folder and Clone Repository**
You can find instructions for [cloning or downloading this repository here](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository), then unzip the repository.

If you have Git installed, follow these steps:

1. Open Git Bash or PowerShell on your computer.
2. Navigate to the folder where you want to save the project (for example Desktop or Downloads):
```
bash
cd ~/Desktop
```
```
powershell
cd "C:\Users\Laptop\Downloads"
```
3. Run the clone command:
``` 
git clone https://github.com/Buithaoaineu/Group_number_3.git
```
4. Open the project in VS Code:
- Start Visual Studio Code.
- Go to File → Open Folder....
- Select the folder where you just cloned the repository
 (For example,  C:\Users\Laptop\Desktop\Group_number_3
or C:\Users\Laptop\Downloads\Group_number_3).
- Click Select folder

### **Step 2: Install Dependencies**
After opening the project folder in VS Code, install the required dependencies:

In the VS Code terminal or Git Bash/PowerShell, type the command:
```
pip install -r requirements.txt
```
### **Step 3: Configure MySQL Database**
- Open MySQL Workbench or the VS Code MySQL extension.
- Go to File → Open SQL Script...
- Click the folder where you just cloned the repository -> select schema.sql  
- Run the `schema.sql` file first to create the tables.  
- Then repeat the same process with `seed.sql` to insert sample data.

### ⚠️ Important Note Before Running

Before running the program, you need to update the file path for `database.csv` in the `load_data` function:
```python
def load_data(self):
    """Load and preprocess data from database.csv"""
    try:
        # Load the database.csv file
        self.data = pd.read_csv('C:\\Users\\Laptop\\...\\database.csv')
        print(f"Successfully loaded database.csv")
        print(f"Total records: {len(self.data)}")
```
How to update the path:
1. Locate the database.csv file in your project.
2. Right-click the file → select Copy path.
3. Open **dashboard.py** → scroll to **def load_data(self):**.
4. Paste the copied path into the code above, replacing 'C:\\\Users\\\YourPath\\\database.csv'.
5. **Important**: In Python, file paths must use double backslashes \\\ (e.g., C:\\\Users\\\Laptop\\\Documents\\\...).

## Running the VS Code
- Open employee_info_manager -> app -> main.py in VS Code
- Press F5 or click Run → Start Debugging
- Or run in terminal:
```
 python .\employee_info_manager\app\main.py
```

##  Project Structure

```
.vscode/               
├── launch.json 
employee-info-manager/ 
├── app/
│   ├── db/           
│   │   ├── connection.py             
│   ├── services/          
│   │   ├── crud_employees_service.py
│   │   ├── crud_departments_service.py
│   │   ├── crud_projects_service.py
│   │   └── crud_assignments_service.py
│   │   └── dashboard.py
│   │   └── database.csv
│   │   └── queries.py
│   │   └── search_filter.py
│   ├── ui/
│   │   ├── login_window.py                
│   │   ├── main_window.py
│   │   ├── employees_ui.py
│   │   ├── departments_ui.py
│   │   ├── projects_ui.py
│   │   ├── assignments_ui.py
│   │   ├── queries_inner.py
│   │   └── search_and_filter.py
│   │   └── export.py
|   ├── main.py
├── document/                    
│   ├── report.pdf/            
│   ├── slides.pdf/              
├── utils
│   ├── create_user.py
├── tests/
│   ├── __init__.py
│   ├── test_db.py
│   ├── test_services.py          
├── .env.example
├── .gitignore
.gitattributes
README.md            # This file
requirements.txt        
schema.sql               
seed.sql         
```

## 🔗 Quick Links

- 📂 GitHub Repository: [GitHub Repository](https://github.com/Buithaoaineu/Group_number_3)
- 🎥 Demo Video: [YouTube Demo](https://youtu.be/MmStJCzWH4w?si=LT9qPqY3Dzx7Qs9x)
- 📄 Full Report: [Download PDF Report](employee_info_manager/document/report.pdf) 
- 🎓 Presentation Slides: [Download PDF Slides](employee_info_manager/document/slides.pdf)
- 🐛 Issue Tracker: GitHub Issues

## Contact & Support

- 📧 Contact: nguyenhavy06032006@gmail.com
- 🏫 Institution: National Economics University
- 🎓 Course: Introduction to Databases
- 👨‍🏫 Instructor: Dr. Hung Tran
- 📅 Submission Date: December 2025

# Built with ❤️ for the Introduction to Database course.

