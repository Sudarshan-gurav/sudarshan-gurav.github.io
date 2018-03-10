### [Basic_Syntax](https://https://sudarshan-gurav.github.io/Basic_Syntax)---[Basic_Concept](sudarshn-gurav.github.i/Basic_concept) ---[Create_Table and Insert_Row](https://sudarshan-gurav.github.io/Create_Insert)---[Install_step](https://sudarshan-gurav.github.io/install_step)



  ### CREATE TABLE FOR LIBRARY_MANAGEMENT
  
  **CREATE TABLE FOR LIBRARY_MANAGEMENT**
  
      CREATE DATABASE library_managment;

   **USE DATABASE**
   
      USE library_managment ;

   **CREATE TABLES FOR LIBRARY_MANAGEMENT**
   
    CREATE TABLE member_details  
    (
       id INT PRIMARY KEY,
       first_name VARCHAR(255),
       last_name VARCHAR(255),
       mobile INT,
       email VARCHAR(255),
       address VARCHAR(255)
    ) ;

    CREATE TABLE book_stock
    (
       id INT PRIMARY KEY,
       name VARCHAR(255),
       quantity INT
    ) ;


    CREATE TABLE author
    (
        id INT PRIMARY KEY,
        name VARCHAR(255)
    ) ;

    CREATE TABLE book_authors
    (
        author_id INT,
        book_id INT,
    
        foreign key (author_id) references member_details(id),
        foreign key (book_id) references book_stock(id)
    ) ;


    CREATE TABLE log_table
    (

