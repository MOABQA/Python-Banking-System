
# **Bank Management System**  🧐💭

## **Introduction**  
This project is a software system designed to automate the functionalities of a bank. The purpose is to create a **Management Information System (MIS)** that manages customer entries, account creation, transactions, and loans while facilitating easy and efficient decision-making for bank officials. You can get more details in the document.

## **Objective**  
The project aims to:  
- Maintain all bank records and transactions systematically.  
- Provide a user-friendly command-line interface for database interaction.  
- Simplify critical banking operations using modern IT practices.  



## **Technology Stack**  
### **Frontend:**  
- **Python IDLE**: Used for coding and command-line-based platform development.  

### **Backend:**  
- **MySQL**: A robust relational database management system for managing records.  



## **Features**  
The system includes:  
- Customer account management (creation, updates, and deletion).  
- Deposits, withdrawals, and fund transfers.  
- Loan management (application, repayment).  
- Centralized and secure information storage and retrieval.  
- Generating transaction reports and maintaining account statuses.  


## **Setup Instructions**  
Follow these steps to set up the system on your machine:  

### **Prerequisites**  
- **Python 3.6 or later** installed on your machine.  
- **MySQL Server** installed and running.  
- **Required Python libraries:**  
  - `mysql-connector-python`  
  - `datetime`  
  - `random`  

To install the necessary libraries, run the following command in your terminal:  
```bash
pip install mysql-connector-python
```

### **Database Setup**  
1. **Create the Database**:  
   - Open MySQL Workbench or Command Line.  
   - Create a database named `bms` using the command:  
     ```sql
     CREATE DATABASE bms;
     ```

2. **Create Tables**:  
   Use the following SQL queries to set up the required tables in the `bms` database:  

   **Customer Details Table (`cdet`)**:  
   ```sql
   CREATE TABLE cdet (
       cid CHAR(5) PRIMARY KEY,
       name VARCHAR(25) NOT NULL,
       phone CHAR(10) NOT NULL,
       pan_card CHAR(10),
       address VARCHAR(50),
       email VARCHAR(25),
       account1 CHAR(10),
       account2 CHAR(10)
   );
   ```

   **Account Details Table (`acc`)**:  
   ```sql
   CREATE TABLE acc (
       acc_no CHAR(10) PRIMARY KEY,
       dos DATE NOT NULL,
       balance DECIMAL(30, 2) DEFAULT 0.00
   );
   ```

   **Login Table (`idp`)**:  
   ```sql
   CREATE TABLE idp (
       id CHAR(5) PRIMARY KEY,
       password VARCHAR(15) NOT NULL
   );
   ```

   **Loan Table (`loan`)**:  
   ```sql
   CREATE TABLE loan (
       acc_no CHAR(10) PRIMARY KEY,
       start DATE NOT NULL,
       stop DATE NOT NULL,
       amount DECIMAL(30, 2) NOT NULL
   );
   ```

   **Transactions Table (`tr`)**:  
   ```sql
   CREATE TABLE tr (
       acc_no CHAR(10),
       date DATE,
       time VARCHAR(10),
       withdraw VARCHAR(3),
       deposit VARCHAR(3),
       to_acc_no CHAR(10),
       amount DECIMAL(30, 2)
   );
   ```

3. **Set User Credentials**:  
   Update the script's `execute()` function with your MySQL username and password:  
   ```python
   co = m.connect(host='localhost', user='root', passwd='YOUR_PASSWORD', database='bms')
   ```

### **Run the System**  
1. Open your Python environment.  
2. Run the main script provided in the project file.  
3. On the initial screen, choose to **Login** or **Register**.  
4. Navigate through the system using the displayed dashboard.  



## **System Requirements**  
### **Hardware:**  
- PC with Intel i3 processor  
- Minimum 4GB RAM  

### **Software:**  
- Microsoft Windows 10  
- Python 3.6 or later  
- MySQL Server  



## **Limitations**  
- The system lacks the capability for actual physical currency management.  
- Security measures in the database may require enhancements to prevent breaches.  



## **Future Enhancements**  
- Modular expansion to add new features and improve security.  
- Enhanced user interface for better usability.  
