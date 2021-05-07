

Technologies used:

1. java 8
2. spring boot 2.4.5 with (spring-security,spring-web,validation,mysql-connector) dependancies.
3.jjwt 0.9.1
4.Mysql

Required IDEs and Tools:

1.eclipse or intellij
2.postman for api testing
3.Xammp for local web server


Project structure:

Controllers package:
controllers handle signup/login requests & authorized requests.
which includes following java files:
1.AuthController.
2.TestController.

Models Package:
includes three enum:
1.ERole
2.Role
3.User

defines two main models for Authentication (User) & Authorization (Role). They have many-to-many relationship.

Respository:
 has intefaces that extend Spring Data JPA JpaRepository to interact with Database.
include following interface:
1.UserRepository
2.RoleRepository 

UserRepository extends JpaRepository<User, Long>
RoleRepository extends JpaRepository<Role, Long>

Payload Package:
defines classes for Request and Response objects.

We also have application.properties for configuring Spring Datasource, Spring Data JPA and App properties (such as JWT Secret string or Token expiration time).

pom.xml containes dependencies

How to run :

1.import project (i.e Assignment) as existing maven porject in eclipse or intellij.
2.Run AssignmentApplication.java file as java application.
note: no need to start tomcat server
3.start phpmyadmin local server.
4.create database with name assignmentdb with username = User and password = 12345
note: no need to create any table inside database.hibernate will take care of it.
5.open postman to run apis.following are the api's that we need to give.

Methods    	Urls					Action
POST	    	/api/auth/signup		signup new account
POST		/api/auth/signin		login an account
GET		/api/test/all			retrieve public content
GET		/api/test/user			access User’s content
GET		/api/test/mod			access Moderator’s content
GET		/api/test/admin			access Admin’s content





