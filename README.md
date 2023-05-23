# KarateWebPage
CSCI 371 Web Scripting Languages: Final Project
Develop Karate School Web Application

Step 1: Create Members Table:
CREATE TABLE IF NOT EXISTS Members
 (
    ID     INT   NOT NULL AUTO_INCREMENT,
    Username    NCHAR(10) NOT NULL,
    Last_Name   NVARCHAR (30) NOT NULL,
    First_Name  NVARCHAR (30) NOT NULL,
    Phone       NVARCHAR (30) NOT NULL,
    Date_Joined DATE NOT NULL,
    Password NCHAR(10) NOT NULL, 
    PRIMARY KEY (ID) );

Step 2: Create Payments table.
CREATE TABLE Payments
 (
    ID  INT  AUTO_INCREMENT,
    Member_Id    INT      NOT NULL,
    Payment_Date DATE NOT NULL,
    Amount    DOUBLE   NOT NULL,
    PRIMARY KEY CLUSTERED (ID),
    FOREIGN KEY (Member_Id) REFERENCES Members(ID)
);


Step 3: Create Enrollments table.
CREATE TABLE Enrollments
 (
    ID  INT  AUTO_INCREMENT,
    Member_Id    INT      NOT NULL,
    Payment_Id    INT   NOT NULL,
    ProgramName NCHAR(20) NOT NULL, 
    Instructor_Id INT      NOT NULL,
    PRIMARY KEY CLUSTERED (ID),
    FOREIGN KEY (Member_Id) REFERENCES Members(ID),
    FOREIGN KEY (Payment_Id) REFERENCES Payments(ID),
	FOREIGN KEY (Instructor_Id) REFERENCES Instructors(ID )
);


Step 4: Create Instructors table.
CREATE TABLE Instructors(
    ID  INT    AUTO_INCREMENT,
    InstructorName NVARCHAR (30) NOT NULL,
	PRIMARY KEY (ID) 
);

Step 5: Develop a New member Signup Form.

Step 6. Develop an Existing Member Login Form.

Step 7. After login, you will be automatically redirected to the Member’s page. 

The page must display the Member’s first and last name, phone number, and the date joined for the current Member(display as a table).
Also, this page should display all payments made by the current Member. Display the payment dates and all payments made by the current Member.


Step 8: Next page – Develop a Karate Program Registration Form.

	Note: Add data to the Enrollments and Payments tables.
 

Step 9. Develop a Web page for the System Administrator.

Administrator should be able to:

1.	Login to his/her own home page.
2.	View the List of instructors.
3.	Delete or Add instructors.
4.	View the List of members.
5.	Delete, Update, or Add a new member.
6.	Search for a member by LastName or ID.

Requirements:

1.	Develop a Header page(‘header.html’).
2.	Develop a Footer page(“footer.html”).
3.	Include Footer and Header files to every PHP web page. Use include(‘header.html’) and include(“footer.html”).
4.	Develop a Home page. Add header file, footer file, name for your Karate School, and image. Also include links for “Sign up” and “Sign in”.
5.	Use SESSION to display the First and the Last name of the current(logged in) Member.
6.	Display “Sign out” link on the Members and Karate Program Registration Form files.
7.	“Sign out” link should execute logout.php file. This file should delete all elements of the SESSION array and the control flow should  be redirected to the home page.
8.	Register 8 Members. 
9.	Enroll Members to different Programs.
