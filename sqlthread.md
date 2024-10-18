# SQl joins
---
Join clause is used to combine rows from two or more tables, based on the related column.  
below are the tables and columns that will be used in the query

![image](/images/tbe%20moses.png)

#### tables orders  
![image](/images/tbe%20orders.png)

## Inner join
The INNER JOIN keyword selects all rows from both the tables as long as the condition is satisfied. This keyword will create the result-set by combining all rows from both the tables where the condition satisfies i.e value of the common field will be the same.

### syntax

```sql
SELECT  column_name(s)
FROM    table1
INNER JOIN table2                 
ON table1.column_name = table2.column_name;
``` 

where table1 is the first table and table2 the second table.
and matching_column is the column matching both the tables

### Example

```sql                               
SELECT *     
FROM table1 INNER JOIN table2
ON table1.column_name = table2.column_name;
```

![image](/images/inner%20joinf.png)

## Left join
The LEFT JOIN keyword returns all records from the left table (table1), and the matching records (if any) from the right table (table2).

### syntax

```sql
SELECT  column_name(s)
FROM    table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
``` 

where table1 is the first table and table2 the second table.    
and matching_column is the column matching both the tables  

### Example

```sql
SELECT *
FROM table1 LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

![image](/images/left%20join.png)
## Right join
The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records (if any) from the left table (table1).

### syntax

```sql  
SELECT  column_name(s)
FROM    table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

### example

```sql              
SELECT *
FROM table1 RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```
![image](/images/right%20join.png)

## Full join
The FULL JOIN keyword returns all records when there is a match in either left (table1) or right (table2) table.

### syntax

```sql  
SELECT  column_name(s)
FROM    table1
FULL JOIN table2
ON table1.column_name = table2.column_name;
```
### example

```sql  
SELECT *
FROM table1 FULL JOIN table2
ON table1.column_name = table2.column_name;
```
![image](/images/full%20join.png)

# ACID properties
 The ACID properties are meant for the transaction that goes through a different group of tasks, and there we come to see the role of the ACID properties.

## Atomicity
The term atomicity defines that the data remains atomic. It means if any operation is performed on the data, either it should be performed or executed completely or should not be executed at all. It further means that the operation should not break in between or execute partially. In the case of executing operations on the transaction, the operation should be completely executed and not partially.

## Consistency
The word consistency means that the value should remain preserved always. In DBMS, the integrity of the data should be maintained, which means if a change in the database is made, it should remain preserved always. In the case of transactions, the integrity of the data is very essential so that the database remains consistent before and after the transaction. The data should always be correct.

## Isolation
The term 'isolation' means separation. In DBMS, Isolation is the property of a database where no data should affect the other one and may occur concurrently. In short, the operation on one database should begin when the operation on the first database gets complete. It means if two operations are being performed on two different databases, they may not affect the value of one another. In the case of transactions, when two or more transactions occur simultaneously, the consistency should remain maintained. Any changes that occur in any particular transaction will not be seen by other transactions until the change is not committed in the memory.

## Durability

Durability ensures the permanency of something. In DBMS, the term durability ensures that the data after the successful execution of the operation becomes permanent in the database. The durability of the data should be so perfect that even if the system fails or leads to a crash, the database still survives. However, if gets lost, it becomes the responsibility of the recovery manager for ensuring the durability of the database. For committing the values, the COMMIT command must be used every time we make changes.  
Therefore, the ACID property of DBMS plays a vital role in maintaining the consistency and availability of data in the database.  
Thus, it was a precise introduction of ACID properties in DBMS. We have discussed these properties in the transaction section also.

# Normalization
Normalization is the process of organizing data in a database. It includes creating tables and establishing relationships between those tables according to rules designed both to protect the data and to make the database more flexible by eliminating redundancy and inconsistent dependency.

## 1. First normal form (1NF)
- Eliminate repeating groups in individual tables.
- Create a separate table for each set of related data.
- Identify each set of related data with a primary key.

## 2. Second normal form (2NF)
The 1NF only eliminates repeating groups, not redundancy. That’s why there is 2NF.
A table is said to be in 2NF if it meets the following criteria:
it’s already in 1NF
has no partial dependency. That is, all non-key attributes are fully dependent on a primary key.

## 3. Third normal form (3NF)
When a table is in 2NF, it eliminates repeating groups and redundancy, but it does not eliminate transitive partial dependency.  
This means a non-prime attribute (an attribute that is not part of the candidate’s key) is dependent on another non-prime attribute. This is what the third normal form (3NF) eliminates.  
So, for a table to be in 3NF, it must:  
- be in 2NF
- have no transitive partial dependency.

## 4. Fourth normal form (4NF)
The Fourth Normal Form (4NF) is a level of database normalization where there are no non-trivial multivalued dependencies other than a candidate key. It builds on the first three normal forms (1NF, 2NF, and 3NF) and the Boyce-Codd Normal Form (BCNF). It states that, in addition to a database meeting the requirements of BCNF, it must not contain more than one multivalued dependency.  
### Properties  
A relation R is in 4NF if and only if the following conditions are satisfied: 
1. It should be in the Boyce-Codd Normal Form (BCNF).
2. The table should not have any Multi-valued Dependency.  

A table with a multivalued dependency violates the normalization standard of the Fourth Normal Form (4NF) because it creates unnecessary redundancies and can contribute to inconsistent data. To bring this up to 4NF, it is necessary to break this information into two tables. 

## 5. Boyce-Codd Normal Form (BCNF)
Boyce–Codd Normal Form (BCNF) is based on functional dependencies that take into account all candidate keys in a relation; however, BCNF also has additional constraints compared with the general definition of 3NF.  

### Rules for BCNF
- Rule 1: The table should be in the 3rd Normal Form.  

- Rule 2: X should be a superkey for every functional dependency (FD) X−>Y in a given relation.  

Note: To test whether a relation is in BCNF, we identify all the determinants and make sure that they are candidate keys.






