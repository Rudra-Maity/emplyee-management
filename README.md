# Employee Management System - Installation Guide

This is a complete Employee Management System built with CodeIgniter 3 and MySQL. Follow these steps to set up and run the application on your local environment using XAMPP.

## Prerequisites
- XAMPP (with PHP 7.3 or higher)
- Web browser

## Installation Steps

### 1. Download and Install XAMPP
If you don't have XAMPP installed, download it from [https://www.apachefriends.org/](https://www.apachefriends.org/) and follow the installation instructions.

### 2. Start Apache and MySQL Services
1. Open XAMPP Control Panel
2. Start Apache and MySQL services

### 3. Create Project Directory
1. Navigate to XAMPP's `htdocs` folder:
   - Windows: `C:\xampp\htdocs`
   - macOS: `/Applications/XAMPP/htdocs`
   - Linux: `/opt/lampp/htdocs`
2. Create a folder named `employee_management`
3. Extract/Copy all project files into this folder

### 4. Create Database
1. Open your web browser and go to `http://localhost/phpmyadmin`
2. Create a new database named `employee_management`
3. Import the database structure by either:
   - Importing the SQL file (if provided)
   - Or copy-paste the SQL code from the `database_structure.sql` file and execute it

### 5. Configure the Application
1. Open `application/config/config.php` 
2. Ensure the base_url is set correctly:
   ```php
   $config['base_url'] = 'http://localhost/employee_management/index.php';
   ```
3. Open `application/config/database.php` and ensure your database settings are correct:
   ```php
   'hostname' => 'localhost',
   'username' => 'root',
   'password' => '',
   'database' => 'employee_management',
   ```

### 6. Create Upload Directory
1. Create a directory named `uploads` in the root of your project
2. Ensure it has write permissions:
   - Windows: Right-click → Properties → Security → Edit → Add "Everyone" with write permissions
   - Linux/macOS: `chmod 777 uploads`

### 7. Access the Application
1. Open your web browser
2. Go to `http://localhost/employee_management`
3. You should see the login page

## Default Login Credentials
- Username: `admin`
- Password: `admin123`

## System Features
1. **User Authentication**
   - Secure login system
   - Session management

2. **Employee Management**
   - Add new employees
   - View employee list
   - Edit employee details
   - Delete employees

3. **Profile Picture Management**
   - Upload employee profile pictures
   - View employee profile pictures

## File Structure Overview
```
employee_management/
├── application/
│   ├── config/
│   │   ├── config.php
│   │   ├── database.php
│   │   └── routes.php
│   ├── controllers/
│   │   ├── Auth.php
│   │   └── Employee.php
│   ├── models/
│   │   ├── Employee_model.php
│   │   └── User_model.php
│   └── views/
│       ├── templates/
│       │   ├── header.php
│       │   └── footer.php
│       ├── login_view.php
│       ├── employee_list.php
│       ├── employee_add.php
│       └── employee_edit.php
├── uploads/
├── .htaccess
└── index.php
```

## Troubleshooting
1. **Database Connection Error**
   - Verify your MySQL service is running
   - Check database credentials in `database.php`
   - Ensure the database exists

2. **URL not working**
   - Make sure mod_rewrite is enabled in Apache
   - Check if .htaccess file is properly configured
   - Verify the base_url in config.php

3. **Upload Issues**
   - Ensure the 'uploads' directory exists and has proper write permissions
   - Check PHP file upload settings in php.ini

4. **Session Issues**
   - Make sure session directory has write permissions
   - Check if cookies are enabled in your browser

## Security Notes
- This system includes basic security features
- In a production environment, consider:
  - Using HTTPS
  - Setting stronger password hashing
  - Implementing rate limiting
  - Adding two-factor authentication

## Support
For any issues or questions, please contact the developer.

---
Enjoy using your new Employee Management System!
