markdown
#  Employee Information Manager v1.0.0

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0%2B-orange)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

##  Table of Contents
- [Project Overview](#project-overview)
- [Installation & Setup](#installation--setup)
- [Running in VS Code](#running-in-vs-code)
- [Project Structure](#project-structure)
- [Team & Contributions](#team--contributions)
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

1. **Open Git Bash or PowerShell** on your computer.
2. **Navigate to the folder** where you want to save the project (for example Desktop or Downloads):
```
bash
cd ~/Desktop
```
```
powershell
cd "C:\Users\Laptop\Downloads"
```
3. **Run the clone command**:
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
Open MySQL Workbench or VS Code MySQL extension
1. Open MySQL Workbench or the VS Code MySQL extension.  
2. Copy the content of both files: `schema.sql` and `seed.sql`.  
3. Run the `schema.sql` file first to create the tables.  
4. Then run the `seed.sql` file to insert sample data.
### **Step 4: Configure Environment Variables**
Create .env file in root directory:
```
env
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=employee_information_manager
DEBUG=True
```
### **Step 5: Initialize Database**
In VS Code terminal:
```
bash
# Import schema
mysql -u root -p employee_manager < database/schema.sql

# Load sample data
mysql -u root -p employee_manager < database/seed.sql
```
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
3. Paste the copied path into the code above, replacing 'C:\\\Users\\\YourPath\\\database.csv'.
4. Important: In Python, file paths must use double backslashes \\\ (e.g., C:\\\Users\\\Laptop\\\Documents\\\...).

## Running in VS Code
- VS Code Launch Configuration
Create .vscode/launch.json:
```
json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [

        {
            "name": "Run employee-info-manager",
            "type": "debugpy",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal"
        }
    ]
}
```
## Running the Application
- Open src/main.py in VS Code
- Press F5 or click Run → Start Debugging
- Or run in terminal:
```
python src/main.py
```
## VS Code Extensions Recommended
- Python: Microsoft Python extension
- MySQL: MySQL management tools
- GitLens: Git integration
- LaTeX Workshop: For report editing

##  Project Structure

```
text
employee-info-manager/
├── .vscode/               
│   ├── launch.json
│   └── settings.json
├── app/
│   ├── db/           
│   │   ├── connection.py
│   │   ├── schema.sql
│   │   └── seed.sql              
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
├── documentary/                    
│   ├── report.pdf/            
│   ├── slides.pdf/           
├── screenshot
│   ├── db1.png
│   ├── db2.png
│   ├── db3.png
│   ├── db4.png
│   ├── erd.png
├── utils
│   ├── create_user.py
├── tests/
│   ├── __init__.py
│   ├── test_db.py
│   ├── test_services.py          
├── .env.example
├── .gitignore
├── requirements.txt        
├── README.md               # This file
└── .gitattributes          
```

##  Team & Contributions
### Team members
1. Tran Phuong Oanh (11247338)

- Database normalization (UNF → 3NF)
- MySQL schema design
- Sample data generation
- ERD creation
- Dashboard visualizations
- Documentation and README
  
2. Bui Phuong Thao (11247353)

- Tkinter GUI design
- CRUD forms implementation
- Search and filter system
- UI/UX testing
- Responsive design
- Error handling
  
3. Nguyen Ha Vy (11247374)

- Database connection layer
- Business logic services
- Input validation
- Error handling
- Documentation and README
- Responsive design

## 🔗 Quick Links

- 📂 GitHub Repository: [GitHub Repository](https://github.com/Buithaoaineu/Group_number_3)
- 🎥 Demo Video: [YouTube Demo](https://youtu.be/MmStJCzWH4w?si=LT9qPqY3Dzx7Qs9x)
- 📄 Full Report: [Download PDF Report](employee_info_manager/documentary/report.pdf) 
- 🎓 Presentation Slides: [Download PDF Slides](employee_info_manager/documentary/slides.pdf)
- 🐛 Issue Tracker: GitHub Issues

## Contact & Support

- 📧 Contact: oanhtran020906@gmail.com
- 🏫 Institution: National Economics University
- 🎓 Course: Introduction to Databases
- 👨‍🏫 Instructor: Dr. Hung Tran
- 📅 Submission Date: December 2025

# Built with ❤️ for the Introduction to Database course.

