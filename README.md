# ASP

1.	Background
Assignment 2 will be a continuation of the SportPro Web Application Project that was partially implemented during the Assignment 1 (see Assignment 1 specifications for more details).

Assignment 2 will be a group project as before.  You should continue your pre-vious assignment 1 as a starting point for this project by simply extending it.
In addition to the existing features (Display Customers, Create Contact List and Survey of Customers) the Assignment 2 will implement a data maintenance section that includes the following features:
•	Maintain products
•	Maintain customers

For the Assignment evaluation the following factors will be taken in considera-tion:
1.	The project compiles and run without errors (pre-requisite)
2.	The user can complete database maintenance functions (display, up-date, insert. delete) for products and customers without errors or excep-tions by having all required validation in place (85%)
o	Products (60%)
o	Customers (25%)
3.	Web forms are properly layout using HTML5 and required CSS stylesheets (10%)
4.	Use of proper coding guidelines and naming conventions (5%)

 

2.	SportsPro Project – Part 2
 The Assignment 2 will implement additional functionality to the SportsPro web application project. It will add a separate maintenance section to allow administrator users to maintain customers and products tables. This functionality will be implemented by using ASP.NET Data Source Controls (SqlDataSource) and respective Data Bound Controls (GridVIew, and DetailsView). A proper input validation will be implemented to ensure that only valid data can be stored in the database. A link to navigate in the maintenance section should be provided in the top level navigation. 
 
3.	TechSupport Database
The TechSupport database consists of the six tables shown in the diagram that follows. The main table is the Incidents table, which contains one row for each technical support incident. Each row in the Incidents table is related to one row in the Customers table, which contains information about the company’s customers; one row in the Products table, which contains information about the company’s products; and one row in the Technicians table, which contains information about the company’s technical support staff members. In addition, a table called Registrations keeps track of the products that are registered to each customer, and the States table contains state and zip code information.


 

Fig. 1 – TechSupport database design

The TechSupport database file - TechSupport.mdf - should be included under the App_Data folder of the web application.

As you test some of the projects that you develop, you’ll need to add, modify, and delete rows in the database. Then, at some point, you may want to restore the original data. To do that with SQL Server Express LocalDB, you can just copy the original database file in the App_Data folder of the application. 
 

4.	Example of Maintenance Menu Options (Only Products an Customers need to be done for this assignment)
An example of an entry point to the Maintenance section of the application.

 

The Master page (Site.Master) of the web project template should include the navigation to the Maintenance section with the menu items for the Products and Customers maintenance pages. For Assignment 2 you need to create two new web forms (content pages)  - ProductsAdmin.aspx and CustomersAdmin.aspx. Specifications for each page will be included in the following sections. 




 

5.	Specifications for each maintenance page

5.1.	Products Maintenance Page (ProductsAdmin.aspx)
This page will provide the functionality to display, update, add and delete products. The GridView control will display the product as well update and delete products. New products will be added through the respective form. An example layout for this page is provided below.

Maintain Products Page
 

•	Operations
- The Grid view will allow sorting of the product list by each column, Edit button will enable updating the product and delete button will remove the product from the list
- Add Product button will allow the user to insert a new product to the list


•	Specifications
•	Add a SqlDataSource that will support select product list, INSERT, UP-DATE and DELETE statement and that support optimistic concurrency.
•	Add a GridView control that is bound to the SqlDataSource control with template fields for ProductCode, Name, Version and Release Date.
•	Insert a new product by collecting and validating respective data and using Insert functionality of the SqlDataSource (on Add Product event handler)
•	Add Required field validators, compare validators and summary validator to enforce that all input fields are required, version field should be a decimal value and release data a date type field (use compare validators)
•	Implement OnRowDeleted, OnRowUpdated and Add_OnClick event han-dler to address database and any concurrency issues
•	On validation errors display respective error message for the users as in fol-lowing screen shots

 

 


5.2.	Customer Maintenance Page (CustomersAdmin.aspx)
This page will provide the functionality to display, update, add and delete customers. The GridView control will display the customer list and as well select a customer. The  DetailsVew control will display, update, insert, and delete a customer. An example lay-out for this page is provided below.
 

Maintain Customers Page
 
Edit Customer
 


Add Customer
 

•	Operations
- The GridView will allow sorting of the customer list by each column, Select button will allow the user to select a record that will be maintained in the DetailsView con-trol
- Details View control will be populated with the selected customer from the grid and will allow the user to update and insert a new customer.

•	Specifications
•	Add a SqlDataSource(1)  that will support select customer list for the grid view control.
•	Add a GridView control that is bound to the SqlDataSource (1) control and that uses BoundFields.
•	Add a SqlDataSource (2) control that will support  SELECT, INSERT, UP-DATE and DELETE customer functions by configuring filtering by Custom-erID from GridView control (WHERE clause)
•	Add a DetailsView control that is bound with SqlDataSource (2) control to allow a user to update, delete and insert a customer and that uses Bound-Fields
•	Implement OnItemDeleted, OnItemUpdated and OnItemInserted event han-dlers of the DetailsView control to address database and any concurrency errors.
e.g.
 
•	No validation will be implemented during update and insert (to save time since this was implemented in the products maintenance page) Insert, Up-date will work as expected with valid inputs only)
