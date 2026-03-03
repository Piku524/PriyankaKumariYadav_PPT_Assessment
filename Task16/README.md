Task 16: RDS Database + SQL Workbench
Objective:
Create and connect to a managed RDS database and run basic SQL queries.

Steps:
AWS RDS → Create Database → MySQL / Aurora → Free Tier.

Set DB name, username, password, storage 20GB, Public access: Yes.

Allow MySQL traffic in Security Group.

Wait for Status = Available.

SQL Workbench → New Connection → Hostname: RDS Endpoint, Port: 3306, Username & Password.

Run queries: CREATE DATABASE TestDB;
USE TestDB;
CREATE TABLE Students(ID INT PRIMARY KEY, Name VARCHAR(50));
INSERT INTO Students VALUES(1,'Alice'),(2,'Bob');
SELECT * FROM Students;
