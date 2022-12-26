![](https://media.giphy.com/media/MdA16VIoXKKxNE8Stk/giphy-downsized.gif)
# DBA Review


## *What is Database ?*
A set of logically related data with a description. 
## *What is DBA ?* 🔥
**Database administration** is the process of establishing computerized databases, and insuring their ``recoverability``, ``integrity``, ``security``, ``availability``,``reliability``, and ``performance``.

## *What is DBMS ?* 🔥
The software that manages the access to the database.it enables users to *define, create, and maintain* the database and provides controlled access to it.
>- Define = DDL (Database Definition Language)
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

🔥 **The system Catalog** It is called sometime DATA DICTIONARY the catalog stores data about the data (meta-data). 

**Recovery** Restore the DB to the consistent state after the event of failure.

**Integrity** Data and update on data should follow the constraints (rule)


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

`Database Administrators (DBA)` 🔥

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

## What is a database view 🔥
A view is a subset of the database, presented to one user or set of users. 

## Mention the benefits using views :
1. They reduce complexity by letting users see the data in the way they want
2. They provide security by excluding data that some users should not see
3. They customize the appearance of the database, such as changing attribute names
4. They hide changes in the database and provide consistent view of the database to users.  
5. The also provide the program-data independence mentioned earlier .

## Table Spaces 
- What a Tablespace Is ? 🔥

Oracle divides a database into one or more logical storage units called tablespaces.

🔥Each **tablespace** <mark>consists of one or more files called</mark> **datafiles**. A **datafile**<mark> physically stores the data objects of the database</mark> such as tables and indexes on disk. 

In other words, Oracle logically stores data in the tablespaces and physically stores data in datafiles associated with the corresponding tablespaces.

![](https://www.oracletutorial.com/wp-content/uploads/2019/07/Oracle-tablespace.png)


A datafile can span multiple disks. The size of a
datafile is initially determined by the DBA upon creation. It can be as
large as the largest file permitted by the operating system. The configuration of the machine on which the database is running determines
exactly how the information in the datafile is distributed across the disk.

![](../photos/T-TS.png)

-  What Tablespaces used for ?


    - Control the storage size allocated for the database data.
    - Grant specific space quotas to the database users.
    - Control the availability of data by taking tablespaces online or offline (more on this later).
    - Improve the performance of the database by allocating data storage across devices.
    - Perform partial database backup or recovery.
	- configure the database such that database objects are separated, to reduce the amount of administration and physical disk I/O (input/output) necessary.
    - DBA ensure that problem areas will remain isolated and will not affect the entire database because of the use of tablespaces.

- Default tablespaces in Oracle

  -  The `SYSTEM` and `SYSAUX tablespaces store system-generated objects such as data dictionary tables. And you should not store any object in these tablespaces.
  - The `USERS` tablespace is helpful for ad-hoc users.
  - The `RBS` holds the undo data The RBS tablespace is used for roll-
back segments.
  - The `TEMP` is the temporary tablespace which is used for storing intermediate results of sorting, hashing, and large object processing operations.
The INDX tablespace is used to store index data. These naming conven-

- Tablespaces status 

  A tablespace can have one of two statuses: `ONLINE` or `OFFLINE`. When a tablespace is online, it is available to the database Instance. For example, data may be read from the datafiles associated with an online tablespace. When a tablespace is offline, it is not available for such activity.

- TableSpaces and Datafiles

 ![ts-df](../photos/TS-DF.png)
The relationship of tablespaces to `datafiles` in that `tablespaces` are logical space management structures that are composed of one or more disk or physical files. Oracle refers to these physical files as datafiles,
the files that hold the physical data contained in the objects in the tablespaces.
Again, one single tablespace can be composed of one or more datafiles.

## **Practical** 
## SQL Recap 

 ![image](https://lms.uop.edu.jo/fit/pluginfile.php/2683/mod_resource/content/0/SQL.png)

### Important SQL Oracle Data Types to remember:

 Oracle supplies the following built-in datatypes:

**`Character` datatypes**
* ``CHAR`` (size) Fixed-length character data of length size bytes
* ``(VARCHAR2 and VARCHAR) + (size)`` Variable-length character data.  

 **``NUMBER`` datatype** Variable-length numeric data. Maximum precision p and/or scale s is 38.  

 **``DATE`` datatype**  Fixed-length date and time data, ranging from Jan. 1, 4712 B.C.E. to Dec. 31, 4712 C.E.  

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


### How to create a User in oracle database
### ex: Create User (name: std4, password: s123) And Grant connect, resource to std4

```sql
Conn system/p2
Create user std4 identified by s123;
Grant connect,resource to std4;
```

Q: Connect with user std4 and Show all tables and views
 ```sql
 conn std4/s123
 Select * from tab;
```
### How to create a Table:
![imageCT-EX](../photos/CT-EX.png)

```sql 
Create table Major(
Mno number(5) primary key,
Mname varchar2(20) NOT NULL,
Mhour number(3)
);
```
```sql
Create table Student (
Sno number(10) primary key,
SName varchar(50) NOT NULL,
city varchar(15),
address varchar(100),
birhdate date,
gender char check (gender in ('M','F')),
Mno number(4),
avg number(2,3) check (avg between 0 and 4),
foreign key(Mno) References Major
);

/*If you started with the student Table you should not put the foreign key statement because the major table dose not exist yet you can create the student table first then the major table then Alter the student table with this statement*/
Alter Table Student Add Constraint Mno_fk foreign key(mno) References major(mno);
```
If there is any SQL Syntax that you don't understand you do't understand : 
visit this site [Oracle Tutorial](https://www.oracletutorial.com/getting-started/)

### How to Display Constraints for table student?
You need to use the user dictionary 
```sql
Select Constraint_name,status form user_constraints From Student;
```
The Results :

![](../photos/Re_se.png)

To Make those constraints more readable you can rename them by altering the table with something like this:

```sql
Alter table student rename constraint SYS_C004081 to sno_pk;
```
OR you consider that form before creating the table like this : 



```sql 
Create table Major(
Mno number(5) primary key,
Mname varchar2(20) NOT NULL,
Mhour number(3)
);
```
```sql
Create table Student (
Sno number(10) constraint Student_pk  primary key,
SName varchar(50) constraint Student_Name_nn NOT NULL,
city varchar(15),
address varchar(100),
birhdate date,
gender char constraint STD_gender_ck check (gender in ('M','F')),
Mno number(4),
avg number(2,3)constraint STD_AVG check (avg between 0 and 4),
constraint student_mno_fk foreign key(Mno) References Major
);
```
The Result: 

![](../photos/co-re.png)





![](https://media.giphy.com/media/Wsju5zAb5kcOfxJV9i/giphy.gif)






