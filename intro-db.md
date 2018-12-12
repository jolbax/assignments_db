### Questions

> What data types do each of these values represent?

- "A Clockwork Orange" -> `CHAR`
- 42 -> `INT`
- 09/02/1945 -> `DATE`
- 98.7 -> `FLOAT`
- $15.99 -> `VARCHAR`

> Explain when a database would be used. Explain when a text file would be used.

A: Basically a text file can be used when prototyping or testing an application. As long as there are no concurrent applications accessing writing to the text file there should be no problem.

But as soon as more advanced requirements for data persistence are needed a database should be used. Examples for advanced requirements are:

- Concurrent access to the data (read and write)
- Higher data loads to be managed.
- Data consistency. Every data change should be fully handled without interruption (otherwise rollback)
- Data availability. The database system should be robust, secure, stable
- Performance. Data processing tasks should be performed on the database and not the application.
- Etc...

> Describe one difference between SQL and other programming languages.

A: SQL is used to query data out databases of relational database systems. It is actually a domain specific language rather than an fully equipped programing language. This is the main difference of SQL and other programming languages.

SQL is a declarative, which means it focus its way of writing statements in "what" rather in "how" to do something.

> In your own words, explain how the pieces of a database system fit together at a high level.

A: The main components of a database system are:

- Hardware: is the actual computer/s where the DBMS is running on, including all I/O media, memory, processing power. And also the physical storage where data will be persistently stored.
- Software: rather middleware, is the programs controlling everything and providing the DB functionality.
- Data: are the bits and bites to be stored and managed by the DBMS, and the metadata describing the actual data.
- Procedures: are general instructions to user a DBMS.Eg. to manage databases, generate reports, make backups, etc.
- Database Access Language (Users): represents the main interface and tool for the user in order to interact with the DBMS. Clearly, it is also used by other applications.

> Explain the meaning of table, row, column, and value.

A:
- **Table** is the container of related data within a database and represents the smallest organizational component in a database. A table consist of data organized in rows and columns.
- **Rows** represents data entries in the database table. Rows consist of a list of values.
- **Columns** represent data attributes, which assign a meaning to the row fields.
- **Value** is the actual data being stored in the table. It represent the smallest data component of a table. A value should always have a data type and column attribute specifying the characteristics of the specific value.

> List three data types that can be used in a table.

A: VAR, INT, DATE

> Given this payments table, provide an English description of the following queries and include their results:

```
     SELECT date, amount
     FROM payments;

     SELECT amount
     FROM payments
     WHERE amount > 500;

     SELECT *
     FROM payments
     WHERE payee = 'Mega Foods';
```

- Provide a table, listing payments with its dates and respectively amounts

```
Date           Amount
5/1/2016       1500.00
5/10/2016      37.00
5/15/2016      124.93
5/23/2016      54.72
```

- Provide a table, listing the amount of payments that are greater than 500

```
Amount
1500.00
```
- Provide a table, listing all information available of payments that its payee is "Mega Foods"

```
Date      Payee          Amount    Memo
5/15/2016 Mega Foods     124.93    Groceries
```

> Given this users table, write SQL queries using the following criteria and include the output:

- The email and sign-up date for the user named DeAndre Data.
- The user ID for the user with email 'aleesia.algorithm@uw.edu'.
- All the columns for the user ID equal to 4.

```
SELECT email, signup FROM users WHERE name='DeAndre Data';

// Output:
//   email             |      signup
// --------------------+-----------------
//   datad@comcast.net |      2008-01-20

SELECT userid FROM users WHERE email='aleesia.algorithm@uw.edu';

// Output
//   userid
// ----------
//     1

SELECT * FROM users WHERE userid=4;

// Output
// userid | name           | email             | signup
// -------+----------------+-------------------+--------
// 4	     | Brandy Boolean | bboolean@nasa.gov | 1999-10-15
```