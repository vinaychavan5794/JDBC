# JDBC

After setting up the tables, the program reads an input file called transfile.
Each line in transfile is a transaction. There are six types of transactions.

Transaction Code 1: Delete an Existing Employee
->Example: 1 100
If the transaction code is 1, the code deletes an existing employee. The other
field in this line is the id of the employee (i.e., the eid ) to be deleted. In this case,
the program deletes the corresponding tuple from the employee relation. If the
deleted employee is the supervisor of another employee(s), say employee with
eid =50, then the sid value of the tuple in the supervisor table whose
eid is 50,is set to NULL .
The code outputs “error” if no tuple for the specified employee exists in the
employee relation. If the employee is successfully deleted, then output is “done”.


Transaction Code 2: Insert a New Employee
->Example: 2 50 Mary 100000 100
If the transaction code is 2, then the program  inserts a new employee. In this case,
the other fields, in the line are eid, name, salary and sid. Each of them is separated
by one or more spaces. Here eid, salary and sid are integers while name is a string
without spaces. For this transaction, a tuple ( eid, name,
salary ) to the employee relation and a tuple ( eid, sid ) to the supervisor relation is inserted.
Before inserting the second tuple, a check is done if the supervisor whose eid
value is specified in the transaction (using sid ) exists in the employee table. If such
an employee exists then an insert :tuple ( eid, sid ) to the supervisor table is done;
otherwise, the code gives an error message and inserts the tuple ( eid , NULL) to the supervisor
table. If thetuples for the new employees are created successfully, then the code outputs “done”. If there
is any problem then it outputs “error”.


Transaction Code 3: Insert a New Supervisor
->Example: 3 50 100
If the transaction code is 3 then an insert of tuple is done in the supervisor table. In
this case the other fields in the line give eid and sid in that order separated by at
least one space. If the sid is blank then the code takes the sid to be NULL value. If a
supervisor tuple with the specified eid already exists, then an update is made
with sid attribute of that tuple to the new value specified, even if the new value is
NULL.

Transaction Code 4: Average Salary of all employees

Transaction Code 5: Supervisor Employee List
->Example: 5 100
If the transaction code is 5, then the code outputs the names of all employees that
work under a supervisor. In this case, the supervisor id is given in the line. For
example, if the given supervisor id is 100, then the code outputs names of
employees that work directly or indirectly under the employee with eid=100.

Transaction Code 6: Average Salary
Example: 6 100
If the transaction code is 6, then the code outputs the average salary of
employees that work under a supervisor ( directly or indirectly) . If the average
salary is not an integer, rounds it to an integer. Here the supervisor id is given
in the input line.

Instruction to run the code:

->Compile the java file by using command "javac JDBCConnectivityProgram.java".After compiling run the program by using command "java JDBCConnectivityProgram".
->Another way to run the program is to put the file in the default package in Eclipse IDE and click run.

->The program reads Book1.xls file to insert sample records in the table.




