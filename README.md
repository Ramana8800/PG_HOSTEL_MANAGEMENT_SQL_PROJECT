# PG_HOSTEL_MANAGEMENT_SQL_PROJECT
# 🏨 PG Hostel Student Management System (SQL Project)

## 📌 Project Overview

The **PG Hostel Student Management System** is a beginner-friendly database project developed using MySQL. The main purpose of this project is to manage hostel room details, student information, rent payments, and visitor records in an organized way.

This project demonstrates how SQL can be used to store, retrieve, filter, and analyze data efficiently. It includes basic SQL queries, aggregate functions, joins, subqueries, views, indexes, and transaction management.

## 🎯 Objectives

- Manage student information and room allocations.
- Store room details and monthly rent.
- Track student rent payments and pending payments.
- Maintain visitor records.
- Retrieve useful information using SQL queries.
- Practice important SQL concepts for interviews and real-world database applications.

## 🛠️ Technologies Used

- **Database:** MySQL
- **Language:** SQL
- **Tool:** MySQL Workbench or any compatible MySQL client
- **Version Control:** Git and GitHub

## 🗂️ Database Structure

Database name: `pg_hostel_management`

The project contains four main tables:

### 1. Rooms

Stores hostel room information.

- `room_id` – Unique room ID
- `room_number` – Room number
- `room_type` – Single, Double, or Triple
- `capacity` – Maximum room capacity
- `monthly_rent` – Monthly rent amount
- `available_beds` – Number of available beds

### 2. Students

Stores student details.

- `student_id` – Unique student ID
- `student_name` – Student name
- `gender` – Student gender
- `phone` – Contact number
- `college` – College name
- `course` – Student course
- `room_id` – Associated room ID

### 3. Payments

Stores student payment details.

- `payment_id` – Unique payment ID
- `student_id` – Associated student ID
- `payment_date` – Date of payment
- `amount` – Payment amount
- `payment_status` – Paid or Pending
- `payment_month` – Month for which payment is recorded

### 4. Visitors

Stores visitor information.

- `visitor_id` – Unique visitor ID
- `student_id` – Associated student ID
- `visitor_name` – Visitor name
- `relationship` – Relationship with the student
- `visit_date` – Date of visit

## 🔗 Table Relationships

- One room can be associated with multiple student records, subject to room capacity.
- One student can have multiple payment records.
- One student can have multiple visitor records.

Primary keys uniquely identify records, while foreign keys establish relationships between tables.

## ✨ Key Features

- Database and table creation.
- Insertion of sample room, student, payment, and visitor data.
- Primary keys, foreign keys, and data validation constraints.
- Data filtering using `WHERE`, `BETWEEN`, `IN`, `LIKE`, and other operators.
- Sorting and limiting records using `ORDER BY` and `LIMIT`.
- Aggregate functions: `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()`.
- Grouping data using `GROUP BY` and `HAVING`.
- String functions: `UPPER()`, `LOWER()`, `CONCAT()`, and `LENGTH()`.
- Date functions: `CURDATE()`, `YEAR()`, `MONTH()`, and `DATEDIFF()`.
- Conditional logic using the `CASE` statement.
- Joins: `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, and `CROSS JOIN`.
- FULL OUTER JOIN simulation using `LEFT JOIN`, `RIGHT JOIN`, and `UNION`.
- Subqueries, `UNION`, and `UNION ALL`.
- Common Table Expressions (CTEs) and views.
- Index creation for student phone number searches.
- Transaction management using `START TRANSACTION`, `SAVEPOINT`, `COMMIT`, and `ROLLBACK`.

## 📊 Sample SQL Queries

### 1. Display All Students

```sql
SELECT * FROM Students;
```

### 2. Find Students with Pending Payments

```sql
SELECT DISTINCT s.student_name
FROM Students s
JOIN Payments p
    ON s.student_id = p.student_id
WHERE p.payment_status = 'Pending';
```

### 3. Display Student and Room Details

```sql
SELECT
    s.student_name,
    s.course,
    r.room_number,
    r.room_type,
    r.monthly_rent
FROM Students s
JOIN Rooms r
    ON s.room_id = r.room_id;
```

### 4. Count Total Students

```sql
SELECT COUNT(*) AS total_students
FROM Students;
```

### 5. Find the Second-Highest Room Rent

```sql
SELECT MAX(monthly_rent) AS second_highest_rent
FROM Rooms
WHERE monthly_rent < (
    SELECT MAX(monthly_rent)
    FROM Rooms
);
```

## 🚀 How to Run the Project

1. Install MySQL Server and MySQL Workbench, or use another compatible MySQL client.
2. Download or clone this repository.
3. Open the project SQL file in your MySQL client.
4. Execute the SQL script in the correct order.
5. The script creates the database, tables, sample records, and SQL queries.
6. Run individual queries to view and analyze the results.

**Note:** The script contains a database creation statement. If you run the project again, check whether the database or tables already exist. The script also includes transaction examples that modify sample payment records, so review those statements before executing them.

## 📚 SQL Concepts Practiced

This project covers beginner to intermediate SQL concepts:

- DDL – `CREATE`, `ALTER`, `DROP`
- DML – `INSERT`, `UPDATE`, `DELETE`
- DQL – `SELECT`
- Constraints and table relationships
- Filtering, sorting, and grouping
- Aggregate, string, and date functions
- Joins and subqueries
- CTEs and views
- Indexes and transactions

## 🎓 Learning Outcomes

Through this project, I gained practical knowledge of MySQL database design, table relationships, SQL query writing, data filtering, data analysis, and transaction management. I also practiced common SQL interview queries.

## 🔮 Future Enhancements

- Develop a web interface for hostel management.
- Add automatic room allocation and availability updates.
- Generate monthly rent reports.
- Add student registration and login.
- Implement payment reminders and visitor reports.

## 👨‍💻 Author

**Ramana Komati**

MCA Graduate | Learning Python Full Stack Development

- GitHub: [Ramana8800](https://github.com/Ramana8800)

## 📄 License

This project is created for educational and learning purposes. You may use it to practice SQL and database management.
