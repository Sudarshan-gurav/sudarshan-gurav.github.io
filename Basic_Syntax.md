### [Python_Assignment](https://sudarshan-gurav.github.io/Assignment)---[Steps to Install MySQL](https://sudarshan-gurav.github.io/Install_step)---[Basic_Concept about Database](https://sudarshan-gurav.github.io/Basic_concept)--- [Library Management Project](https://sudarshan-gurav.github.io/Create_Insert) ---[Store Procedure in MySQL](https://sudarshan-gurav.github.io/store_procedure)---[Cursor in Store Procedure](https://sudarshan-gurav.github.io/cursor)---[steps to insatll oracle](https://sudarshan-gurav.github.io/step_install_oracle)---[Python_Basic](https://sudarshan-gurav.github.io/python)

# Basic Syntax of MySQL:

schema in simple term schema is design of our database 
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
 
 **MySQL UPDATE statement is used to modify the existing records in a table.
 
 **MySQL ALTER statement is used to  add, modify, or drop/delete columns in a table.
 
1.RENAME TABLE:

Syntax:
  
  >  *  ALTER TABLE countries RENAME country_new;
  
E.g:

>   * ALTER TABLE old RENAME new;

2.Write a MySQL statement to add a column to the table.

> *  ALTER TABLE table_name
>  * ADD Column_name DATATYPE;

3.Write a MySQL statement to **add a columns as the first** column into the table.

Syntax: 

> *   ALTER TABLE table_name
> *   ADD col_name DATATYPE FIRST;

4.Write a MySQL statement to add a new column after specific column in the table.

Synatx:

>  ALTER TABLE table_name
>  ADD new_col DATATYPE  
>  AFTER specific_col;

5.Write a MySQL statement change the data type of the column in the table.

> * ALTER TABLE table_name
> * MODIFY col_name NEW_DATATYPE;

6.Write a MySQL statement to drop the column from the table.

>  * ALTER TABLE table_name
>  * DROP col_name;

7.Write a MySQL statement to change the name of the column old to new, keeping the data type and size same.

Syntax:

If data is not impoertant or thier is no data in this column we can change

> *  ALTER TABLE table_name
> *  DROP old_name,
> *  ADD new_name DATATYPE
> *  AFTER col_name; 

But If data is required and we want to change the name of column then use belwo:

Synatx:

> * ALTER TABLE table_name
> * CHANGE old_col_name new_col_name varchar(25);

8.Write a MySQL statement to add a primary key for the column in the table.

Syntax:

> * ALTER TABLE table_name
> * ADD PRIMARY KEY(Col_name);

 **MySQL DROP statement is used to
 
 **MySQL DELETE statement is used to delete existing records in a table.
 
 **
