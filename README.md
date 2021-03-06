# Internet and Applications
For the class "Internet and Application" of NTUA we will build a project that inserts articels into a relational database.
1. The articles are downloaded from: [www.semanticscholar.org](https://www.semanticscholar.org/cord19). 
2. We will create the Database ER-diagram and the Database with MySQLWorkbench and the program that will insert our data into our database.
3. We also created a program tha produces a bar diagram presenting the articles published per month, by "PLoS One" magazine.
4. We added a javascript file that fetches the 10 top countries with the most publishes.
5. Furthermore we inserted a search bar that brings back all the titles from the articles produced by an organization.

### We expanded our project by adding an independent java service
6. We created a java application in eclipse.
7. For the needs of this service we added a user table in ou database that savs the first and last name of our users.
8. Through the application you can see all the users added, add a new user and search for the articles produced by an organization.


## [Requirements](requirements.txt)
### For the first project:
- mysql 8.0.19
- mysql_connector 2.2.9
- numpy 1.17.4
- pandas 0.25.3

### For the second project:
- eclipse IDE
- mysql 8.0.19
- jsp 2.2
- apache tomcat 8.5
- jdk 1.8
- jstl 1.2.1
- Servlet API 2.5

## Installation
1. First of all we initialize a mysql database, in our project we used [MySQLWorkbench](https://www.mysql.com/products/workbench/)
2. Then, connect to your database using your crendentials and run the following inside mysql command prompt:
   1. [create-tables.sql](database-configuration/create-tables.sql): to create the database.
   
### In the terminal

3. Run,

```bash
 $ git clone https://github.com/elenisproject/internet-and-applications.git
 $ cd internet-and-applications
```

4. Download from the articles from [www.semanticscholar.org](https://www.semanticscholar.org/cord19) and save them inside the /internet-and-applications/import-data folder.
5. Add your database credentials at the settings.py file,
```bash
 $ cd internet-and-applications/import-data/settings.py
```
6. Run the following strictly at this order,

```bash
 $ pip3 install -r requirements.txt
 $ python3 ./import-data/insert_metadata.py
 $ python3 ./import-data/insert_into_first_table.py
 $ python3 ./import-data/insert_authors.py
 $ python3 ./import-data/insert_text.py
 $ python3 ./import-data/insert_cite_span.py
 $ python3 ./import-data/insert_ref_span.py
 $ python3 ./import-data/abstract.py
 $ python3 ./import-data/cite_span_abstract.py
 $ python3 ./import-data/ref_span_abstract.py
 $ python3 ./import-data/back_matter.py
 $ python3 ./import-data/cite_span_back_matter.py
 $ python3 ./import-data/ref_span_back_matter.py
 $ python3 ./import-data/bib_entries.py
 $ python3 ./import-data/ref_entries.py
```

7. Run the app.js
```bash
   $ cd node-js/node-js-mysql
   $ cd server
   $ nodemon app.js
```

## File Structure:
[database-configuration](https://github.com/elenisproject/internet-and-applications/tree/master/database-configuration):
this file contais the code to build our local database.<br />
Our Database hase 15 tables in total, one table for the metadata.csv file that has the general information for all the pdf_json files. <br />
While the other 14 tables are used to save all our data from the pdf_jason folder. <br />

**ER-Diagram** <br />
 ![](img/Database_ER.png)
[import-data](https://github.com/elenisproject/internet-and-applications/tree/master/import%20data):
 
 - *settings.py:* contains the settings for connecting to our database.
 - *_.py:* is the code used to insert our data to a table, the file's name is the table's name we insert our data.
 - *final-chart.html:* shows the plot produced by app.js
 - *app.js:* connects with database, serves in localhost:3000
 - *java-eclipse:* for the java project 
