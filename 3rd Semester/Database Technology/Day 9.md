# Day 9
Class: [[COMP6799001 - Database Technology]]
Session: 10
Topics: 
-   Complex Integrity Constraints in SQL
-   Designing Active Databases  
-   Triggers and Active Databases
Date: 2022-12-13
Lecturer: [[3rd Semester/Lecturers/D6659 - EKO SETYO PURWANTO, S.Pd., M.Kom.]]

# SQL Codes Variables

- 0 Statement executed successfully
- 100 = no more data available in query result
- < 0 = indicates some error has occurred

# SQLSTATE
- String of five characters
- '00000' = no error
- Other values indicate various errors or exceptions

# CURSOR
- Points to a single tuple (row) from result of query

# OPEN CURSOR command
- Fetches query result and sets cursor to a position before first row in result
- Becomes current row from cursor

# FETCH commands
- Moves cursor to next row in result of query

# DB Stored Procedures and Functions

- When database program is needed by several applications
- To reduce data transfer and communication cost between client and server in certain situations
- To enhance modelling power provided by `VIEW`s by allowing more complex types of derived data

# Techniques for database programming

- Database Applications
	- Host language (Java, C/C++, Python, etc.)
	- Data sublanguage (SQL)
- Interactive interface
	- Typed directly into a monitor (CLI)
- File of commands
	- Read commands directly from a file (.sql)
- Database Applications
	- May have a web interface (phpmyadmin)
- Embedding
	- Running database commands in a programming language
	- Precompiler or preprocessor to identify database statements for processing by the DBMS
- Using a library
	- Using a certain programming language to connect to DBMS to do certain read/write operations through APIs or using libraries
