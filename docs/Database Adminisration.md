# DBA Review
## **Theory** 

## *What is Database ?*
A set of logically related data with a description. 
## *What is DBA ?*
**Database administration** is the process of establishing computerized databases, and insuring their ``recoverability``, ``integrity``, ``security``, ``availability``,``reliability``, and ``performance``.

## *What is DBMS ?*
The software that manages the access to the database.it enables users to *define, create, and maintain* the database and provides controlled access to it.
> - Define = DDL (Database Definition Language)
>-  Create = DML (Database Manipulation Language)
>-  Maintenance = (DCL/TCL)  like security, integrity, concurrency control, recovery control, and user-accessible catalog.
## The History of DBMS

### *First Generation DBMS*
- Hierarchical Model
- Network Model

### *Second Generation DBMS*

- relational model
- The extended relational model

### *Third Generation DBMS*
- Object Oriented DBMS and Object-Relational DBMS
- These are called 

## *Advantages of DBMSs* 
1.  Control of Data Redundancy
2. Data Consistency
3. Economy of scale
4. Sharing of data
5. Improved data integrity
6. Improved security
7. Improved Backup and Recovery Services
8. Increased Productivity
9. Increased Concurrency 
10. Improved Data Accessibility and Responsiveness

## *Disadvantages*
1. Complexity
2. Size
3. Cost

## Functions of a DBMS
<mark>**Data storage, retrieval, and update**</mark>
	A DBMS must provide users with the ability to store, retrieve, and update data in the database.  It should hide the internal physical implementation details from users

<mark>**A user-accessible catalog**</mark>
	A DBMS must provide a catalog in which descriptions of data items are stored and which is accessible to users.

**Transaction Support**
	<mark> A DBMS must furnish a mechanism that will ensure that either all updates corresponding to a given transaction are made or that none of them is made.</mark>  This is to prevent the database being in an inconsistent state.  A transaction is a series of actions, carried out by a single user, or a program that access or changes the contents of the database.

**Concurrency Control Services**
	A DBMS must furnish a mechanism to ensure that the database is updated correctly when multiple users are updating the database concurrently

**Recovery services**
A DBMS must furnish a mechanism for recovering the database in the event that the database is damaged in any way.

**Security services** A DBMS must furnish a mechanism to ensure that only authorized users can access the database.
	
**Support for data communication** A DBMS must be capable of integrating with communication software.


**Integrity services**
	A DBMS must furnish a means to ensure that both the data in the database and changes to the data follow a certain rules.

**Services to promote data independence**  DBMS must include facilities to support the independence of programs from the actual structure of the database.

**Utility services**
	A DBMS should provide a set of utility services. These are tools to help the DBA to administer the database effectively, such as import facilities, monitor facilities, statistical analysis programs, index reorganization facilities, and many others.

## *Some Definitions*      

**The system Catalog** It is called sometime DATA DICTIONARY the catalog stores data about the data (meta-data). 




## *What are the components of the DBMS Environment*
- Hardware
- Software
- Data 
- Procedures
- People  (Users) (Roles)

## Roles in the Database Environment DB USERS
- Database Administrators (DBA)
- Database Designers
- Application Programmers
- End-Users( Naïve , Sophisticated)



Responsibilities For different user types:

`Database Administrators (DBA)`

1. Manage Users( Create User , Grant and Revoke Privileges)
2. Defining Security & Integrity Checks 
3. Monitoring Performance 
4. Defining Backup / Recovery Procedures 
5. Setting System Parameters
6. Acquiring Hardware and Software 
7. Define DB Procedures , Triggers


`Database Designers`

1. Define DB Schema  (Structure , Types , Constraints)
2. Communicate with end user  and understand their needs


`Application Programmers`

N/A
 

`End-Users`: They are the clients for the database to serve their information needs.

- **Naïve users** : They do not need to know about the database;They access the database through simple application programs such as data entry.

- **Sophisticated users**: They are familiar with the structure of the database and the functionality of the DBMS.They use high-level query language, such as SQL.

### *DBA Responsibilities*:

**Defining the Schema**

The DBA defines the schema which contains the structure of the data in the application. The DBA determines what data needs to be present in the system ad how this data has to be represented and organized. 

**Liaising with Users**

The DBA needs to interact continuously with the users to understand the data in the system and its use. 

**Defining Security & Integrity Checks**

The DBA finds about the access restrictions to be defined and defines security checks accordingly. Data Integrity checks are also defined by the DBA.

**Defining Backup / Recovery Procedures**

The DBA also defines procedures for backup and recovery. Defining backup procedures includes specifying what data is to backed up, the periodicity of taking backups and also the medium and storage place for the backup data. 

**Monitoring Performance**

The DBA has to continuously monitor the performance of the queries and take measures to optimize all the queries in the application.

## *DBA Challenges*
- Ever Changing Technologies
- Never ending requests
- Urgency of a client’s demands for  data
- Need to maintain a secure, yet available database environment

## What is a database view
A view is a subset of the database, presented to one user or set of users. 



## Mention the benefits using views :
1. They reduce complexity by letting users see the data in the way they want
2. They provide security by excluding data that some users should not see
3. They customize the appearance of the database, such as changing attribute names
4. They hide changes in the database and provide consistent view of the database to users.  
5. The also provide the program-data independence mentioned earlier 




## **Practical** 
## SQL Recap 

 ![image](https://lms.uop.edu.jo/fit/pluginfile.php/2683/mod_resource/content/0/SQL.png)

### Important SQL Oracle Data Types to remember:

 Oracle supplies the following built-in datatypes:

  **character datatypes**
* ``CHAR`` (size) Fixed-length character data of length size bytes
* ``(VARCHAR2 and VARCHAR) + (size)`` Variable-length character data.  
* LONG  Variable-length character data.  

 **``NUMBER`` datatype** Variable-length numeric data. Maximum precision p and/or scale s is 38.  

 **``DATE`` datatype**  Fixed-length date and time data, ranging from Jan. 1, 4712 B.C.E. to Dec. 31, 4712 C.E.  


### How to create a Table:
```sql
Create table Student (
Sno number(10) primary key,
SName varchar(50),
city varchar(15),
address varchar(100),
birhdate date,
gender char check (gender in 'M'and 'F'),
Mno number (4),
avg number(2,3) check (avg between 0 and 4)
);
```


#### DML : 
```sql
insert into dept values(50,'Info Tech','Amman');

update emp set sal = 1000 , job = 'QA'
   where empno = 7369;

delete from emp where sal >= 2000;
```

#### DDL : 

```sql
alter table dept add office varchar2(40);

alter table dept modify office varchar2(60);

alter table dept drop column office;

alter table emp add constraint emp_sal_ck
      check(sal between 400 and 7000 ) ;

alter table emp disable constraint emp_sal_ck ;

alter table emp enable  constraint emp_sal_ck ;

alter table emp drop constraint emp_sal_ck;

Truncate table dept;

Drop table dept;
```


