
#  ******* Learn Bash and SQL by Building a Bike Rental Shop
# ** Review
# *** The first thing you need to do is start the terminal. Do that by clicking the "hamburger" menu at the top left of the screen, going to the "terminal" section, and clicking "new terminal". Once you open a new one, type echo hello terminal into the terminal and press enter.

1. Capitalization matters

2. If the tests don't run automatically, try typing exit into the terminal and redoing the instructions

You are going to build a bike rental shop. It will have a database, and a bash script to interact with the database. Use the terminal to connect to PostgreSQL by entering psql --username=freecodecamp --dbname=postgres.

1. Type the above command into the terminal and press enter

2. Type psql --username=freecodecamp --dbname=postgres into the terminal and press enter

List the databases with \l to see what databases are here.

1. Type \l into the psql prompt and press enter

2. Type psql --username=freecodecamp --dbname=postgres into the terminal to log in to psql if you aren't logged in first

You need your own database for the bike shop. Create a new database named bikes.

1. Use the CREATE DATABASE keywords

2. Here's an example: CREATE DATABASE database_name;

3. Type CREATE DATABASE bikes; into the psql prompt and press enter

4. Type psql --username=freecodecamp --dbname=postgres into the terminal to log in to psql if you aren't logged in first

List databases again to make sure your database got created.

1. Use the list shortcut command

2. Type \l into the psql prompt

3. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

There it is. Connect to it so you can start building the structure of your bike shop database.

1. Use the connect shortcut command

2. Add the database name to the command

3. It's the \c command

4. Here's an example: \c database_name

5. Try entering \c bikes into the psql prompt

6. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Your database needs three tables. One for your bike inventory, one for your customers, and one for the bikes that are rented out. Create a table named bikes in your database for the inventory.

1. Use the CREATE TABLE keywords

2. Don't forget the parenthesis

3. Here's an example: CREATE TABLE table_name();

4. Try entering CREATE TABLE bikes(); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the tables to make sure your table got created.

1. Use the display shortcut command

2. It's the \d command

3. Type \d into the psql prompt and press enter

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

The table will have a few columns for bike information. First, is a unique ID column. Add a column to the bikes table named bike_id. Give it a type of SERIAL and make it a PRIMARY KEY.

1. Use the ALTER TABLE, ADD COLUMN, SERIAL, and PRIMARY KEY keywords

2. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

3. Try entering ALTER TABLE bikes ADD COLUMN bike_id SERIAL PRIMARY KEY; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Use the display command to view the details of the bikes table.

1. It's the \d command

2. Add the table name to the command

3. Try entering \d bikes in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

The first column is set. Add a column named type for the type of bike. Make it a VARCHAR(50) and give it a constraint of NOT NULL.

1. Use the ALTER TABLE, ADD COLUMN, VARCHAR(50), and PRIMARY KEY keywords

2. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

3. Try entering ALTER TABLE bikes ADD COLUMN type VARCHAR(50) NOT NULL; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the details of the bikes table again.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d bikes in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in

The first two columns look good. Add a column named size to the bikes table that is an INT and has the NOT NULL constraint. This will be for the size of each bike.

1. Use the ALTER TABLE, ADD COLUMN, INT, and NOT NULL keywords

2. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

3. Try entering ALTER TABLE bikes ADD COLUMN size INT NOT NULL; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in

Add another column to the table named available. Make it a boolean and has a constraint of NOT NULL. Also give it a default value of TRUE. This will be set to false when someone rents out a bike.

1. Use the ALTER TABLE, ADD COLUMN, BOOLEAN, NOT NULL and DEFAULT TRUE keywords

2. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS DEFAULT;

3. Try entering ALTER TABLE bikes ADD COLUMN available BOOLEAN NOT NULL DEFAULT TRUE; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in

Display the details of the bikes table again so you can make sure it's how you want it.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d bikes in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

That table is done for now. Create another table named customers. It will store a name and phone number for each customer that rents a bike.

1. Use the CREATE TABLE keywords

2. Don't forget the parenthesis

3. Here's an example: CREATE TABLE table_name();

4. Try entering CREATE TABLE customers(); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Add a customer_id column to your new table that is a type of SERIAL and make it a PRIMARY KEY.

1. Use the ALTER TABLE, ADD COLUMN, SERIAL, and PRIMARY KEY keywords

2. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

3. Try entering ALTER TABLE customers ADD COLUMN customer_id SERIAL PRIMARY KEY; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the details of the customers table so you can make sure your new column is there.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d customers in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

There it is. Add a column named phone for customers phone numbers. Make it a varying character that has a maximum length of 15 characters. Also make sure it can't be null, and that it has to be unique.

1. Use the ALTER TABLE, ADD COLUMN, VARCHAR(), NOT NULL, and UNIQUE keywords

2. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

3. Try entering ALTER TABLE customers ADD COLUMN phone VARCHAR(15) NOT NULL UNIQUE; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Add the last column. Call it name and make it a VARCHAR(40) that can't be null.

1. Use the ALTER TABLE, ADD COLUMN, VARCHAR(), and NOT NULL keywords

2. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

3. Try entering ALTER TABLE customers ADD COLUMN name VARCHAR(40) NOT NULL; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the details of the customers table.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d customers in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

That table is finished. Lastly, you need a table to store which bikes are rented and who has rented them. Create a new table named rentals.

1. Use the CREATE TABLE keywords

2. Don't forget the parenthesis

3. Here's an example: CREATE TABLE table_name();

4. Try entering CREATE TABLE rentals(); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Add a rental_id column to your new table. Make it automatically increment with SERIAL and make it the primary key for this table.

1. The other two properties are SERIAL and PRIMARY KEY

2. Use the ALTER TABLE, ADD COLUMN, SERIAL, and PRIMARY KEY keywords

3. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

4. Try entering ALTER TABLE rentals ADD COLUMN rental_id SERIAL PRIMARY KEY; in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the details of the rentals table.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d rentals in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Next, you need a column for the customer who is renting a bike. Add column named customer_id. This will have an id of a customer from the customers table. Make the column an INT and NOT NULL to start.

1. Add the column to the rentals table

2. Use the ALTER TABLE, ADD COLUMN, INT, and NOT NULL keywords

3. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

4. Try entering ALTER TABLE rentals ADD COLUMN customer_id INT NOT NULL; in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Make the column you just added a foreign key that references the customer_id column from the customers table. Here's an example of how you can do that:

ALTER TABLE table_name ADD FOREIGN KEY(column_name) REFERENCES referenced_table(referenced_column);
1. Without the keywords, it looks like tihs: rentals customer_id customers(customer_id)

2. Try entering ALTER TABLE rentals ADD FOREIGN KEY(customer_id) REFERENCES customers(customer_id); in the psql prompt

3. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the details of the rentals table to make sure your key is set.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d rentals in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

That foreign key is set. You need another column so you know what bike a customer is renting. Add a column named bike_id and make it an INT and NOT NULL.

1. Add the column to the rentals table

2. Use the ALTER TABLE, ADD COLUMN, INT, and NOT NULL keywords

3. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

4. Try entering ALTER TABLE rentals ADD COLUMN bike_id INT NOT NULL; in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Make that column a foreign key that references the bike_id column from the bikes table so you know what bike the id is for.

1. Here's the example again: ALTER TABLE table_name ADD FOREIGN KEY(column_name) REFERENCES referenced_table(referenced_column);

2. Without the keywords, it looks like tihs: rentals bike_id bikes(bike_id)

3. Try entering ALTER TABLE rentals ADD FOREIGN KEY(bike_id) REFERENCES bikes(bike_id); in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the details of the rentals table so you can make sure the key is correct.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d rentals in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Moving along. You want to know when a customer rents a bike, and when it gets returned. Add a column to your rentals table named date_rented that's a type of DATE. Make sure the entry can't be null, and give it a default value of NOW().

1. Add the column to the rentals table

2. Use the ALTER TABLE, ADD COLUMN, DATE, NOT NULL, and DEFAULT NOW() keywords

3. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE CONSTRAINTS;

4. Try entering ALTER TABLE rentals ADD COLUMN date_rented DATE NOT NULL DEFAULT NOW(); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Display the details of the rentals table again.

1. Use the display shortcut command

2. Add the table name to the command

3. Here's an example: \d table_name

4. Try entering \d rentals in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

It looks good. Lastly, you need a column for when a customer returns a bike. Add a column named date_returned that's a type of DATE.

1. Use the ALTER TABLE, ADD COLUMN, DATE keywords

2. Add the column to the rentals table

3. Here's an example: ALTER TABLE table_name ADD COLUMN column_name TYPE;

4. Try entering ALTER TABLE rentals ADD COLUMN date_returned DATE; in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

View the details of the table again.

1. It's the rentals table

2. Use the display shortcut command

3. Add the table name to the command

4. Here's an example: \d table_name

5. Try entering \d rentals in the psql prompt

6. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

The tables are all finished. Display all the tables so you can see what you ended up with.

1. Use the display shortcut command

2. It's the \d command

3. Enter \d in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

You have nine bikes in your inventory. Add the first one to your bikes table. It has a type of Mountain and a size of 27. Make sure to put your VARCHAR values in single quotes. The bike_id and available columns should be filled in automatically, so you don't need to worry about those.

1. Use the INSERT INTO and VALUES keywords

2. Here's an example: INSERT INTO table_name(column_name, column_name) VALUES(value, value);

3. View the details of the bikes table with \d bikes to see what values it expects

4. Try entering INSERT INTO bikes(type, size) VALUES('Mountain', 27); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

View all the columns in your bikes table with SELECT.

1. Use * to view all the columns

2. Here's an example: SELECT * FROM table_name;

3. Try entering SELECT * from bikes; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Looks like it's all working, the bike_id and available columns were filled in automatically. Insert another bike. Give it a type of Mountain and a size of 28.

1. Make sure to put your VARCHAR values in single quotes

2. Use the INSERT INTO and VALUES keywords

3. Here's an example: INSERT INTO table_name(column_name, column_name) VALUES(value, value);

4. Try entering INSERT INTO bikes(type, size) VALUES('Mountain', 28); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Add another Mountain bike to your inventory. Make it a 29 inch bike.

1. Use the INSERT INTO and VALUES keywords

2. Make sure to put your VARCHAR values in single quotes

3. Here's an example: INSERT INTO table_name(column_name, column_name) VALUES(value, value);

4. Try entering INSERT INTO bikes(type, size) VALUES('Mountain', 29); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Add a 27 inch Road bike to the table.

1. Use the INSERT INTO and VALUES keywords

2. Make sure to put your VARCHAR values in single quotes

3. Here's an example: INSERT INTO table_name(column_name, column_name) VALUES(value, value);

4. Try entering INSERT INTO bikes(type, size) VALUES('Road', 27); in the psql prompt

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Use SELECT to view all the data in the bikes table again.

1. Use * to view all the columns

2. Here's an example: SELECT * FROM table_name;

3. Try entering SELECT * from bikes; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Add the two bikes to your inventory, they are 28 and 29 inch Road bikes. Try to add them both with one command.

1. Here's an example: INSERT INTO table_name(column_name, column_name) VALUES(value, value), (value, value);

2. Make sure to put your VARCHAR values in single quotes

3. Try entering INSERT INTO bikes(type, size) VALUES('Road', 28), ('Road', 29); in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

There's three more bikes. Add 19, 20, and 21 inch BMX bikes to your table. Try to add them with one command.

1. Here's an example: INSERT INTO table_name(column_name, column_name) VALUES(value, value), (value, value), (value, value);

2. Make sure to put your VARCHAR values in single quotes

3. Try entering INSERT INTO bikes(type, size) VALUES('BMX', 19), ('BMX', 20), ('BMX', 21); in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

View all the data in your bikes table.

1. Use SELECT with * to view all the columns

2. Here's an example: SELECT * FROM table_name;

3. Try entering SELECT * from bikes; in the psql prompt

4. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in first

Your current inventory is all added. For the rest of the project, I recommend leaving that terminal open and connected, and that you should "split" the terminal so you have a second one to use for bash commands. Do that by clicking the "hamburger" menu at the top left of the window, going to the "terminal" section, and clicking "split terminal". After you have opened it, use the touch command to create a file named bike-shop.sh in the project folder.

1. Try entering touch bike-shop.sh in the terminal

2. Make sure it's the regular terminal, and not the psql one

3. Make sure you are in the project folder first

4. If you opened a new terminal instead of splitting it, you can close it by entering exit and try again

5. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you want

This file will be the program for your bike rental shop. Open the file and add a "shebang" at the top so it uses bash when it's executed. If you don't remember, it looks like this: #!/bin/bash.

1. Add #!/bin/bash to the top of your bike-shop.sh file

In the file, use echo with the -e flag to print ~~~~~ Bike Rental Shop ~~~~~ with a new line at the beginning and end.

1. The newline character is \n

2. Use double quotes around the message so the new lines are printed

3. Here's an example: echo -e "\n<message_here>\n"

4. Add echo -e "\n~~~~~ Bike Rental Shop ~~~~~\n" to the bike-shop-sh file

Use the terminal (not the psql one) and the chmod command to make your file executable. Add the +x flag and bike-shop.sh to the command to do that.

1. Here's an example: chmod +x <filename>

2. Try entering chmod +x bike-shop.sh in the terminal

3. Make sure you are in the project folder first

Type ./bike-shop.sh in the terminal to run your script.

1. Make sure to use the regular terminal and not the psql one

2. Make sure you are in the project folder first

😄 In the script, create an empty function named MAIN_MENU. This will have a few options to enter when the script runs to rent or return a bike.

1. Here's an example:

FUNCTION_NAME() {

}
2. Add this to the bottom of the script:

MAIN_MENU() {

}
In your function, echo the text How may I help you? so that there's a greeting when you go to the menu.

1. Add echo "How may I help you?" in the designated area

Call your MAIN_MENU at the bottom of the file so the function runs when you start the script.

1. Add MAIN_MENU at the bottom of the file

Run the file in the terminal again so you can see what it is outputting.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

It's coming along. Add another echo command in the function below the other one. Make it output text that looks like this:


1. Rent a bike
2. Return a bike
3. Exit
Note that there's an empty line at the start.

1. Use the echo command with the -e flag and line breaks (\n) to produce the suggested output

2. Without the words, it looks like this: echo -e "\n1. \n2. \n3. "

3. Run your script if you need to see if the output matches

4. Add echo -e "\n1. Rent a bike\n2. Return a bike\n3. Exit" to your function

Run the file to make sure it worked.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

You have some options displaying. Next, you need to get input from whoever is using the program. Use the read command to read input into a variable called MAIN_MENU_SELECTION below the options.

1. Here's an example: read <VARIABLE_NAME>

2. Here's what the code looks like: read MAIN_MENU_SELECTION

3. Add the code at the bottom of the MAIN_MENU function

4. The MAIN_MENU function should look like this:

MAIN_MENU() {
  echo "How may I help you?"
  echo -e "\n1. Rent a bike\n2. Return a bike\n3. Exit"
  read MAIN_MENU_SELECTION
}
When an option gets entered, you need to take a user to one of those other menus. Add an empty RENT_MENU function below the MAIN_MENU function.

1. Make sure the RENT_MENU function is below the MAIN_MENU function and above where you call MAIN_MENU

2. Add this in the suggested area:

RENT_MENU() {

}
For the time being, just echo Rent Menu in the function so you can see if it's working.

1. Don't use any flags with the command

2. Add echo "Rent Menu" in the RENT_MENU function

Add an empty RETURN_MENU function below the RENT_MENU function for when a user enters the option to return a bike.

1. Make sure the RETURN_MENU function is below the RENT_MENU function and above where you call MAIN_MENU

2. Add this in the suggested area:

RETURN_MENU() {

}
Use echo to print Return Menu in the function you just added. You will change these later.

1. Don't use any flags with the command

2. Add echo "Return Menu" in the RETURN_MENU function

Add an empty EXIT function below the RETURN_MENU function for when a user wants to exit the program.

1. Make sure the EXIT function is below the RETURN_MENU function and above where you call MAIN_MENU

2. Add this in the suggested area:

EXIT() {

}
This one probably doesn't need a placeholder message. In the EXIT function, use echo to print Thank you for stopping in. with a new line at the beginning and end of the message.

1. The newline character is \n

2. Use double quotes around the message so the new lines are printed

3. Here's an example: echo -e "\n<message_here>\n"

4. Add echo -e "\nThank you for stopping in.\n" to the EXIT function

When a user enters an option at the main menu, you want to take them to the appropriate sub-menu. You can use a case statement for this. Here's an example:

case EXPRESSION in
  PATTERN) STATEMENTS ;;
  PATTERN) STATEMENTS ;;
  PATTERN) STATEMENTS ;;
  *) STATEMENTS ;;
esac
The expression you want is the $MAIN_MENU_SELECTION variable. You are expecting it to be a 1, 2, or 3 for your various menus. Add a case statement that takes users to their corresponding menus. The * is for when anything else is entered. Take users to the MAIN_MENU when the variable isn't a 1, 2, or 3.

1. Add the case statement in the MAIN_MENU function below the read MAIN_MENU_SELECTION line

2. Here's how it starts:

case $MAIN_MENU_SELECTION in
  1) RENT_MENU ;;
3. Add this case statement below the;

case $MAIN_MENU_SELECTION in
  1) RENT_MENU ;;
  2) RETURN_MENU ;;
  3) EXIT ;;
  *) MAIN_MENU ;;
esac
Run the script a few times and try out the different menus. Be sure to enter something other than one of the options to go to the main menu.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Add an argument to where you call MAIN_MENU in the case statement. It should be Please enter a valid option.. The next step will adjust the function so the message is printed when a user enters an invalid option.

1. Here's an example: FUNCTION_CALL "<argument_message>"

2. Here's how the function call should look:

  *) MAIN_MENU "Please enter a valid option." ;;
3. The whole case statement should look like this:

case $MAIN_MENU_SELECTION in
  1) RENT_MENU ;;
  2) RETURN_MENU ;;
  3) EXIT ;;
  *) MAIN_MENU "Please enter a valid option." ;;
esac
At the top of the MAIN_MENU function, add an if condition that checks if there's an argument ($1) passed to the function. If there is, print the message with a new line in front of it.

1. Here's an example of an if:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
fi
2. The condition you want is $1

3. Use echo with the -e flag and a new line character (\n) to print the argument with a new line at the beginning in the <STATEMENTS> area

4. Here's an example of that part: echo -e "\n<argument_here>"

5. The if statement should look like this:

if [[ $1 ]]
then
  echo -e "\n$1"
fi
6. Make sure to put it at the top of the MAIN_MENU function

Run the script and enter an invalid option to see the message. Exit the program when you are done.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Looks good. Delete the echo "Rent Menu" from the RENT_MENU function so you can start adding the ability to rent a bike from the database.

1. The RENT_MENU function should be empty

2. The RENT_MENU function should look like this:

RENT_MENU() {

}
In the RENT_MENU function, add three single line comments; get available bikes, if no bikes available, and send to main menu, in that order.

1. Here's an example of a single line comment: # <comment here>

2. The RENT_MENU function should look like this:

RENT_MENU() {
  # get available bikes

  # if no bikes available

  # send to main menu

}
To get the bikes available, you need to query the database from your script. Below the "shebang", add a PSQL variable that looks like this: PSQL="psql -X --username=freecodecamp --dbname=bikes --tuples-only -c". You will then be able to use it to query the database like this: $($PSQL "<query_here>").

1. Add the suggested variable below the "shebang" and above where you print the Bike Rental Shop line

Below the get available bikes comment. Create an AVAILABLE_BIKES variable that gets the bike_id, type, and size columns from the bikes table for the bikes that are available. Order the results by their bike_id column. Here's an example: AVAILABLE_BIKES=$($PSQL "<query_here>")

1. Use the SELECT, FROM, WHERE, and ORDER BY keywords in your query

2. Get the three suggested columns in the same order they are listed; bike_id, type, size

3. The condition you want is WHERE available = true

4. Without the keywords, the query looks like this: bike_id, type, size bikes available = true bike_id

5. The query should be SELECT bike_id, type, size FROM bikes WHERE available = true ORDER BY bike_id

6. Add AVAILABLE_BIKES=$($PSQL "SELECT bike_id, type, size FROM bikes WHERE available = true ORDER BY bike_id") below the get available bikes comment

Below the new variable, use echo to print it. Place it in double quotes so it prints any new lines.

1. Here's an example: echo "<variable_here>"

2. Use the variable with $AVAILABLE_BIKES

3. Add echo "$AVAILABLE_BIKES" to the suggested area

Run your script and go to the rent menu to see if the available bikes are being printed.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Awesome. In the psql prompt, set the available column to false for all the bikes so you can see what it prints when there's no bikes available.

1. Use the UPDATE, SET, and WHERE keywords

2. Here's an example: UPDATE <table> SET <column> = <value> WHERE <condition>

3. You want to set available to false for columns that are true

4. After the SET can look like this: available = false WHERE available = true

5. Try entering UPDATE bikes SET available = false WHERE available = true; in the psql prompt

6. Type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in. I recommend "splitting" the terminal so you can have one for bash commands and one for psql commands. You can do that by clicking the "hamburger" menu at the top left of the window, going to the "terminal" section, and clicking "split terminal".

Run your script and go to the rent menu to see the output.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure it's the regular terminal and not the psql one

3. Make sure you are in the project folder first

So if there's no bike available, the variable will be empty. In the script, below the if no bikes available comment, add an if condition that checks if the variable is empty. Use -z to check if it's empty. Place the send to main menu comment in its STATEMENTS area.

1. Use -z <VARIABLE> to see if a variable is empty

2. Here's an example:

if [[ -z <VARIABLE> ]]
then
  <STATEMENTS>
fi
3. The if condition should look like this:

if [[ -z $AVAILABLE_BIKES ]]
then
  # send to main menu
fi
4. Make sure it's right below the suggested comment

Below the comment in the if you just added. Send users to the main menu and give them the message, Sorry, we don't have any bikes available right now.

1. Here's an example MAIN MENU "<message_here>"

2. Make sure it's in the if condition below the send to main menu comment

3. The function call should look like this: MAIN_MENU "Sorry, we don't have any bikes available right now."

4. The if condition should look like this:

if [[ -z $AVAILABLE_BIKES ]]
then
  # send to main menu
  MAIN_MENU "Sorry, we don't have any bikes available right now."
fi
Run the script and go to the rent menu to see the message. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

If no bikes are available, you will get that message. Add an else to the if condition for when there is bikes available. In it, add four single line comments; display available bikes, ask for bike to rent, if input is not a number, and send to main menu.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. An if/else statement looks like this:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
else
  <STATEMENTS>
fi
4. The else should look like this:

else
  # display available bikes

  # ask for bike to rent

  # if input is not a number

  # send to main menu

5. The whole if should look like this:

if [[ -z $AVAILABLE_BIKES ]]
then
  # send to main menu
  MAIN_MENU "Sorry, we don't have any bikes available right now."
else
  # display available bikes

  # ask for bike to rent

  # if input is not a number

  # send to main menu

fi
Below the display available bikes comment you just added, use echo to print Here are the bikes we have available: with a new line in front of the message

1. Use echo with the -e flag and the new line character (\n) to print the suggested message

2. Use double quotes around the message

3. Here's an example: echo -e "\n<message_here>"

4. Add echo -e "\nHere are the bikes we have available:" below the suggested comment

Move the echo command that prints all the available bikes below the message you just added.

1. It's the echo $AVAILABLE_BIKES command

2. It should be below the Here are the bikes we have available: message

3. You should only print the bikes available in that one spot

4. Place the echo "$AVAILABLE_BIKES" line in the suggested spot

In the psql prompt, set all the bikes, except for the BMX bikes, back to true so you can see a list of bikes to rent.

1. Use the UPDATE, SET, and WHERE keywords

2. Here's an example: UPDATE <table> SET <column> = <value> WHERE <condition>

3. You want to set available to true for columns that don't have a type of BMX

4. You can use the != operator to check for columns not equal to a value

5. After the SET can look like this: available = true WHERE type != 'BMX'

6. Try entering UPDATE bikes SET available = true WHERE type != 'BMX'; in the psql prompt

7. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Run the script and go to the rent menu to see the list of bikes available.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Instead of directly printing the list, pipe the output into a while loop that reads each line. Here's how that looks:

echo "$AVAILABLE_BIKES" | while read <VAR_1> <VAR_2> <VAR_3> <VAR_4> <VAR_5>
do
  <STATEMENTS>
done
It will read the first line of your AVAILABLE_BIKES variable into the five variables. Each variable being the next word in the line. Read each line into variables, BIKE_ID BAR TYPE BAR SIZE. In the <STATEMENTS> area, use echo to print the BIKE_ID, TYPE, and SIZE variables, in that order.

1. The first line should be echo "$AVAILABLE_BIKES" | while read BIKE_ID BAR TYPE BAR SIZE

2. The <STATEMENTS> area looks like this: echo "$BIKE_ID $TYPE $SIZE"

3. Here's how it should look:

echo "$AVAILABLE_BIKES" | while read BIKE_ID BAR TYPE BAR SIZE
do
  echo "$BIKE_ID $TYPE $SIZE"
done
Run the script and go to the rent menu again to see if it's working.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

It's working 😄 Adjust the echo command that prints the bike info so that the first line printed would look like this: 1) 27" Mountain Bike. The rest would look the same, but with their bike info. Make sure to escape any characters you need to.

1. Be sure to use double quotes and escape the " after SIZE

2. Run your script and check the output if you want to see if it matches the suggestion

3. Escape a " with \"

4. Here's an example: echo "<bike_id>) <size>" <type> Bike"

5. Make the suggested line look like this: echo "$BIKE_ID) $SIZE\" $TYPE Bike"

6. The whole loop should look like this:

echo "$AVAILABLE_BIKES" | while read BIKE_ID BAR TYPE BAR SIZE
do
  echo "$BIKE_ID) $SIZE\" $TYPE Bike"
done
Run the script and go to the rent menu again to see what it looks like now.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

That's better. Below the ask for bike to rent comment, print Which one would you like to rent? with a new line in front of it.

1. Use echo with the -e flag and the new line character (\n) to print the suggested message

2. Use double quotes around the message

3. Here's an example: echo -e "\n<message_here>"

4. Add echo -e "\nWhich one would you like to rent?" below the suggested comment

Just below that, add a command to read input into a variable named BIKE_ID_TO_RENT.

1. Here's an example: read <VARIABLE_NAME>

2. Add this to the suggested area: read BIKE_ID_TO_RENT

Next, you want to find out how to test if the user input is a number. In the terminal, enter [[ a =~ [0-9] ]]; echo $? to see if a is a number. The conditional expression will run, and echo $? will print the exit code of it (the last command).

1. Enter [[ a =~ [0-9] ]]; echo $? in the terminal

2. It's the regular terminal, not the psql one

It printed 1 for false. Meaning that a did not match the pattern [0-9], or a did not contain a number from 0-9. Enter the same commands, but check if a1 matches the pattern.

1. The previous command was [[ a =~ [0-9] ]]; echo $?

2. Enter [[ a1 =~ [0-9] ]]; echo $? in the terminal

That printed 0 for true. a1 does contain a number from 0-9. Enter the same command, but change the pattern to ^[0-9]$. The ^ signifies the start of the pattern, and $ means the end. So the input will have to start, contain a number 0-9, and end.

1. The previous command was [[ a1 =~ [0-9] ]]; echo $?

2. Enter [[ a1 =~ ^[0-9]$ ]]; echo $? in the terminal

1 for false. a1 does not match the pattern. Using the same syntax, check if 1 matches the pattern.

1. The previous command was [[ a1 =~ ^[0-9]$ ]]; echo $?

2. Enter [[ 1 =~ ^[0-9]$ ]]; echo $? in the terminal

1 does match the pattern. It starts, contains a number, and ends. Check if 11 matches the same pattern.

1. The previous command was [[ 1 =~ ^[0-9]$ ]]; echo $?

2. Enter [[ 11 =~ ^[0-9]$ ]]; echo $? in the terminal

That did not match because the pattern only allows a single number. Add a + after the [0-9] to allow any strings that start, contain one or more numbers, and end.

1. Enter the previous command with the suggested changed

2. The previous command was [[ 11 =~ ^[0-9]$ ]]; echo $?

3. Enter [[ 11 =~ ^[0-9]+$ ]]; echo $? in the terminal

So that pattern will match any positive integers. You want to check if the input is not a number. Add ! in front of the comparison of the previous command to do that.

1. Enter the previous command with the suggested changed

2. The previous command was [[ 11 =~ ^[0-9]+$ ]]; echo $?

3. Enter [[ ! 11 =~ ^[0-9]+$ ]]; echo $? in the terminal

Back in your script, below the if input is not a number comment, add an if condition that checks if the input is not a number using the method you just practiced. Add the send to main menu comment in the then area of the if.

1. You want to check if the $BIKE_ID_TO_RENT variable is not a number

2. You entered [[ ! 11 =~ ^[0-9]+$ ]]; echo $? in the terminal on the last step

3. Here's an example:

if [[ <CONDITION> ]]
then
  # send to main menu
fi
4. The condition you want is [[ ! $BIKE_ID_TO_RENT =~ ^[0-9]+$ ]]

5. Add this in the suggestion area:

if [[ ! $BIKE_ID_TO_RENT =~ ^[0-9]+$ ]]
then
  # send to main menu
fi
If the $BIKE_ID_TO_RENT variable is not a number, add the code to send users to the main menu with the message, That is not a valid bike number.

1. You want to call the MAIN_MENU function with the message as an argument

2. Here's an example: MAIN_MENU "<message_here>"

3. Add MAIN_MENU "That is not a valid bike number." below the send to main menu comment

Run the script, go to the rent menu, and enter something that isn't a number to make sure it is working. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Add an else area for when the input is a number. Add these three single line comments in it; get bike availability, if not available, send to main menu.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. An if/else statement looks like this:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
else
  <STATEMENTS>
fi
4. The else area should look like this:

else
  # get bike availability

  # if not available

  # send to main menu

5. The whole if should look like this:

if [[ ! $BIKE_ID_TO_RENT =~ ^[0-9]+$ ]]
then
  # send to main menu
  MAIN_MENU "That is not a valid bike number."
else
  # get bike availability

  # if not available

  # send to main menu

fi
Below the get bike availability comment you just added, create a BIKE_AVAILABILITY variable. Set it equal to a query that gets the available column from the bikes table for the input. Also, make sure to only get the row if it is available.

1. Here's an example: BIKE_AVAILABILITY=$($PSQL "<query_here>")

2. Use the SELECT, FROM, WHERE, and AND keywords

3. Here's an example of the query: SELECT <column> FROM <table> WHERE <condition1> AND <condition2>

4. You only want the available column for the bike with a bike_id equal to the $BIKE_ID_TO_RENT variable and only if the bike is available

5. You want two conditions, WHERE bike_id = $BIKE_ID_TO_RENT AND available = true

6. Add BIKE_AVAILABILITY=$($PSQL "SELECT available FROM bikes WHERE bike_id = $BIKE_ID_TO_RENT AND available = true") below the get bike availability comment

Right below the variable you just created, use echo to print it so you can see what it looks like.

1. Print a variable like this: echo $<VARIABLE_NAME>

2. The variable you want is BIKE_AVAILABILITY

3. Add echo $BIKE_AVAILABILITY in the suggested area

Run the script a few times, go to the rent menu, enter a bike that is available and one that isn't. You should have some BMX bikes that aren't available.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

The variable will be t or empty. Below the if not available comment, add an if condition that checks if it's empty. Put the send to main menu comment in it's statements area.

1. Here's an example:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
fi
2. The condition you want is -z $BIKE_AVAILABILITY

3. Place the # send to main menu comment in the <STATEMENTS> area

4. The if condition should look like this:

if [[ -z $BIKE_AVAILABILITY ]]
then
  # send to main menu
fi
In the if condition you just added, send users to the main menu with the message That bike is not available. if they input a number that isn't available.

1. You want to call the MAIN_MENU function with the message as an argument

2. Here's an example: MAIN_MENU "<message_here>"

3. Add MAIN_MENU "That bike is not available." below the send to main menu comment

Remove the line where you print the BIKE_AVAILABILITY variable. You don't need it anymore.

1. Remove the echo $BIKE_AVAILABILITY line

Run the script and go to the rent menu, enter a bike that isn't available to make sure it's working. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

In the psql prompt, set all the bikes availability back to true.

1. Use the UPDATE, SET, and WHERE keywords

2. Here's an example: UPDATE <table> SET <column> = <value> WHERE <condition>

3. You want to set available to true for all the bikes

4. After the SET can look like this: available = true WHERE available = false

5. Try entering UPDATE bikes SET available = true WHERE available = false; in the psql prompt

6. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

In your script, add an else for when a bike is available. Add these four comments in the else area get customer info, if customer doesn't exist, get new customer name, and insert new customer.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. An if/else statement looks like this:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
else
  <STATEMENTS>
fi
4. The else area should look like this:

else
  # get customer info

  # if customer doesn't exist

  # get new customer name

  # insert new customer

5. The whole if should look like this:

if [[ -z $BIKE_AVAILABILITY  ]]
then
  # send to main menu
  MAIN_MENU "That bike is not available."
else
  # get customer info

  # if customer doesn't exist

  # get new customer name

  # insert new customer

fi
As the comments say, you need to get the customer info and find out if they are an existing customer. Below the get customer info comment, print What's your phone number? with a new line in front of it.

1. Use echo with the -e flag and the new line character (\n) to print the suggested message

2. Use double quotes around the message

3. Here's an example: echo -e "\n<message_here>"

4. Add echo -e "\nWhat's your phone number?" below the suggested comment

Below the line you just printed, read input into a PHONE_NUMBER variable. Since the phone number is unique, you can use it to identify a customer.

1. Here's an example: read <VARIABLE_NAME>

2. Add read PHONE_NUMBER to the suggested area

3. Add it below where you print What's your phone number?

With the customer's phone number, you can get their name. Below where you get the phone number, create a CUSTOMER_NAME variable that gets the customers name from the database using the phone number.

1. Query the database to set the CUSTOMER_NAME variable

2. Here's an example: CUSTOMER_NAME=$($PSQL "<query_here>")

3. Use the SELECT, FROM and WHERE keywords for your query

4. You want only the name column from the customers table

5. The condition you want is phone = '$PHONE_NUMBER'

6. The query should look like this: SELECT name FROM customers WHERE phone = '$PHONE_NUMBER'

7. Add CUSTOMER_NAME=$($PSQL "SELECT name FROM customers WHERE phone = '$PHONE_NUMBER'") below the read PHONE_NUMBER line

If the customer is in the database with the phone number used, the variable will be set to the name. If not, it will be empty. Add an if condition below the if customer doesn't exist comment that checks if the variable is empty. Place the next two comments in the then area.

1. Here's an example:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
fi
2. The condition you want is -z $CUSTOMER_NAME

3. Place the # get new customer name and # insert new customer comments in the <STATEMENTS> area

4. The if condition should look like this:

if [[ -z $CUSTOMER_NAME ]]
then
  # get new customer name

  # insert new customer

fi
5. Make sure it's below the if customer doesn't exist comment

If the customer isn't in the database, you need to get their name so you can add them. Below the get new customer name comment, print What's your name? with a new line in front of the message.

1. Use echo with the -e flag and the new line character (\n) to print the suggested message

2. Use double quotes around the message

3. Here's an example: echo -e "\n<message_here>"

4. Add echo -e "\nWhat's your name?" below the suggested comment

Below the question you just printed, read input into a variable named CUSTOMER_NAME.

1. Here's an example: read <VARIABLE_NAME>

2. Add read CUSTOMER_NAME to the suggested area

3. Add it below where you print What's your name?

You have the two pieces of information you need. Below the insert new customer comment, create an INSERT_CUSTOMER_RESULT variable that inserts the customer into the database.

Run your script and go to the rent menu. Pick a bike to rent, then enter 555-5555 when it asks for a phone number, and Me when it asks for your name.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Follow the instructions closely

3. Make sure to use 555-5555 for the phone number and Me for the name

4. The database should have a customer with 555-5555 as their phone number, and Me as their name in it

That should have added a new customer to the database. In the psql prompt, view all the data in the customers table to see if it's working.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM customers; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Excellent. View all the data in the rentals table.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM rentals; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

So you still need to add the rental to the rentals table when a bike is picked out. View all the data in the bikes table.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM bikes; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

And set the available column to false for the bike rented. Below the end of the if statement that inserts a new customer, add five more comments; get customer_id, insert bike rental, set bike availability to false, get bike info, and send to main menu

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. The comments should be below (not in) the if [[ -z $CUSTOMER_NAME ]] statement

4. The comments should look like this:

  if [[ -z $CUSTOMER_NAME ]]
  then
    # get new customer name
    echo -e "\nWhat's your name?"
    read CUSTOMER_NAME

    # insert new customer
    INSERT_CUSTOMER_RESULT=$($PSQL "INSERT INTO customers(name, phone) VALUES('$CUSTOMER_NAME', '$PHONE_NUMBER')")
  fi

  # get customer_id

  # insert bike rental

  # set bike availability to false

  # get bike info

  # send to main menu

You're getting close to done with the rent functionality. To add a rental to the database, you need the customer ID. Below the get customer_id comment, create a CUSTOMER_ID variable that gets the customer_id using the phone number.

1. Here's an example: CUSTOMER_ID=$($PSQL "<query_here>")

2. You want to get the customer_id column from the customers table using the PHONE_NUMBER variable in your condition to get it

3. The condition you want is WHERE phone = '$PHONE_NUMBER'

4. The query looks like this: SELECT customer_id FROM customers WHERE phone = '$PHONE_NUMBER'

5. Add CUSTOMER_ID=$($PSQL "SELECT customer_id FROM customers WHERE phone = '$PHONE_NUMBER'") below the get customer_id comment

Now that you have the bike ID and customer ID, you can add the rental to the database. Below the insert bike rental comment, create a INSERT_RENTAL_RESULT variable that adds the rental to the database.

1. Here's an example: INSERT_RENTAL_RESULT=$($PSQL "<query_here>")

2. View the rentals table by entering \d rentals in the psql prompt to see what the columns are

3. The query looks similar to this: INSERT INTO rentals(column1, column2) VALUES(value1, value2)

4. You want to insert the BIKE_ID_TO_RENT and CUSTOMER_ID variables into the bike_id and customer_id columns

5. The query should look like this: INSERT INTO rentals(bike_id, customer_id) VALUES($BIKE_ID_TO_RENT, $CUSTOMER_ID)

6. Add INSERT_RENTAL_RESULT=$($PSQL "INSERT INTO rentals(customer_id, bike_id) VALUES($CUSTOMER_ID, $BIKE_ID_TO_RENT)") below the insert bike rental comment

That should add the rental to the database. The last thing to do is set available to false for the bike. Below the set bike availability to false comment, create a SET_TO_FALSE_RESULT variable that does that.

1. Here's an example: SET_TO_FALSE_RESULT=$($PSQL "<query_here>")

2. You want to use the UPDATE, SET, and WHERE keywords

3. You want to set the available column to false for the bike_id of BIKE_ID_TO_RENT

4. The query looks similar to this: UPDATE <table> SET <column> = <value> WHERE <condition>

5. The query looks like this: UPDATE bikes SET available = false WHERE bike_id = $BIKE_ID_TO_RENT

6. Add SET_TO_FALSE_RESULT=$($PSQL "UPDATE bikes SET available = false WHERE bike_id = $BIKE_ID_TO_RENT") below the set bike availability to false comment

Run the script and go to the rent menu. Pick the first bike on the list and enter 555-5555 when it asks for a phone number again. That phone number should already be in the database, so it won't ask for a name or insert a customer.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure to enter the correct bike number and phone number

3. There should be a rental in the database for customer with phone number 555-5555 and name Me

In the psql prompt, view all the data in the rentals table. There should be a new rental.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM rentals; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

The rental was added and the date_rented was filled in automatically. 😄 Next, view all the data in the bikes table. Order the results by bike_id

1. Use the SELECT, FROM, and ORDER BY keywords with * to view all the data

2. Enter SELECT * FROM bikes ORDER BY bike_id; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

The available column was set to false for the bike you rented. The last thing to do is give a nice message about the rental. Below the get bike info comment, create a BIKE_INFO variable that gets the size and type, in that order, of the bike rented.

1. Here's an example: BIKE_INFO=$($PSQL "<query_here>")

2. You want to use the SELECT, FROM, and WHERE keywords

3. Use the BIKE_ID_TO_RENT variable to find the needed info for the bike

4. The query looks similar to this: SELECT size, type FROM <table> WHERE <condition>

5. The condition you want is WHERE bike_id = $BIKE_ID_TO_RENT

6. The query looks like this: SELECT size, type FROM bikes WHERE bike_id = $BIKE_ID_TO_RENT

7. Add BIKE_INFO=$($PSQL "SELECT size, type FROM bikes WHERE bike_id = $BIKE_ID_TO_RENT") below the get bike info comment

Below the variable you just created, use echo to print it.

1. Print a variable like this: echo $<VARIABLE_NAME>

2. The variable you want is BIKE_INFO

3. Add echo $BIKE_INFO in the suggested area

Run the script again and go to the rent menu, there should now be one less bike displayed. Pick the next bike on the list and rent it using the customer with phone number 555-5555 again so you can see the variable.

1. Enter ./bike-shop.sh in the terminal and press enter

2. There should be at least two rentals for the customer with phone nummber 555-5555 and name Me

It should have printed 28 | Mountain. The message you want to print after someone rents a bike would have said I have put you down for the 28" Mountain Bike, Me.. You need to format that variable for the message. The sed command can be used to replace characters and patterns in text. It looks like this: sed s/<regex_pattern_to_replace>/<characters_to_replace_with>/<regex_flags>. In the terminal, enter echo '28 | Mountain' | sed 's/ /=/g' to practice.

1. Enter the suggested command in the terminal

2. Not the psql one

The command you used, "piped" a string (28 | Mountain) to the sed command, where it replaced all the spaces with =. Enter the same command, but replace all the spaces with nothing.

1. The previous command was echo '28 | Mountain' | sed 's/ /=/g'

2. Remove the = from the previous command

3. Enter echo '28 | Mountain' | sed 's/ //g' in the terminal

The g regex flag stands for "global". It will replace all instance of the pattern. In this case, it replaced all the spaces. Enter the same command but without that flag.

1. The previous command was echo '28 | Mountain' | sed 's/ //g

2. Remove the g flag from the previous command

3. Enter echo '28 | Mountain' | sed 's/ //' in the terminal

That time, only the first instance of the pattern was replaced. The first space was removed. Enter the same command, but replace the first instance of  | (<space>|) with nothing.

1. The previous command was echo '28 | Mountain' | sed 's/ //

2. You want to replace the space in the pattern of the last command with  | (<space_here>|)

3. Enter echo '28 | Mountain' | sed 's/ |//' in the terminal

Enter the same command, but make the output look like how you want in the message, 28" Mountain.

1. The previous command was echo '28 | Mountain' | sed 's/ |//

2. Use " as the character to replace  | (<space>|) with

3. Enter echo '28 | Mountain' | sed 's/ |/"/' in the terminal

Back in your script, where you echo the BIKE_INFO, pipe the output into a sed command that replaces  | (<space>|) with " so the text will read <SIZE>" <TYPE>. 28 | Mountain would become 28" Mountain, for instance.

1. The previous command was echo '28 | Mountain' | sed 's/ |/"/'

2. You want to add the | sed 's/ |/"/' part of the previous command after your echo $BIKE_INFO line

3. Make the suggested area look like this:

echo $BIKE_INFO | sed 's/ |/"/'
Run the script and rent another bike using the customer with phone number 555-5555 again. Make sure the bike info printed looks like you want.

1. Enter ./bike-shop.sh in the terminal and press enter

2. The customer with phone number 555-5555 and name Me should have at least three bikes rented

Now it is formatted for the message. Take that echo command and the part that formats it, put it in a sub shell, and set the output into a variable named BIKE_INFO_FORMATTED. Here's an example: BIKE_INFO_FORMATTED=$(<formatted info here>)

1. You want to put the echo $BIKE_INFO | sed 's/ |/"/' part in the subshell

2. It should look like this: BIKE_INFO_FORMATTED=$(echo $BIKE_INFO | sed 's/ |/"/')

What you put the in subshell ($(...)) will be executed, and the result of it will replace the subshell. In this case, the formatted bike info was printed when you ran the script before, so the BIKE_INFO_FORMATTED variable will be set to that. Below the send to main menu comment, send users to the main menu with a message that would print I have put you down for the 28" Mountain Bike, Me. if Me rented the 28 inch Mountain Bike.

1. Use dynamic info for the bike info and the customer's name

2. You want to use the BIKE_INFO_FORMATTED and CUSTOMER_NAME variables

3. The message should look like this: I have put you down for the $BIKE_INFO_FORMATTED Bike, $CUSTOMER_NAME.

4. Add MAIN_MENU "I have put you down for the $BIKE_INFO_FORMATTED Bike, $CUSTOMER_NAME." below the send to main menu comment

Run the script and rent the next bike on the list. Use the customer with 555-5555 as their phone number. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. The customer with phone number 555-5555 and name Me should have at least four bikes rented

There's an extra space around the customer's name. You can use sed again to fix that. In the terminal, enter echo ' M e ' to print M e with spaces around it to see if you can find out how.

1. Enter the echo ' M e ' in the terminal

2. Not the psql one

It printed, but you can only assume there's a space at the end. Place the last command in a subshell with quotes around it. Put a period right after the subshell and echo the whole thing in the terminal. Here's how it looks: echo "$(echo ' M e ')."

1. Enter echo "$(echo ' M e ')." in the terminal

Now you can be certain there's a space at the end. Within the subshell of the last command, use a pipe and the sed command to replace the first space with no space. Here's the sed replacement pattern you want: 's/ //'.

1. The previous command was echo "$(echo ' M e ')."

2. Here's an example of how the subshell should look: $(echo ' M e ' | sed <pattern>)

3. This is the exact subshell: $(echo ' M e ' | sed <pattern>)

4. Enter echo "$(echo ' M e ' | sed 's/ //')." in the terminal

That removed only the first space it found. Change the previous command to replace all instances of a space instead of just the first one.

1. The previous command was echo "$(echo ' M e ' | sed 's/ //')."

2. Use a regex flag to make the suggested modification

3. You want to add the g flag to the sed replacement pattern.

4. The sed pattern should look like this: 's/ //g'

5. Enter echo "$(echo ' M e ' | sed 's/ //g')." in the terminal

That replaced all the spaces. You only had an extra space at the beginning of the customer name. Add a ^ in front of the space in the replacement pattern of the last command to only replace a space at the beginning of the text.

1. The previous command was echo "$(echo ' M e ' | sed 's/ //g')."

2. You want to change the matching pattern to ^  (^<space>)

3. The matching pattern is between the first and second forward slashes

4. The sed pattern should look like this: s/^ //g

5. Enter echo "$(echo ' M e ' | sed 's/^ //g')." in the terminal

The caret you added means that's the start of the text. So it will replace a space only if it's at the beginning. Enter the last command, but add two more spaces (three total) at the beginning of the text.

1. The previous command was echo "$(echo ' M e ' | sed 's/^ //g')."

2. Change the ' M e ' part to include the suggestion

3. The new text should be '   M e ' ('<three_spaces>M e ')

4. In the terminal, enter echo "$(echo '   M e ' | sed 's/^ //g')."

The ^  (^<space>) pattern only replaced the first space. Add * at the end of the matching pattern to replace all spaces at the beginning of text.

1. The previous command was echo "$(echo '   M e ' | sed 's/^ //g')."

2. The matching pattern is between the first and second forward slash

3. The new pattern is: 's/^ *//g'

4. Enter echo "$(echo '   M e ' | sed 's/^ *//g')." in the terminal

The customer name only had an extra space at the beginning. Unsure as to why, but there may be others with extra spaces at the end as well. You can match the end of text with $. Change the matching pattern of the last command so it replaces a single space at the end. The pattern is  $ (<space>$).

1. The previous command was echo "$(echo '   M e ' | sed 's/^ *//g')."

2. The matching pattern is between the first and second forward slash

3. Change the matching pattern to the suggestion

4. Enter echo "$(echo '   M e ' | sed 's/ $//g')." in the terminal

Add two more spaces to the end of the text in the previous command (three spaces total).

1. The previous command was echo "$(echo '   M e ' | sed 's/ $//g')."

2. The matching pattern is between the first and second forward slash

3. Change the matching pattern to the suggestion

4. Enter echo "$(echo '   M e   ' | sed 's/ $//g')." in the terminal

The pattern only replaces a single space at the end. Change the last command so it replaces all spaces at the end of the text.

1. The previous command was echo "$(echo '   M e   ' | sed 's/ $//g')."

2. Use * in a pattern after a character to replace zero or more of that character

3. The matching pattern you want is  *$ (<space>*$)

4. Change the matching pattern to the suggestion

5. Enter echo "$(echo '   M e   ' | sed 's/ *$//g')." in the terminal

That replaced all the spaces at the end of the text. You can use | as an "or" operator in a matching pattern to replace one pattern or another. Use it to change the matching pattern so it would replace any amount of spaces at the beginning and any amount of spaces at the end of the text.

1. The previous command was echo "$(echo '   M e   ' | sed 's/ *$//g')."

2. You want to replace the ^ * (^<space>*) pattern

3. And the  *$ (<space>*$) pattern

4. The matching pattern should look like this: 's/^ *| *$//g'

5. Enter echo "$(echo '   M e   ' | sed 's/^ *| *$//g')."

That didn't work. It doesn't like that "or" (|) operator for some reason. Check the manual of the sed command to see if you can find anything.

1. Here's an example of how to see a manual: man <command>

2. Enter man sed in the terminal

3. Press enter until you have seen the whole manual

Somewhere in there is a flag for using extended regular expressions with sed. That might work. Add it to the echo "$(echo '   M e   ' | sed 's/^ *| *$//g')." command that didn't work to find out.

1. 👇

2. Find the flag in the terminal output for using extended regular expressions with sed

3. It's the -E flag

4. You previously entered echo "$(echo '   M e   ' | sed 's/^ *| *$//g')."

5. Add the -E flag to the sed part of that command

6. Enter echo "$(echo '   M e   ' | sed -E 's/^ *| *$//g')." in the terminal

😉 That trimmed all spaces from the front and end of the text. Back in the last message of your script, place the CUSTOMER_NAME variable in a subshell, echo and pipe it into a sed command that removes all spaces from the front and back. Use the same method you used in the terminal.

1. Here's an example: $(echo $CUSTOMER_NAME | sed ...)

2. ^ * will match all spaces at the beginning of text, and  *$ will match spaces at the end

3. The previous command was echo "$(echo '   M e   ' | sed -r 's/^ *| *$//g')."

4. Change the $CUSTOMER_NAME variable in the last message to $(echo $CUSTOMER_NAME | sed -r 's/^ *| *$//g')

Run the script and rent another bike with the customer whose phone number is 555-5555. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. The customer with phone number 555-5555 and name Me should have at least five bikes rented

Run the script again. Rent another bike, use 000-0000 as the phone number this time, and Test as the name to create a new customer. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. The customer with phone number 000-0000 and name Test should have at least one bike rented

Run the script again. Rent another bike with the customer you just created. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. The customer with phone number 000-0000 and name Test should have at least two bikes rented

In the psql prompt, view all the data in your bikes table in order by the bike_id.

1. Use the SELECT, FROM, and ORDER BY keywords with * to view all the data

2. Enter SELECT * FROM bikes ORDER BY bike_id; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

There should be two bikes left available to rent. Next, look at all the data in the customers table.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM customers; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

There should two customers in that table now. Lastly, look at all the data in the rentals table.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM rentals; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

The rent functionality looks like it all works. Delete the echo Return Menu line in the RETURN_MENU function so you can get started with that.

1. The RETURN_MENU function should be empty

2. The RETURN_MENU function should look like this:

RETURN_MENU() {

}
Add three single line comments to the return menu function; get customer info, if not found, and send to main menu, in that order.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. The comments should be in the RETURN_MENU function

4. The RETURN_MENU function should look like this:

RETURN_MENU() {
  # get customer info

  # if not found

  # send to main menu

}
Below the get customer info comment you just added, print What's your phone number? with a new line in front of the sentence.

1. Use echo with the -e flag and the new line character (\n) to print the suggested message

2. Use double quotes around the message

3. Here's an example: echo -e "\n<message_here>"

4. Add echo -e "\nWhat's your phone number?" below the suggested comment

Just below that, use read to get input into a PHONE_NUMBER variable.

1. Here's an example: read <VARIABLE_NAME>

2. Add read PHONE_NUMBER to the suggested area

3. Add it below where you print What's your phone number?

Just below that, set the CUSTOMER_ID variable to a query that gets the customer ID from the database using the phone number they gave you.

1. Here's an example: CUSTOMER_ID=$($PSQL "<query_here>")

2. You want to get the customer_id column from the customers table using the PHONE_NUMBER variable in your condition to get it

3. The condition you want is WHERE phone = '$PHONE_NUMBER'

4. The query looks like this: SELECT customer_id FROM customers WHERE phone = '$PHONE_NUMBER'

5. Add CUSTOMER_ID=$($PSQL "SELECT customer_id FROM customers WHERE phone = '$PHONE_NUMBER'") below the read PHONE_NUMBER line in the RETURN_MENU function

If they are in the database, the variable will be their customer_id. If not, it will be empty. Below the if not found comment, add an if statement that checks if it's empty. Put the send to main menu comment in the then area.

1. Here's an example:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
fi
2. The condition you want is -z $CUSTOMER_ID

3. Place the # send to main menu comment in the <STATEMENTS> area

4. The if condition should look like this:

if [[ -z $CUSTOMER_ID ]]
then
  # send to main menu

fi
If the customer isn't found, send them to the main menu with the message I could not find a record for that phone number.

1. You want to call the MAIN_MENU function with the message as an argument

2. Here's an example: MAIN_MENU "<message_here>"

3. Add MAIN_MENU "I could not find a record for that phone number." below the send to main menu comment

Run the script and go to the return menu. Enter a phone number that is not in the database. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Add an else to the if condition for if the phone number is found in the database. Place get customer's rentals, if no rentals, and send to main menu in the else area as single line comments.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. The comments should be in the else area of the if [[ -z CUSTOMER_ID ]] statement

4. An if/else statement looks like this:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
else
  <STATEMENTS>
fi
5. The else area should look like this:

else
  # get customer's rentals

  # if no rentals

  # send to main menu

fi
6. The whole if should look like this:

if [[ -z $CUSTOMER_ID  ]]
then
  # send to main menu
  MAIN_MENU "I could not find a record for that phone number."
else
  # get customer's rentals

  # if no rentals

  # send to main menu

fi
You want to find out what rentals a customer has using their phone number and display them. You will need to join all the tables. Start by using the psql prompt to view all the data in the bikes table.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM bikes; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Next, use a LEFT JOIN with bikes as the left table to join the bikes and rentals tables. Use the USING keyword to join the two tables.

1. You need the SELECT, FROM, LEFT JOIN, and USING keywords

2. Here's an example: SELECT <column> FROM <table_1> LEFT JOIN <table_2> USING(<foreign_key>)

3. Enter \d bikes or \d rentals in the psql prompt to view the details of the table and find the foreign key column

4. It's the bike_id column

5. Enter SELECT * FROM bikes LEFT JOIN rentals USING(bike_id); in the psql prompt

6. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

You only need the bikes that are being rented. Use an inner join with the same two tables to only get those. Use the USING keyword again.

1. It's an INNER JOIN

2. You need the SELECT, FROM, INNER JOIN, and USING keywords

3. Here's an example: SELECT <column> FROM <table_1> INNER JOIN <table_2> USING(<foreign_key>)

4. Enter SELECT * FROM bikes INNER JOIN rentals USING(bike_id); in the psql prompt

5. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Add a join to the previous command that joins the last table so you can get the customer information. Use an INNER JOIN and the USING keyword again.

1. The previous query was SELECT * FROM bikes INNER JOIN rentals USING(bike_id);

2. Here's an example: SELECT <column> FROM <table_1> INNER JOIN <table_2> USING(<foreign_key>) INNER JOIN <table_3> USING(foreign_key)

3. Enter \d rentals or \d customers in the psql prompt to view the details of the table and find the foreign key column

4. It's the customer_id column

5. Enter SELECT * FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id); in the psql prompt

6. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Add two conditions to the last query to narrow down the results to the bikes that are currently being rented by customer with 555-5555 as their phone number. The second condition should check the date_returned column

1. The previous query was SELECT * FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id);

2. You want to add a WHERE <condition_1> AND <condition_2> to the last query

3. Use the IS NULL keyword to check the date_returned in one of the conditions

4. The two conditions are WHERE phone = '555-5555' AND date_returned IS NULL

Now you have all the rentals for one specific customer. Only get the columns you need to display the bike information to them. They are the same three columns you used to display the list of available bikes.

1. The previous query was SELECT * FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND date_returned IS NULL;

2. The three columns you want are bike_id, type, and size

3. Enter SELECT bike_id, type, size FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND date_returned IS NULL; in the psql prompt

4. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

One more thing, order the results of the last query by their bike_id column.

1. The previous query was SELECT bike_id, type, size FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND date_returned IS NULL;

2. Add ORDER BY bike_id to the end of the last query

3. Enter SELECT bike_id, type, size FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND date_returned IS NULL ORDER BY bike_id; in the psql prompt

4. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

That's the query you will need to use to get the bikes a customer is renting. In your script below the get customer's rentals comment. Create a CUSTOMER_RENTALS variable that gets the rentals for the customer. Use the PHONE_NUMBER variable to get them.

1. Here's an example: CUSTOMER_RENTALS=$($PSQL "<query_here>")

2. You previously entered SELECT bike_id, type, size FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND date_returned IS NULL ORDER BY bike_id; in the psql prompt

3. All the columns and tables should be in the same order as in the above query

4. The query looks like this: SELECT bike_id, type, size FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id) WHERE phone = '$PHONE_NUMBER' AND date_returned IS NULL ORDER BY bike_id

5. Add CUSTOMER_RENTALS=$($PSQL "SELECT bike_id, type, size FROM bikes INNER JOIN rentals USING(bike_id) INNER JOIN customers USING(customer_id) WHERE phone = '$PHONE_NUMBER' AND date_returned IS NULL ORDER BY bike_id") below the get customer's rentals comment

Below the variable you just created, use echo to print it. Make sure to put double quotes around it.

1. Here's an example: echo "<variable_here>"

2. Use the variable with $CUSTOMER_RENTALS

3. Add echo "$CUSTOMER_RENTALS" to the suggested area

Run the script and go to the return menu. Enter 555-5555 for the phone number to see the rentals for Me.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

The query is working. If the customer has no rentals, the variable will be empty. Below the if no rentals comment, add an if condition that checks if it's empty. Put the send to main menu comment in the then area again.

1. Here's an example:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
fi
2. The condition you want is -z $CUSTOMER_RENTALS

3. Place the # send to main menu comment in the <STATEMENTS> area

4. The if condition should look like this:

if [[ -z $CUSTOMER_RENTALS ]]
then
  # send to main menu

fi
If the customer has no rentals, send them to the main menu with the message You do not have any bikes rented. Add the code below the next comment.

1. You want to call the MAIN_MENU function with the message as an argument

2. Here's an example: MAIN_MENU "<message_here>"

3. Add MAIN_MENU "You do not have any bikes rented." below the send to main menu comment

Add an else to the condition for when the customer does have rentals. Place four single line comments in it; display rented bikes, ask for bike to return, if not a number, and send to main menu.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. The comments should be in the else area of the if [[ -z CUSTOMER_RENTALS ]] statement

4. The else area should look like this:

else
  # display rented bikes

  # ask for bike to return

  # if not a number

  # send to main menu

fi
5. The whole if should look like this:

if [[ -z $CUSTOMER_RENTALS  ]]
then
  # send to main menu
  MAIN_MENU "You do not have any bikes rented."
else
  # display rented bikes

  # ask for bike to return

  # if not a number

  # send to main menu

fi
Below the display rented bikes comment, print Here are your rentals: with a new line in front of it.

1. Use echo with the -e flag and the new line character (\n) to print the suggested message

2. Use double quotes around the message

3. Here's an example: echo -e "\n<message_here>"

4. Add echo -e "\nHere are your rentals:" below the suggested comment

Move the echo $CUSTOMER_RENTALS line to below the line you just printed.

1. Move the suggested code below where you print Here are your rentals:

2. You should only print the variable in that one spot

3. Place the echo "$CUSTOMER_RENTALS" line in the suggested spot

Run the script and go to the return menu. Enter 555-5555 for the phone number to see the rented bikes.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Where you print the list of rented bikes, pipe the command into a while loop that reads the data. You should read the data into BIKE_ID, BAR, TYPE, BAR, and SIZE variables. Make it print each rented bike in the same fashion as the list of available bikes.

1. Here's an example:

echo "$CUSTOMER_RENTALS" | while read <VARIABLES>
do
  echo <RENTED_BIKE_INFORMATION>
done
2. The first line should look like this: echo "$CUSTOMER_RENTALS" | while read BIKE_ID BAR TYPE BAR SIZE

3. The loop should print 1) 27" Mountain Bike for each bike with the appropriate bike info

4. The whole thing looks like this:

echo "$CUSTOMER_RENTALS" | while read BIKE_ID BAR TYPE BAR SIZE
do
  echo "$BIKE_ID) $SIZE\" $TYPE Bike"
done
Run the script and go to the return menu. Enter the same phone number again to make sure the list is showing up correctly.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Below the ask for bike to return comment, print Which one would you like to return? with a new line in front of it.

1. Use echo with the -e flag and the new line character (\n) to print the suggested message

2. Use double quotes around the message

3. Here's an example: echo -e "\n<message_here>"

4. Add echo -e "\nWhich one would you like to return?" below the suggested comment

Below the line you just printed, read input into a BIKE_ID_TO_RETURN variable.

1. Here's an example: read <VARIABLE_NAME>

2. Add read BIKE_ID_TO_RETURN to the suggested area

3. Add it below where you print Which one would you like to return?

Below the if not a number comment, check if the input for the bike ID to return is a number using the same method you did earlier. Place the send to main menu comment in the statement.

1. Here's an example:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
fi
2. The condition should check that the $BIKE_ID_TO_RETURN variable is not a number using the pattern matching operator (=~) and the pattern ^[0-9]+$

3. The condition you want is [[ ! $BIKE_ID_TO_RETURN =~ ^[0-9]+$ ]]

4. Place the # send to main menu comment in the <STATEMENTS> area

5. The if condition should look like this:

if [[ ! $BIKE_ID_TO_RETURN =~ ^[0-9]+$ ]]
then
  # send to main menu

fi
If they don't input a number, send them to the main menu with That is not a valid bike number. as the message.

1. You want to call the MAIN_MENU function with the message as an argument

2. Here's an example: MAIN_MENU "<message_here>"

3. Add MAIN_MENU "That is not a valid bike number." below the send to main menu comment

Add an else for when they do input a number. Place check if input is rented, if input not rented, and send to main menu single line comments in it.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. The comments should be in the else area of the if [[ ! $BIKE_ID_TO_RETURN =~ ^[0-9]+$ ]] statement

4. The else area should look like this:

else
  # check if input is rented

  # if input not rented

  # send to main menu

fi
5. The whole if should look like this:

if [[ ! $BIKE_ID_TO_RETURN =~ ^[0-9]+$ ]]
then
  # send to main menu
  MAIN_MENU "That is not a valid bike number."
else
  # check if input is rented

  # if input not rented

  # send to main menu

fi
You need to check if the input is a bike_id rented by the customer so you can return it. In the psql prompt, join the rentals and customers tables with an INNER JOIN using the USING keyword.

1. You need the SELECT, FROM, INNER JOIN, and USING keywords

2. Here's an example: SELECT <column> FROM <table_1> INNER JOIN <table_2> USING(<foreign_key>)

3. Enter \d rentals or \d customers in the psql prompt to view the details of the table and find the foreign key column

4. It's the customer_id column

5. Enter SELECT * FROM rentals INNER JOIN customers USING(customer_id); in the psql prompt

6. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Add three conditions to the previous query. Check the phone, bike_id, and date_returned columns to narrow the results to the first bike you rented with Me.

1. The previous query was SELECT * FROM rentals INNER JOIN customers USING(customer_id);

2. You want to add a WHERE <condition_1> AND <condition_2> AND <condition_3> to the last query

3. Use the IS NULL keyword to check the date_returned in one of the conditions

4. The other two conditions should check the phone and bike_id of the first rental

5. The three conditions are WHERE phone = '555-5555' AND bike_id = 1 AND date_returned IS NULL

6. Enter SELECT * FROM rentals INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND bike_id = 1 AND date_returned IS NULL; in the psql prompt

7. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

You only need to know what bike is going to be returned. Narrow the columns from the last query to only get the one column you would need for returning a bike.

1. The previous query was SELECT * FROM rentals INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND bike_id = 1 AND date_returned IS NULL;

2. Only column you need is the rental_id column

3. Enter SELECT rental_id FROM rentals INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND bike_id = 1 AND date_returned IS NULL; in the psql prompt

4. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Back in the script, below the check if input is rented comment, create a RENTAL_ID variable that gets the rental ID of the bike that was input.

1. The input is the BIKE_ID_TO_RETURN variable

2. Here's an example: RENTAL_ID=$($PSQL "<query_here>")

3. You previously entered SELECT rental_id FROM rentals INNER JOIN customers USING(customer_id) WHERE phone = '555-5555' AND bike_id = 1 AND date_returned IS NULL; in the psql prompt

4. Be sure to use the same columns from the above query for the conditions with the PHONE_NUMBER and BIKE_ID_TO_RETURN variables

5. Add RENTAL_ID=$($PSQL "SELECT rental_id FROM rentals INNER JOIN customers USING(customer_id) WHERE phone = '$PHONE_NUMBER' AND bike_id = $BIKE_ID_TO_RETURN AND date_returned IS NULL") below the check if input is rented comment

Below the if input not rented comment, add an if that checks if the RENTAL_ID variable is empty. Place the send to main menu comment in the then area.

1. Here's an example:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
fi
2. The condition you want is -z $RENTAL_ID

3. Place the # send to main menu comment in the <STATEMENTS> area

4. The if condition should look like this:

if [[ -z $RENTAL_ID ]]
then
  # send to main menu

fi
If the input isn't rented by the given customer, send them to the main menu with You do not have that bike rented. as the message.

1. You want to call the MAIN_MENU function with the message as an argument

2. Here's an example: MAIN_MENU "<message_here>"

3. Add MAIN_MENU "You do not have that bike rented." below the send to main menu comment

Add an else to the if condition you just added. Use echo to print Rental ID $RENTAL_ID found in it so you can see if it's all working.

1. Here's an example:

if [[ <CONDITION> ]]
then
  <STATEMENTS>
else
  <STATEMENTS>
fi
2. Place echo "Rental ID $RENTAL_ID found" in the else area

3. The if condition should look like this:

if [[ -z $RENTAL_ID ]]
then
  # send to main menu
  MAIN_MENU "You do not have that bike rented."
else
  echo "Rental ID $RENTAL_ID found"
fi
Run the script and go to the return menu. Enter 555-5555 to see the rented bikes. Input a bike that isn't on the list, then go to the menu again and input a bike that is on the list.

1. Enter ./bike-shop.sh in the terminal and press enter

2. Make sure you are in the project folder first

Looks like it works. Delete the line where you print the rental ID.

1. Delete the echo "Rental ID $RENTAL_ID found" line

Add three single line comments in the else area; update date_returned, set bike availability to true, and send to main menu.

1. Here's an example of a single line comment: # <comment_here>

2. Make sure the comments are in the same order listed

3. The comments should be in the else area of the if [[ -z $RENTAL_ID ]] statement

4. The else area should look like this:

else
  # update date_returned

  # set bike availability to true

  # send to main menu

fi
5. The whole if should look like this:

if [[ -z $RENTAL_ID ]]
then
  # send to main menu
  MAIN_MENU "You do not have that bike rented."
else
  # update date_returned

  # set bike availability to true

  # send to main menu

fi
After a person picks a bike to return and you know that it's a bike they have rented, you need to update all the info in the database to return it. Below the update date_returned comment, create a RETURN_BIKE_RESULT variable that sets the date_returned column to NOW() for the bike rented. Use the RENTAL_ID to figure out which row to update.

1. Here's an example: RETURN_BIKE_RESULT=$($PSQL "<query_here>")

2. You want to use the UPDATE, SET, NOW(), and WHERE keywords in the query

3. Here's an example of the query: UPDATE <table> SET <column> = <value> WHERE <condition>

4. The query you want is UPDATE rentals SET date_returned = NOW() WHERE rental_id = $RENTAL_ID

5. Add RETURN_BIKE_RESULT=$($PSQL "UPDATE rentals SET date_returned = NOW() WHERE rental_id = $RENTAL_ID") below the update date_returned comment

That should update the rentals table. Lastly, you need to make the bike available again. Below the set bike availability to true comment, create a SET_TO_TRUE_RESULT variable that makes the bike available again.

1. Here's an example: SET_TO_TRUE_RESULT=$($PSQL "<query_here>")

2. You want to use the UPDATE, SET, and WHERE keywords in the query

3. You want to update the available column to true for the bike with BIKE_ID_TO_RETURN

4. The query you want is UPDATE bikes SET available = true WHERE bike_id = $BIKE_ID_TO_RETURN

5. Add SET_TO_TRUE_RESULT=$($PSQL "UPDATE bikes SET available = true WHERE bike_id = $BIKE_ID_TO_RETURN") below the set bike availability to true comment

After all that is done, send them to the main menu with Thank you for returning your bike. as the message.

1. Add the code below the last send to main menu comment

2. You want to call the MAIN_MENU function with the message as an argument

3. Here's an example: MAIN_MENU "<message_here>"

4. Add MAIN_MENU "Thank you for returning your bike." below the send to main menu comment

Run the script and return one of the bikes that Me has rented out. When you are done, exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. The customer with phone number 555-5555 and name Me should have at least one rental with the date_returned column not null

In the psql prompt, view all the data in the rentals table.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM rentals; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

Now the rental has been returned. View all the data in the bikes table in order by their bike_id.

1. Use the SELECT and FROM keywords with * to view all the data

2. Enter SELECT * FROM bikes ORDER BY bike_id; in the psql prompt

3. You can type psql --username=freecodecamp --dbname=bikes into the terminal to log in to psql if you aren't logged in.

And the bike is available again. This is the last step. Run the script once more. Feel free to play around, rent and return some bikes. When you are ready to be done, return all the bikes you rented and exit the program.

1. Enter ./bike-shop.sh in the terminal and press enter

2. All rentals should have a date_returned value, and all bikes should have available set to true
