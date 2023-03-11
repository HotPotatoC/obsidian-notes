# LEC - Session 1
Class: [[COMP6481001 - Database Design]]
Session: 1
Topics: Introduction to Databases
Date: 2023-02-16
Lecturer: [[4th Semester/Lecturers/D6659 - EKO SETYO PURWANTO, S.Pd., M.Kom.]]

# Database

A collection of self-describing and integrated data files

- metadata
- data dictionary
- overhead data

## Database Approaches

- Data Definition Language (DDL)
- Data Manupulation Language (DML)
- Structured Query Language (SQL)
- Security System
- Integrity System
- Concurrency control system
- Backup & recovery system
- View mechanism

## Database Managemeny System (DBMS)

![[Pasted image 20230216100153.png]]

```
PropertyForRent (propertyNo, street. city, postcode, type, rooms, rent, ownerNo)
PrivateOwner (ownerNo, fName. IName. address, telNo)
Client (clientNo, fName. IName, address, telNo, pretType, maxRent)
Lease (leaseNo, propertyNo, clientNo, paymentMethod, deposit. paid, rentStart. rentFinish)
```

## DBMS Environment

- **Hardware**: Client-server architecture
- **Software**: DBMS, OS, network, application
- **Data**: Schema, subschema, table, attribute
- **People**: Data administrator & database administrator
- **Procedure**: start, stop, log on, log off, back up, recovery

## Advantages of DBMS

- Control Redundancy
- **Consistency**
- Integrity
- **Security**
- Concurrency control
- **Backup & Recovery**
- Data standard
- **More information**
- Data sharing & conflict control
- **Productivity & accessibility**
- Economy of scale
- **Maintenance**

## Limitations of DBMS

- Complexity
- Size
- Cost
	- Software
	- Hardware
	- Conversion
- Performance
- Vulnerability

# Exercise

Please explain about advantage and disadvantage of DBMS

Advantage:
- DBMS provides an easier way to access and manipulate data ex: using queries
- DBMS organizes data in a more structured way
- DBMS provides consistency and integrity to make sure the data is consistent and enforces data integrity rules such as constraints to prevent invalid data
- DBMS provides a secure way to store data with authentication mechanisms.
- DBMS also provide backup & recovery system

Disadvantage:
- DBMS can be more complex to setup and maintain
- DBMS can be more costly especially for large and compex systems
- DBMS can add performance overhead for accessing and manipulating data, especially with large datasets
- DBMS can be a source of security vulnerability if not setup correctly