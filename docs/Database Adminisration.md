> As a part of DBA this is a Review before the mid exam 

### What is Database ?
A set of related logically related data with a description. 
### What is DBA ?
Database administration is the process of establishing computerized databases, and insuring their recoverability, integrity, security, availability, reliability, and performance.
All this is done with someone called database Administrator.
### What is DBMS ?
The software that manages the access to the database.it enables users to *define, create, and maintain* the database and provides controlled access to it.
> - Define = DDL (Database Definition Language)
>-  Create = DML (Database Manipulation Language)
>-  Maintenance = (DCL/TCL)  like security, integrity, concurrency control, recovery control, and user-accessible catalog.

# SQL Recap 

 ![[Pasted image 20221214201822.png]]

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


