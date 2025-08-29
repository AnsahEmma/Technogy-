<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduManage - Education Management System</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #4a6da7;
            --secondary: #7b9acc;
            --accent: #f47a60;
            --light: #f5f5f5;
            --dark: #333;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
        }
        
        body {
            background-color: #f8f9fa;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 1.5rem;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            transition: opacity 0.3s;
        }
        
        .nav-links a:hover {
            opacity: 0.8;
        }
        
        .auth-buttons {
            display: flex;
            gap: 1rem;
        }
        
        .btn {
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: white;
        }
        
        .btn-secondary {
            background-color: var(--secondary);
            color: white;
        }
        
        .btn-accent {
            background-color: var(--accent);
            color: white;
        }
        
        .btn-success {
            background-color: var(--success);
            color: white;
        }
        
        .btn-danger {
            background-color: var(--danger);
            color: white;
        }
        
        .btn:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }
        
        .hero {
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%234a6da7" opacity="0.1"/><path d="M0 0L100 100" stroke="%234a6da7" stroke-width="2" opacity="0.2"/></svg>');
            padding: 3rem 0;
            text-align: center;
            margin-bottom: 2rem;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto;
            color: var(--dark);
        }
        
        .dashboard {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }
        
        .sidebar {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .sidebar h3 {
            margin-bottom: 1rem;
            color: var(--primary);
            border-bottom: 2px solid var(--secondary);
            padding-bottom: 0.5rem;
        }
        
        .sidebar-menu {
            list-style: none;
        }
        
        .sidebar-menu li {
            margin-bottom: 0.5rem;
        }
        
        .sidebar-menu a {
            color: var(--dark);
            text-decoration: none;
            display: block;
            padding: 0.5rem;
            border-radius: 4px;
            transition: all 0.3s;
        }
        
        .sidebar-menu a:hover, .sidebar-menu a.active {
            background-color: var(--secondary);
            color: white;
        }
        
        .main-content {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .section-title {
            margin-bottom: 1.5rem;
            color: var(--primary);
            border-bottom: 2px solid var(--secondary);
            padding-bottom: 0.5rem;
        }
        
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }
        
        .card {
            background: linear-gradient(135deg, #f5f5f5, #e0e0e0);
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .card h3 {
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        .card p {
            color: var(--dark);
        }
        
        .stats {
            display: flex;
            justify-content: space-around;
            margin-bottom: 2rem;
        }
        
        .stat-item {
            text-align: center;
            padding: 1rem;
        }
        
        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary);
        }
        
        .stat-label {
            color: var(--dark);
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 2rem;
        }
        
        th, td {
            padding: 0.75rem;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        
        th {
            background-color: var(--secondary);
            color: white;
        }
        
        tr:hover {
            background-color: #f5f5f5;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        input, select, textarea {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }
        
        .modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            width: 100%;
            max-width: 500px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.2);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .close {
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        footer {
            background-color: var(--dark);
            color: white;
            padding: 2rem 0;
            margin-top: 2rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }
        
        .footer-section h3 {
            margin-bottom: 1rem;
            color: var(--secondary);
        }
        
        .footer-bottom {
            text-align: center;
            margin-top: 2rem;
            padding-top: 1rem;
            border-top: 1px solid #555;
        }
        
        @media (max-width: 768px) {
            .dashboard {
                grid-template-columns: 1fr;
            }
            
            .nav-links {
                display: none;
            }
            
            .card-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav>
                <div class="logo">EduManage</div>
                <ul class="nav-links">
                    <li><a href="#" class="active">Dashboard</a></li>
                    <li><a href="#">Students</a></li>
                    <li><a href="#">Courses</a></li>
                    <li><a href="#">Faculty</a></li>
                    <li><a href="#">Grades</a></li>
                    <li><a href="#">Attendance</a></li>
                </ul>
                <div class="auth-buttons">
                    <button class="btn btn-primary" id="loginBtn">Login</button>
                    <button class="btn btn-secondary" id="registerBtn">Register</button>
                </div>
            </nav>
        </div>
    </header>

    <div class="hero">
        <div class="container">
            <h1>Comprehensive Education Management System</h1>
            <p>Streamline student information, course management, grades, and attendance in one unified platform</p>
        </div>
    </div>

    <div class="container">
        <div class="dashboard">
            <div class="sidebar">
                <h3>Main Menu</h3>
                <ul class="sidebar-menu">
                    <li><a href="#" class="active">Dashboard</a></li>
                    <li><a href="#">Student Management</a></li>
                    <li><a href="#">Course Catalog</a></li>
                    <li><a href="#">Gradebook</a></li>
                    <li><a href="#">Attendance Tracking</a></li>
                    <li><a href="#">Faculty Management</a></li>
                    <li><a href="#">Reports & Analytics</a></li>
                    <li><a href="#">Settings</a></li>
                </ul>
            </div>

            <div class="main-content">
                <h2 class="section-title">Dashboard Overview</h2>
                
                <div class="stats">
                    <div class="stat-item">
                        <div class="stat-number">1,248</div>
                        <div class="stat-label">Total Students</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">64</div>
                        <div class="stat-label">Faculty Members</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">42</div>
                        <div class="stat-label">Courses</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">96%</div>
                        <div class="stat-label">Attendance Rate</div>
                    </div>
                </div>

                <h3 class="section-title">Recent Activities</h3>
                <div class="card-grid">
                    <div class="card">
                        <h3>New Registrations</h3>
                        <p>15 new students registered this week</p>
                    </div>
                    <div class="card">
                        <h3>Assignments Due</h3>
                        <p>7 assignments due in the next 3 days</p>
                    </div>
                    <div class="card">
                        <h3>Upcoming Events</h3>
                        <p>Annual Science Fair on October 15</p>
                    </div>
                </div>

                <h3 class="section-title">Student Performance</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Student ID</th>
                            <th>Name</th>
                            <th>Course</th>
                            <th>Grade</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>S1001</td>
                            <td>John Smith</td>
                            <td>Mathematics</td>
                            <td>A</td>
                            <td>Excellent</td>
                        </tr>
                        <tr>
                            <td>S1002</td>
                            <td>Emily Johnson</td>
                            <td>Physics</td>
                            <td>B+</td>
                            <td>Good</td>
                        </tr>
                        <tr>
                            <td>S1003</td>
                            <td>Michael Brown</td>
                            <td>Chemistry</td>
                            <td>A-</td>
                            <td>Very Good</td>
                        </tr>
                        <tr>
                            <td>S1004</td>
                            <td>Sarah Williams</td>
                            <td>Biology</td>
                            <td>C+</td>
                            <td>Needs Improvement</td>
                        </tr>
                    </tbody>
                </table>

                <button class="btn btn-accent" id="addStudentBtn">Add New Student</button>
            </div>
        </div>
    </div>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Login to System</h2>
                <span class="close">&times;</span>
            </div>
            <form id="loginForm">
                <div class="form-group">
                    <label for="username">Username</label>
                    <input type="text" id="username" placeholder="Enter your username" required>
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" placeholder="Enter your password" required>
                </div>
                <button type="submit" class="btn btn-primary">Login</button>
            </form>
        </div>
    </div>

    <!-- Add Student Modal -->
    <div class="modal" id="addStudentModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Add New Student</h2>
                <span class="close">&times;</span>
            </div>
            <form id="studentForm">
                <div class="form-group">
                    <label for="studentName">Full Name</label>
                    <input type="text" id="studentName" placeholder="Enter student's full name" required>
                </div>
                <div class="form-group">
                    <label for="studentEmail">Email</label>
                    <input type="email" id="studentEmail" placeholder="Enter student's email" required>
                </div>
                <div class="form-group">
                    <label for="studentCourse">Course</label>
                    <select id="studentCourse" required>
                        <option value="">Select a course</option>
                        <option value="math">Mathematics</option>
                        <option value="physics">Physics</option>
                        <option value="chemistry">Chemistry</option>
                        <option value="biology">Biology</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="studentYear">Year</label>
                    <select id="studentYear" required>
                        <option value="">Select year</option>
                        <option value="1">First Year</option>
                        <option value="2">Second Year</option>
                        <option value="3">Third Year</option>
                        <option value="4">Fourth Year</option>
                    </select>
                </div>
                <button type="submit" class="btn btn-success">Add Student</button>
            </form>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>EduManage</h3>
                    <p>Comprehensive education management system for institutions of all sizes.</p>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Contact Info</h3>
                    <p>Email: info@edumanage.com</p>
                    <p>Phone: +1 (555) 123-4567</p>
                    <p>Address: 123 Education Ave, Learning City</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 EduManage. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // DOM Elements
        const loginBtn = document.getElementById('loginBtn');
        const registerBtn = document.getElementById('registerBtn');
        const addStudentBtn = document.getElementById('addStudentBtn');
        const loginModal = document.getElementById('loginModal');
        const addStudentModal = document.getElementById('addStudentModal');
        const closeButtons = document.querySelectorAll('.close');
        const loginForm = document.getElementById('loginForm');
        const studentForm = document.getElementById('studentForm');

        // Open Modals
        loginBtn.addEventListener('click', () => {
            loginModal.style.display = 'flex';
        });

        addStudentBtn.addEventListener('click', () => {
            addStudentModal.style.display = 'flex';
        });

        // Close Modals
        closeButtons.forEach(button => {
            button.addEventListener('click', () => {
                loginModal.style.display = 'none';
                addStudentModal.style.display = 'none';
            });
        });

        // Close modal when clicking outside
        window.addEventListener('click', (e) => {
            if (e.target === loginModal) {
                loginModal.style.display = 'none';
            }
            if (e.target === addStudentModal) {
                addStudentModal.style.display = 'none';
            }
        });

        // Form Submissions
        loginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            // Simulate authentication
            if (username && password) {
                alert('Login successful! Welcome back.');
                loginModal.style.display = 'none';
            } else {
                alert('Please enter both username and password.');
            }
        });

        studentForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const name = document.getElementById('studentName').value;
            const email = document.getElementById('studentEmail').value;
            const course = document.getElementById('studentCourse').value;
            const year = document.getElementById('studentYear').value;
            
            // Simulate adding student
            if (name && email && course && year) {
                alert(`Student ${name} has been successfully added to the system.`);
                studentForm.reset();
                addStudentModal.style.display = 'none';
                
                // In a real application, we would add the student to the database
                // and update the UI accordingly
            } else {
                alert('Please fill out all fields.');
            }
        });

        // Simulated data for demonstration
        console.log('Education Management System Loaded');
        console.log('Simulating database operations...');
        
        // Simulated database tables
        const simulatedDatabase = {
            students: [
                { id: 'S1001', name: 'John Smith', email: 'john@example.com', course: 'Mathematics', year: 2, grade: 'A' },
                { id: 'S1002', name: 'Emily Johnson', email: 'emily@example.com', course: 'Physics', year: 3, grade: 'B+' },
                { id: 'S1003', name: 'Michael Brown', email: 'michael@example.com', course: 'Chemistry', year: 1, grade: 'A-' },
                { id: 'S1004', name: 'Sarah Williams', email: 'sarah@example.com', course: 'Biology', year: 4, grade: 'C+' }
            ],
            courses: [
                { id: 'C101', name: 'Mathematics', instructor: 'Dr. James Wilson', credits: 4 },
                { id: 'C102', name: 'Physics', instructor: 'Prof. Susan Lee', credits: 4 },
                { id: 'C103', name: 'Chemistry', instructor: 'Dr. Robert Davis', credits: 3 },
                { id: 'C104', name: 'Biology', instructor: 'Prof. Jennifer Miller', credits: 3 }
            ],
            faculty: [
                { id: 'F201', name: 'Dr. James Wilson', department: 'Mathematics', email: 'jwilson@example.com' },
                { id: 'F202', name: 'Prof. Susan Lee', department: 'Physics', email: 'slee@example.com' },
                { id: 'F203', name: 'Dr. Robert Davis', department: 'Chemistry', email: 'rdavis@example.com' },
                { id: 'F204', name: 'Prof. Jennifer Miller', department: 'Biology', email: 'jmiller@example.com' }
            ]
        };

        // Simulate SQL queries
        function simulateSQLQuery(query) {
            console.log(`Simulating SQL query: ${query}`);
            
            // Very basic simulation of query results
            if (query.includes('SELECT * FROM students')) {
                return simulatedDatabase.students;
            } else if (query.includes('SELECT * FROM courses')) {
                return simulatedDatabase.courses;
            } else if (query.includes('SELECT * FROM faculty')) {
                return simulatedDatabase.faculty;
            }
            
            return [];
        }

        // Example queries
        const allStudents = simulateSQLQuery('SELECT * FROM students');
        console.log('All students:', allStudents);
        
        const allCourses = simulateSQLQuery('SELECT * FROM courses');
        console.log('All courses:', allCourses);
        
        const allFaculty = simulateSQLQuery('SELECT * FROM faculty');
        console.log('All faculty:', allFaculty);
    </script>
</body>
</html>
