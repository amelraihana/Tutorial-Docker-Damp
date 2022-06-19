# Tutorial Docker Damp

## What is Docker?

Docker is an open source platform for building, deploying, and managing containerized applications.

It enables developers to build, deploy, run, update and manage containers—standardized, executable components that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.

Containers simplify development and delivery of distributed applications. They have become increasingly popular as organizations shift to cloud-native development and hybrid multicloud environments. It’s possible for developers to create containers without Docker, by working directly with capabilities built into Linux and other operating systems. But Docker makes containerization faster, easier and safer. 

## Installation steps and procedures

* Install and run Docker Desktop
https://www.docker.com/get-started
*  We will use Docker official images like PHP Apache, and MySQL. We will specify their parameters in a docker-compose.yml file. 

 ![](https://user-images.githubusercontent.com/107705027/174447896-8ae84c55-ff38-4e1e-b891-1b8d8fcbf6c6.jpeg)   
* Run docker-compose up in cmd to gather all the data, download the Apache server, build the image and run the container.
 
![docker-compose-up](https://user-images.githubusercontent.com/107705027/174448169-3e24c646-b626-4005-8055-e47ef9ce75fd.png)
![Screenshot (27)](https://user-images.githubusercontent.com/107705027/174451721-c8a8a9e7-0612-45ad-bd84-6a3a7d1bddc4.png)

* Open the Docker and check if it is running          

![docker-engine-container-running](https://user-images.githubusercontent.com/107705027/174448245-739e22f0-517a-4b93-a294-23dadc01e081.png)

 ![Screenshot (25)](https://user-images.githubusercontent.com/107705027/174451756-af5d92f0-bb33-4f25-bc93-f6a35e7af955.png)

* Make sure the container is configured to execute the PHP scripts by open your local host post -  http://localhost:8000/.

![apache-server-running](https://user-images.githubusercontent.com/107705027/174448291-aa4312f1-58b7-436c-b339-d06c8d35dbe7.png)
* The container is configured to execute some PHP code.


## Execute some PHP code and get the output in the browser
* In Docker, go to project directory ➙ ./php/src, create an index.php file        
                      
                      
![Screenshot (3)](https://user-images.githubusercontent.com/107705027/174448487-550818b9-facf-4196-8b8b-b6717701c06c.png)


## Setup a MySQL database
* In Docker,Setup Password authentication by using MYSQL_USER: MYSQL_USER and MYSQL_PASSWORD: MYSQL_PASSWORD to connect to MySQL and access the MYSQL_DATABASE: MYSQL_DATABASE.
* Restart policy set to restart: always.    
                      
![Screenshot (5)](https://user-images.githubusercontent.com/107705027/174448645-90e87c66-e4c0-4f17-b2cc-f0d385c5a976.png)
* Head to the /php folder, create a Docker file, name it Dockerfile and add the following PHP configurations.

![Screenshot (7)](https://user-images.githubusercontent.com/107705027/174448836-ca2f9674-bd48-4f8a-bacc-fce77840ba20.png)
* Build custom image inside php-apache service in the docker-compose.yml file. Configure by specifying a depends_on: environment.
* Example yml file              
                    
![Screenshot (10)](https://user-images.githubusercontent.com/107705027/174449253-2305257f-4ae1-4cbd-a34d-029418aa18c9.png)
* Run docker-compose up in cmd to pull and MySQL will be added to the container. 

![Screenshot (25)](https://user-images.githubusercontent.com/107705027/174451308-17586fb2-3e6d-4d4e-9aaf-8d688a464ad3.png)

## Run SQL query using PHP scripts
* Go to index.php file and input the following PHP MySQL connection code.                     
 
![Screenshot (12)](https://user-images.githubusercontent.com/107705027/174449532-dfcfa7f9-31b1-447d-8281-3a4a68b0cddd.png)

## Setting PHPMyAdmin
* Add a PHPMyAdmin service                  
 
![Screenshot (14)](https://user-images.githubusercontent.com/107705027/174449642-88b084ee-c5e2-4d62-ae6e-14c91177243c.png)
* Open http://localhost:8080/ on the browser to access the PHPMyAdmin.        
 
![Screenshot (16)](https://user-images.githubusercontent.com/107705027/174449691-90acb154-7dd1-4d0c-b54a-8fef555c7dbb.png)
* To login to the Phpmyadmin panel, use username as root and password as MYSQL_ROOT_PASSWORD. 
The password was already set in the MySQL environment variables (MYSQL_ROOT_PASSWORD: MYSQL_ROOT_PASSWORD)

![Screenshot (18)](https://user-images.githubusercontent.com/107705027/174449800-a490f2d1-fa35-49f9-9816-00cf7fcae3d7.png)

## Fill in the records and print them on a PHP website
* Create database table and fill in some records. Select the database and execute the following query.

![phpadmin](https://user-images.githubusercontent.com/107705027/174450385-145f79a9-966c-4f6f-845b-78022b9cb5e0.jpeg)

![list](https://user-images.githubusercontent.com/107705027/174451391-f95f4728-58d5-486d-a68b-ba5e90830fb3.jpeg)


 * Write an SQL SELECT query with PHP.       
                
  ![Screenshot (21)](https://user-images.githubusercontent.com/107705027/174450547-2426b39a-bb43-4718-99dc-c6693f302674.png)
  * Refresh http://localhost:8000/ to view the result.  
                        
![Screenshot (23)](https://user-images.githubusercontent.com/107705027/174450614-e96610d5-5fc8-4ad9-8b47-92d7038c9655.png)

The end.

* This tutorial is made by 

Name | Matric Number
------------ | -------------
Muhammad Haikal Bin MD Shariff | 1928873
Amelia Raihana Binti Azhan  | 2016258
Siti Sarah Binti Rosman | 2021128
