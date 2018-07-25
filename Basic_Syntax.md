### [Back To Link Page..](https://sudarshan-gurav.github.io/link)

# Basic Syntax of MySQL:

**what is Schema**

**schema** in simple term schema is design of our database 
  if we want to create a large database then first we need to design our database schema 
  
 ## Example of schema:
     
  it contain:
      
   1.table names
     
   2.attributes
     
   3.data type
     
   4.details of key (primary or foriegn key)
     
   5.description
     
 **MySQL CREATE DATABASE this statement is used to create DATABASE in 
   MySql syntax:**
 
       CREATE DATABASE database_name ;
 
**MySQL USE statement is used to select database 
  MySql syntax :**
 
        USE database_name
 
**MySQL CREATE statement is used to create table in 
  MySql syntax :**
  
         CREATE TABLE table_name
         ( col_name data_type contrain,
           col_name data_type contarin,
         
           .
           .
           .
           col_name data_type contrain
           );
  
  **MySQL INSERT statement is used to insert record(s) or row(s) into a table.**
  
   > **1.if we want to INSERT values for specific columns:**
   
 **MySQL Syntax:**
        
        INSERT INTO table_name 
        ( 
          col_name1,
          col_name2,
        )
       VALUES
 
 **MySQL UPDATE statement is used to modify the existing records in a table.**
 
For a single table, the UPDATE statement updates columns of existing rows in the named table with new values. Specific columns 

can be modified using the SET clause by supplying new values for that column.

The WHERE clause can be used to specify the conditions those identify which rows to update. Without using WHERE clause, all rows 

are updated.

The ORDER BY clause is used to update the order that is already specified.

The LIMIT clause specifies a limit on the number of rows that can be updated. 
 
The UPDATE statement supports the following modifiers:

LOW_PRIORITY: Using LOW_PRIORITY keyword, execution of the UPDATE is delayed until no other clients are reading from the table

IGNORE : Using IGNORE keyword, the update statement does not abort even if errors occur during the update.

MySQL UPDATE with WHERE:

**MySQL UPDATE column can be used to update some specific columns**

Syntax:

        UPDATE table_name SET col_name WHERE col_name = 'value';
 
 
 **MySQL ALTER statement is used to  add, modify, or drop/delete columns in a table.**
 
**1.Rename Table rename the exiting table name:**

Syntax:
  
      ALTER TABLE countries RENAME country_new;
  
E.g:

      ALTER TABLE old RENAME new;

**2.Write a MySQL statement to add a column to the table.**

     ALTER TABLE table_name
     ADD Column_name DATATYPE;

**3.Write a MySQL statement to add a columns as the first  column into the table.**

Syntax: 

       ALTER TABLE table_name
       ADD col_name DATATYPE FIRST;

**4.Write a MySQL statement to add a new column after specific column in the table.**

Synatx:

      ALTER TABLE table_name
      ADD new_col DATATYPE  
      AFTER specific_col;

**5.Write a MySQL statement change the data type of the column in the table.**

      ALTER TABLE table_name
      MODIFY col_name NEW_DATATYPE;

**6.Write a MySQL statement to drop the column from the table.**

       ALTER TABLE table_name
       DROP col_name;

**7.Write a MySQL statement to change the name of the column old to new, keeping the data type and size same.**

Syntax:

If data is not impoertant or thier is no data in this column we can change

      ALTER TABLE table_name
      DROP old_name,
      ADD new_name DATATYPE
      AFTER col_name; 

But If data is required and we want to change the name of column then use belwo:

Synatx:

      ALTER TABLE table_name
      CHANGE old_col_name new_col_name varchar(25);

**8.Write a MySQL statement to add a primary key for the column in the table.**

Syntax:

      ALTER TABLE table_name
      ADD PRIMARY KEY(Col_name);


**9.Write a MySQL statement to add a primary key for a combination of columns.**

      ALTER TABLE locations
      ADD PRIMARY KEY(location_id,country_id);



 **MySQL DROP statement is used to remove rows from a table.**
 
Example: MySQL DELETE specific rows or records

Syntax:

           DELETE FROM table_name 
           WHERE column_name=row_name;
           
Example: MySQL DELETE all rows or records

Syntax:

          DELETE FROM Table_name;
          
Example: MySQL DELETE with ORDER BY for limited number of rows

Synatx:

          DELETE FROM newauthor 
          ORDER BY country DESC LIMIT  2;
          
 
 **MySQL DELETE statement is used to delete existing records in a table.**
 
 
 
 
**MySQL TRUNCATE table**

MySQL TRUNCATE TABLE statement is used to delete all the rows from a table. Apparently, this is similar to 'DELETE FROM <TABLE 

NAME>' statement,but they are quite different.

Difference between TRUNCATE and DELETE

   TRUNCATE 	                                                                                    DELETE

It is a DDL command (i.e. a command used to define      |||     It is a DML command (i.e. a command used for managing data) and can be 

.                                                             rolled back.

the database structure or schema) and once you have 

deleted the rows using it, 

you can not use the ROLLBACK to undo the task. 	

You can't use WHERE clause. 	                                                  You can use WHERE clause.

Faster than DELETE. 	                                                          Slower than TRUNCATE. 
