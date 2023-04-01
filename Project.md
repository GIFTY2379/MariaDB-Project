# Creating and connecting to a MariaDB DB instance


## In this project creates an EC2 instance and an RDS for MariaDB DB instance. The project shows you how to access the DB instance from the EC2 instance using a standard MySQL client. As a best practice, this project creates a private DB instance in a virtual private cloud (VPC). In most cases, other resources in the same VPC, such as EC2 instances, can access the DB instance, but resources outside of the VPC can't access it.

## The following diagram shows the configuration when the tutorial is complete.


![getting-started-mariadb](https://user-images.githubusercontent.com/69006353/227979043-e75d46b0-f050-45c0-9f8b-755157d5fd66.png)

# Create a MariaDB DB instance

## The basic building block of Amazon RDS is the DB instance. This environment is where you run your MariaDB databases.

## In this example, you use Easy create to create a DB instance running the MariaDB database engine with a db.t3.micro DB instance class.


# To create a MariaDB DB instance with Standard create

1. Sign in to the AWS Management Console and open the Amazon RDS console at https://console.aws.amazon.com/rds/.
   
2. In the upper-right corner of the Amazon RDS console, choose the AWS Region in which you want to create the DB instance.
   
3. In the navigation pane, choose Databases.
   
4. Choose Create database and make sure that Standard create is chosen.
   
5. In Configuration, choose MariaDB.
   
6. For DB instance size, choose Free tier.
   
7. For DB instance identifier, enter database-1
   
8. For Master username, enter a name for the master user, or keep the default name.
   

## The Create database page should look similar to the following image.

<img width="1440" alt="1" src="https://user-images.githubusercontent.com/69006353/227982190-31119b9c-4db6-4aa7-9d8f-593486352d20.png">
<img width="1440" alt="2" src="https://user-images.githubusercontent.com/69006353/227982343-5a01732f-0d87-4521-bc08-b11af054d1b6.png">

## To use an automatically generated master password for the DB instance, select Auto generate a password.

## To enter your master password, make sure Auto generate a password is cleared, and then enter the same password in Master password and Confirm password.

## The Create password page should look similar to the following image.

<img width="1440" alt="3" src="https://user-images.githubusercontent.com/69006353/227983100-ce96f3ee-01ca-4269-8ce8-c1e71a323c58.png">
<img width="1440" alt="4" src="https://user-images.githubusercontent.com/69006353/227983228-c638a2f2-f5cf-4732-9942-2a07c7e88113.png">


## Choose Create database.

## To view the master username and password for the DB instance, choose View credential details.

## You can use the username and password that appears to connect to the DB instance as the master user. In the Databases list, choose the name of the new MariaDB DB instance to show its details.

## The DB instance has a status of Creating until it is ready to use.

## Wait for the Region & AZ value to appear. When it appears, make a note of the value because you need it later. In the following image, the Region & AZ value is us-east-1b.

## Same as these picture



<img width="1440" alt="5" src="https://user-images.githubusercontent.com/69006353/227984441-0f2fc83b-8a65-4cf4-befa-059fdfd6933b.png">
<img width="1440" alt="6" src="https://user-images.githubusercontent.com/69006353/227984713-13ac77eb-d89e-4e1e-b519-e39d71bb2ccc.png">
<img width="1440" alt="7" src="https://user-images.githubusercontent.com/69006353/227984941-0f3d188a-b4f4-4e1a-bf8e-4b3ef4333e0b.png">
<img width="1440" alt="8" src="https://user-images.githubusercontent.com/69006353/227985173-9d7b650d-2e74-4055-b064-c1b7115a81de.png">

<img width="1440" alt="9" src="https://user-images.githubusercontent.com/69006353/227985273-e2cff858-0803-4573-b7a2-6635e3607f5b.png">
<img width="1440" alt="10" src="https://user-images.githubusercontent.com/69006353/227985397-c2a1171b-dcbf-4055-b5c7-1987661172a2.png">

# How To Create a MARIADB Database, Tables and Insert Data

How do I create a MARIADB database, tables, and insert (store) data into newly created tables?

MARIADB is a free and open source database management system. You need to use sql commands to create database. You also need to login as mysql root user account. To create a database and set up tables for the same use the following sql commands:


```
$ sudo apt update -y
```
```
$ sudo apt install mariadb
```
```
$ mysql -h endpoint -P 3306 -u admin -p
```

# After you enter the password for the user, you should see output similar to the following.

<img width="1440" alt="Screenshot 2023-03-15 at 07 23 09" src="https://user-images.githubusercontent.com/69006353/227995688-766c6873-8186-43fb-bc74-3ad73697d9af.png">


# Procedure for creating a database and a sample table

## Login as the mysql root user to create database:

```
$ mysql -u root -p
```
## Sample outputs:

```
mysql>
```

## Add a database called books, enter:

```
$ mysql> CREATE DATABASE books;
```

## You should see output similar to the following.

<img width="327" alt="Screenshot 2023-03-15 at 08 11 30" src="https://user-images.githubusercontent.com/69006353/228004497-70570de8-5b8b-43d2-9528-c82d0abd8c47.png">

## Now, database is created. Use a database with use command, type:

```
$ mysql> USE books;
```

## You should see output similar to the following.

<img width="327" alt="Screenshot 2023-03-15 at 08 13 20" src="https://user-images.githubusercontent.com/69006353/228005217-3b6d65ad-62f0-422d-904f-f44a32147c77.png">


## Next, create a table called authors with name, email and id as fields:

```
$ mysql> CREATE TABLE authors (id INT, name VARCHAR(20), email VARCHAR(20));

```
## You should see output similar to the following.

<img width="615" alt="Screenshot 2023-03-15 at 08 15 31" src="https://user-images.githubusercontent.com/69006353/228006065-7d5ca064-6ece-44af-a34f-891376fe9a17.png">

## To display your tables in books database, enter:

```
$ mysql> SHOW TABLES;
```

## Sample outputs:

<img width="389" alt="Screenshot 2023-03-15 at 07 56 24" src="https://user-images.githubusercontent.com/69006353/228006933-371ebb37-6429-4d40-9339-e19ec495b954.png">


## Finally, add a data i.e. row to table books using INSERT statement, run:

```
$ mysql> INSERT INTO authors (id,name,email) VALUES(1,"Vivek","xuz@abc.com");
```

## Sample outputs:

Query OK, 1 row affected (0.00 sec)

Try to add few more rows to your table:


```
$ mysql> INSERT INTO authors (id,name,email) VALUES(2,"Priya","p@gmail.com");
$ mysql> INSERT INTO authors (id,name,email) VALUES(3,"Tom","tom@yahoo.com");
```

### To display all rows i.e. data stored in authors table, enter:

```
$ mysql> SELECT * FROM authors;
```

## Sample outputs:

<img width="1440" alt="13" src="https://user-images.githubusercontent.com/69006353/228050153-d27ffb29-0d65-4bac-a41c-1c01416ad4cb.png">

<img width="1440" alt="14" src="https://user-images.githubusercontent.com/69006353/228050449-4bda576f-61cf-4a98-8720-9b06c542e5ec.png">

<img width="1440" alt="15" src="https://user-images.githubusercontent.com/69006353/228050698-d44e87a3-6c9c-4fe0-bcd6-8a3e2fa4b437.png">

<img width="1440" alt="16" src="https://user-images.githubusercontent.com/69006353/228050820-a5ae6f0b-e410-4357-9278-0079b5592dfe.png">

<img width="1440" alt="17" src="https://user-images.githubusercontent.com/69006353/228051053-a329a7ab-9312-45af-92fc-dd3c57e5ed68.png">

<img width="1440" alt="18" src="https://user-images.githubusercontent.com/69006353/228051227-95237f89-dadb-4c2a-96b3-82c9cbadcc2f.png">


# Congratulations! You have finished your very first MARIADB PROJECT
