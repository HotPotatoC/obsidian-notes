# LEC - Session 2
Class: [[COMP6481001 - Database Design]]
Session: 2
Topics: 
Date: 2023-02-23
Lecturer: [[4th Semester/Lecturers/D6659 - EKO SETYO PURWANTO, S.Pd., M.Kom.]]

# Database System Development Lifecycle

The Database System Development Lifecycle is Inherently associated with the lifecycle of the information system.

## 1. Database Planning

**Finding a problem**: In this step we define mission statement for database system which is objectives for our database applications

**Objectives defined**: Once mission statement is defined, *mission objectives* are defined

**Support for objectives**: Each objective should i dentify a particular task that the database must support

Database planning should also include development of standards that govern:
- how data will be collected,
- how the format should be specified,
- what necessary documentation will be needed,
- how design and implementation should proceed.

## 2. System Definition

Describe scope and boundaries of database system and the major user views. User view defines what is required of a database system from perspective of:
- a particular job role (such as Manager or Supervisor) or
- enterprise application area (such as marketing, personnel, or stock control).

Database application may have one or more **user views**. User views means that there are multiple types of users seperated as roles that each has it's own permissions and limitations.

Identifying user views helps ensure that no major users of the database are forgotten when developing requirements for new system

User views also help in development of complex database system allowing requirements to be broken down into manageable pieces.

**Representation of a Database System withh Multiple User Views**

![[Pasted image 20230223100938.png]]

## 3. Requirements Collection and Analysis

Process of **collecting and analyzing information** about the part of organization to be suppoerted by the database system, and using this information to identify users' requirements of new system

**Information is gathered for each major user view including:**
- a description of data used or generated
- details of how data is to be used/generated
- any additional requirements for new database system.

## 3.1 Main Approaches

#### 3.1.1 Centralized Approach

![[Pasted image 20230223101327.png]]

#### 3.1.2 View Integration Approach

![[Pasted image 20230223101415.png]]

## 4. Database Design

Process of creating a design for a database that will support the enterprise's mission statement and mission objectvies for the required database system.

Main approaches include:
- Top-down
- Bottom-up
- Inside-out
- Mixed: uses both top-down and bottom-up

**Criteria to Produce an Optimal Data Model**
1. Structural validity
2. Simplicity
3. Expressibility
4. Nonredudancy
5. Shareability
6. Extensibility
7. Integrity
8. Diagrammatic representation

**Three phases of database design**

![[Pasted image 20230223101900.png]]

### 4.1 Conceptual Database Design

Process of constructing a model of the data used in an enterprise, independent of all physical considerations.

### 4.2 Logical Database Design

Process of constructing a model of the data used in an enterprise based on a specific data model (e.g. relational), but independent of a particular DBMS and other physical considerations.

### 4.3 Physical Database Design

Process of producing a description of the database implementation on secondary storage.

## 5. DBMS Selection

Selection of an appropriate DBMS to support the database system. Undertaken at any time prior to logical design provided sufficient information is available regarding system requirements

## 6. Application Design

Design of user interface and application programs that use and process the database.

## 7. Prototyping

Building working model of a database system

Purpose of prototyping:
- to identifty features of a system that work well, or are inadequate
- to suggest improvements or even new features
- to clarify the users' requirements
- to evaluate feasibility of a particular system design

## 8. Implementation

Physical realization of the database and application designs (DDL, 3GL or 4GL, DML)

## 9. Data conversion and loading

Transferring any existing data into new database and converting any existing applications to run on new database.

## 10. Testing

Process of running the database system with intent of finding errors.

Demonstrates that database and application programs appear to be working according to requirements.

Evaluation conducted against a usability specification. Examples of criteria include:
- Learnability;
- Performance;
- Robustness;
- Recoverability;
- Adaptability.

## 11. Operational Maintenance

Process of monitoring and maintaining database system following installation. Can be updating the system or upgrading it

Monitoring performance of system, if performance falls, may require tuning or reorganization of the database.
 