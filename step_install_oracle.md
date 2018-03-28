### [Python_Assignment](https://sudarshan-gurav.github.io/Assignment)---[Steps to Install MySQL](https://sudarshan-gurav.github.io/Install_step)---[Basic_Concept about Database](https://sudarshan-gurav.github.io/Basic_concept)---[Basic Syntax of MySQL](https://sudarshan-gurav.github.io/Basic_Syntax) --- [Library Management Project](https://sudarshan-gurav.github.io/Create_Insert) ---[Store Procedure in MySQL](https://sudarshan-gurav.github.io/store_procedure)---[Cursor in Store Procedure](https://sudarshan-gurav.github.io/cursor)---[steps to insatll oracle](https://sudarshan-gurav.github.io/step_install_oracle)---[Python_Basic](https://sudarshan-gurav.github.io/python)


## Steps Installing Oracle 11g R2 Express Edition on Ubuntu 64-bit

**first we have to download zip file from oracle**
 
 *Link:*
 http://www.oracle.com/technetwork/products/express-edition/downloads/index.html
 
 **Step2:to Unzip Downloded file**
 
unzip oracle-xe-11.2.0-1.0.x86_64.rpm.zip

**Step3:Install the following packages :**
> *sudo apt-get update
> *sudo apt-get install alien libaio1 unixodbc vim

## Step4:Convert the .rpm package into .deb package :

 >   **sudo alien --scripts -d oracle-xe-11.2.0-1.0.x86_64.rpm

##  Step5:basically we use chkconfig command can also be used to activate and deactivate services

>  **sudo vim /sbin/chkconfig
 
 (copy and paste the following into the file )


          #!/bin/bash
          
          # Oracle 11gR2 XE installer chkconfig hack for Ubuntu
          
          file=/etc/init.d/oracle-xe
          
          if [[ ! `tail -n1 $file | grep INIT` ]]; then
          
          echo >> $file
          
          echo '### BEGIN INIT INFO' >> $file
          
          echo '# Provides: OracleXE' >> $file
          
          echo '# Required-Start: $remote_fs $syslog' >> $file
          
          echo '# Required-Stop: $remote_fs $syslog' >> $file
          
          echo '# Default-Start: 2 3 4 5' >> $file
          
          echo '# Default-Stop: 0 1 6' >> $file
          
          
          echo '# Short-Description: Oracle 11g Express Edition' >> $file
          
          echo '### END INIT INFO' >> $file
          
          fi
          
          update-rc.d oracle-xe defaults 80 01
  
  
  ## Step6: Save the above file (Esc -> :wq -> Enter ) provide appropriate execute privilege :
       
   >    *sudo chmod 755 /sbin/chkconfig
   
  
  ## Step6:Set the Kernel parameters :
   
   >   **sudo vim /etc/sysctl.d/60-oracle.conf 
   
    (Enter the following) 
    
             # Oracle 11g XE kernel parameters  
           
           fs.file-max=6815744  
           
           net.ipv4.ip_local_port_range=9000 65000  
           
           kernel.sem=250 32000 100 128 
           
           kernel.shmmax=536870912 
         
           save the file (Esc -> : ->wq ->enter
          
          
 ##  Step7:  Verify the change : 

>  **sudo cat /etc/sysctl.d/60-oracle.conf 
    
  ## Step8:restart services
    
  > **sudo service procps restart
  
  ## Step9: make some more required changes :
    
     1. sudo ln -s /usr/bin/awk /bin/awk 
  
     2. mkdir /var/lock/subsys  
    
     3. touch /var/lock/subsys/listener 

  
 ## Step10:we are ready to install Oracle 11gR2 XE. Go to the directory where we want to created the ubuntu package file  and enter following commands in terminal :


 >   **sudo dpkg --install oracle-xe_11.2.0-2_amd64.deb  

## Step11:

 >   **sudo /etc/init.d/oracle-xe configure 
 
        (enter config information and set password).
        
 ##  Step12:
 
 >    **pico ~/.bashrc set environment variables like java
 
          export ORACLE_HOME=/u01/app/oracle/product/11.2.0/xe
          export ORACLE_SID=XE
          export NLS_LANG=`$ORACLE_HOME/bin/nls_lang.sh`
          export ORACLE_BASE=/u01/app/oracle
          export LD_LIBRARY_PATH=$ORACLE_HOME/lib:$LD_LIBRARY_PATH
          export PATH=$ORACLE_HOME/bin:$PATH
          
  ## Step13: (These files are used to set environmental items for a users shell)
  
  >   **. ~/.profile  
  
  ##   Step13:Start the Oracle 11gR2 XE :

>   **sudo service oracle-xe start

##  Create your user :
   **start sqlplus and login as sys :**
   
>   **sqlplus sys as sysdba 



  
          

  
