Database Normalization
 - Structuring relational database 
 - To reduce data redundancy
 - To improve data integrity
 - To simplify queries
 
 Types:
 -1NF
 -2NF
 -3NF
 -BCNF
 
 
 1NF
 - Each column should have atomic values
 - Each column should contain values of same type
 - Each column should have Unique name for attributes/columns
 - Order of saving data does not matter
 
 Instance
   Employee_ph                      Employee_ph:
  345-567-6187, 431-098-9087 ---->  345-567-6187
                                    431-098-9087
 
 2NF
 -Should be in 1NF
 - No partial dependency should exist OR
 - No non-prime attribute is dependent on the proper subset of any candidate key of table
 - {teacher_id,subject,teacher_age} ------> {teacher_id,subject},{teacher_id, teacher_age}
 - Candidate key - {teacher_id,subject) Determining key (PK)
 
 3NF
 - Should be in 1 and 2NF
 - No transitive dependency OR
 - Transitive functional dependency of non-prime attribute on any super key should be removed.
 - {emp_id,emp_name,emp_zip,emp_state,emp_city,emp_district} -------> {emp_id,emp_name,emp_zip}, {emp_zip,emp_city,emp_state,emp_district}
 
 
 BCNF
 -Stricter form of 3NF (Also called 3.5NF)
 - Should be in 3NF
 - For every functional dependency X->Y, X should be the super key of the table
 - {emp_id,emp_nationality,emp_dept,dept_type,dept_no_emp} --------> {emp_id,emp_nationality}, {emp_dept,dept_type,dept_no_emp}, {emp_id,emp_dept}
 -BCNF as left side is a key
    - emp_id -> emp_nationality
    - emp_dept -> dept_type,dept_no_emp
 
 KEYS:
 Source: https://dba.stackexchange.com/questions/71924/what-is-the-difference-between-primary-key-and-super-key-in-dbms
 Book (BookID, BookName, Author)
 1. Superkey - set which has one or more attributes that are taken collectively and can identify attributes uniquely.Identify each tuple uniquely
    (BookID), (BookId,Bookname), (BookID, Author), (BookName,Author)
 2. Candidate key - minimal super key not having redundant attributes
    (BookId), (bookname, author)
 3. Primary key - Key used uniquely to identify the records. Designer picks the unique keys from candidate key
    (bookId)
    
  ER Diagram rules:
  * Composite attributes - tree like structure (Name- FN,LN,Mn)
  * Multivalued attributes - Double ellipse (many phone numbers)
  * Derived attribute - Dashed ellipse (
    
  Participation Constraints
  * Total Participation − Each entity is involved in the relationship. Total participation is represented by double lines. 
  * Partial participation − Not all entities are involved in the relationship. Partial participation is represented by single lines.

 
 
 
