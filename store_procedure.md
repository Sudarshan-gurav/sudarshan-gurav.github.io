## What is stored procedure in MySQL?

 store proceddure is same as our C,C++ program inside store procedure we can write bunch of code and 

1 stored procedures help increase the performance,provide code resuabilty and security. 
     
2 Stored procedures help reduce the traffic between application and database server because instead of sending multiple 

   statements, the application has to send only name and parameters of the stored procedure.
       
 3.They allow for variable declarations, flow control.
     
 4.MySQL5 has introduce the store procedure.
     
 5.Stored procedures are fast. MySQL server takes some advantage of caching, just as prepared statements do.
     
## What is Prepared Statement?
  
  **MySQL Prepared Statement usage**

   In order to use MySQL prepared statement, you need to use other three MySQL statements as follows:

  PREPARE – Prepare: At first, the application creates the statement template and send it to the DBMS. 
    
  Certain values are left unspecified, called parameters, *placeholders* or *bind* variables (labelled "?" below):

   INSERT INTO table_name (list_attributes) VALUES (?, ?);
    
   EXECUTE – Executes a prepared statement preparing by a PREPARE statement.
    
   DEALLOCATE PREPARE – Releases a prepared statement.
    
  **MySQL has default delimiter is (;) semicolon.**
   
  **Check the MySQL version:**
  
  >    *  SELECT VERSION();
  
   **Pick the Delimiter in Stored Procedure.**
  
   To change delimiter because a procedure can have many statements, and everyone must end with a semicolon.
        
 ```sql
    
               delimiter $$ ( $$ whatever we want)
    
 ```  
  our delimter is change.Now the default DELIMITER is "$$"
   
  **Execute simple MySQL Command to check delimiter is change or not:**
      
   >  *   select * from table_name $$ (default delimiter is change)
  
  **Create Procedure Syntax:**
  
  >   * CREATE PROCEDURE proc_name()
  
   **Call Pocedure:**
  
  >   * CALL proc_name $$
  
 **Drop Procedure**
  
  >  * DROP PROCEDURE proc_name$$
  
 **Use bunch of Statement Inside Stored Procedure.**
  
  **A compound statement is a block that can contain other blocks**
    
 ```sql
 
               CREATE PROCEDURE proc_name () 

               BEGIN      
              
                    declare_var;
                    declare_stmt;
                    queries;
                    statement_list : It represents one or more statements terminated by a semicolon(;);
                    control_stmt;
                    loops;
                    cursors;
                 
               END;
  ```
               
  **Declaring variables**

To declare a variable inside a stored procedure, we use the DECLARE  statement :
         
 >   *   DECLARE variable_name datatype(size) DEFAULT default_value;
     
  **Assigning variables**

Once you declared a variable, we can start using it. To assign a variable another value, you use the SET  statement, 
            for example:
           
  >  *    DECLARE var_name INT DEFAULT 0;
  >  *     SET var_name = 10;

  **If we declare a variable inside BEGIN .... END  block, it will be out of scope if the END is reached.**
        
  variable that begins with the @ sign is session variable.
           
## Parameters :

 CREATE PROCEDURE proc_name() : Parameter list is empty
    
 CREATE PROCEDURE proc_name (IN varname DATA-TYPE) :
    
  pass by value whatever changes we made to this varible inside the body of store procedure it will 
         
  not reflate the outside the store procedure in our calling program 
          
   which accept a number from the user.
        
  CREATE PROCEDURE proc_name (OUT varname DATA-TYPE) :  One output parameter
    
   CREATE PROCEDURE proc_name (INOUT varname DATA-TYPE) : both IN-OUT paramter 
    
    
 **ITERATE Statement**

ITERATE means "start the loop again". ITERATE can appear only within LOOP, REPEAT, and WHILE statements. 
     syntax :

>   *  ITERATE label;

**LEAVE statement**

LEAVE exits the program

>    *   LEAVE label; 

## Let see Some Simple Example of stored procedure that gives a basic idea about stored procedure.
 

  ```sql

          > DELIMITER $$
                  create procedure p1()
                   begin
                    select * from log_table;
                  end $$

            > call p1()$$      // call procedure

            >     output:
                  +--------+---------+------------+-------------+
                  | mem_id | book_id | issue_date | return_date |
                  +--------+---------+------------+-------------+
                  |      1 |       1 | 2018-01-10 | 2018-01-20  |
                  |      2 |       3 | 2018-01-05 | 2018-01-15  |
                  |      3 |       2 | 2017-12-10 | 2017-12-20  |
                  -----------------------------------------------
                  ----------------------------------------------------------------------------------------------------------------


               >    delimiter ;      //change delimiter

               >   delimiter $$      //set delimiter

                   create procedure p2(IN a integer)    // 
                  begin
                    set a=a+10;
                  end 
                   $$


                  > set @a=4$$               //set variable @a=4 


                  > call p2(@a)$$            //call procedure (pass the parameter)

                 > select @a$$
                 
                 +------+
                  | @a   |
                  +------+
                  |    4 |
                  +------+
                 
                 -----------------------------------------------------------------------------------------------------------


                 > create procedure p3(out b integer)    
                       begin 
                          set b=10;
                       end $$

                 > set @b=4$$

                 > select @b$$

                  +------+
                  | @b   |
                  +------+
                  |    4 |
                  +------+


                > call p3(@b)$$

                > set @b=23$$


                > select @b$$
                
                  +------+
                  | @b   |
                  +------+
                  |   23 |
                  +------+

                 > call p3(@b)$$


                 > select @b$$
                 
                  +------+
                  | @b   |
                  +------+
                  |   10 |
                  +------+
                  --------------------------------------------------------------------------------------------------------

                  >     create procedure even_odd(IN num integer)

                       begin 
                          if num % 2 = 0 then 
                             select 'even';
                          else
                             select 'odd';
                  	end if;
                         end $$

                  > call even_odd(10)$$

                              +------+
                              | even |
                              +------+
                              | even |
                              +------+
                  
                  -------------------------------------------------------------------------------

                >  create procedure prime(IN a integer )
                     begin 
                        declare num integer;             
                        declare count integer;
                        set num=2;
                        set count=0;
                           while num<=a/2 do
                             if a%num=0 then
                               set count=count+1;
                            end if;
                              set num=num+1;
                           end while;
                        if count=0 then
                            select 'num is prime';
                        else
                            select 'num is not prime';
                        end if;
                      
                    end $$
                
             >   OutPut :
             
             > call prime(2)$$
                        +--------------+
                        | num is prime |
                        +--------------+
                        | num is prime |
                        +--------------+
                        
                 > call prime(4)$$
                        +------------------+
                        | num is not prime |
                        +------------------+
                        | num is not prime |
                        +------------------+
                        

                > create procedure myproc()

                begin
                       SELECT * FROM table_name ;
                end$$

               > call myproc() 
               > it diplay the table that we selected.
               
               

                  ---------------------------------------------------------
              
 ```
