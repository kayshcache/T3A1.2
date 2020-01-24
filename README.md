# T3A1.2
### Q1
All tables are divided into smaller entities. Database tables in a relational database have the following characteristics: They contain 1 or more fields and zero or many records, most likely an ID field and another field to hold a value mapped to that identifier. Each field in a database table of a relational database will have a datatype and potentially several more optional constraining characteristics, such as, parameters detailing whether the field value must be unique in the table, whether or not it can hold NULL values or require a value, and other charactistics can also be defined for each field. Records are created, deleted, mutated or read by software applications via database management systems that differ depending on the type of relational database employed. When creating a table in a relational database, field names must be specified in the CREATE TABLE query. The Relational Database Management System (RDBMS) defines the specifications of writing database queries (or commands) that generate, drop and manage tables.
### Q2
To be precise there are several more than three types of relationships in relational databases. The three referred to here are most likely: many-to-many, one-to-many, only-one-to-one. Primary and foreign keys are used in Many-to-Many relationships to represent relationships between data in one table and corresponding data in one or more other tables. This kind of relationship can be facilitated by a junction table. Junction tables work to represent the relationships by holding 2 or more foreign keys from other tables in their fields. They can be used to connect two tables and reduce the amount of repeated data that would be required to represent the many-to-many relationship. Junction tables cut down on record verbosity by dividing many-to-many relationships into 2 or more one-to-many and provide an additional table with fields that can be associated only with that relationship. For example students and classes can be connected with a students/classes junction that can hold additional data such as grades.
### Q3
Constraints in relational databases can be utilized to ensure data integrity by specifying rules for what data is represented in each table. This allows for limits to be placed on what data can be inserted when records are created. NOT NULL restructs the field from being NULL effectively making it required. In other words, at time of insertion values must be included in the query in order to successfully execute without error. UNIQUE can be used to reduce bloat of duplicate records. For example, if an email field of a user table is made UNIQUE it might stop users from creating multiple accounts when there is already on created from them in the database. A PRIMARY KEY (PK) is a combination of these two constraints, it must be both unique in the table and cannot be NULL, and as it often than an integer is used for the PK it is therefore possible to autoincrement the key creating an identifier for each record in the table. An interesting additional constraint is DEFAULT, it can be used to set a value when one is not send with the insertion query.
### Q4
Data types enforce data integrity in a relational database by restricting the kind of data value that can be inserted in a table. By being specific about what data type to expect from an insertion query it is possible to reduce considerably incorrect or false and misleading data from being entered into the database by users. For example, product prices must be decimal values in order to make calculations on that data elsewhere, such as in the business logic. If that data is not the anticipated datatype for the calculation errors can occur elsewhere in the database or in the program accessing it. Another example might be setting size limits of VARCHAR datatype fields by assigning a value indicating maximum length that can be inserted. DATE data types can be a very effecient way to time_stamp records as they are inserted. All of then reasons and more are what make data types an important facet of relational databases. The correct application of data types and field constraints can hugely mitigate the need to cleanse databases of corrupt of innaccurate data later in an applications lifecycle.
### Q5
The function of three operators provided by SQL operations for the definition and manipulation of data in a relational database are UPDATE, CREATE, and SELECT ... yada yada yada (check is that right first)
### Q6
Data manipulation is highly effective using SQL queries with relational databases via the use of a "JOIN". When retrieving data from multiple tables in a relational database, the INNER JOIN query can be used to manipulation the data returned by (for example) the SELECT statement. The INNER JOIN command retrieves data from multiple tables matching values in both tables. By using the INNER JOIN keyword it's possible to select all records from multiple tables when there is matching ID or primary key fields between them. A condition of there being records in a "Books" table that doesn't have matches in a corresponding "Authors" table won't show any of those unmatching records.

An example of complex INNER JOIN command can be seen below in this SELECT statement, it joins all books with their authors and publisher information found in a relational database:
```sql
SELECT Books.BookID, Authors.AuthorName, Publishers.PublisherName FROM ((Books
  INNER JOIN Authors ON Books.AuthorID = Authors.AuthorID)
  INNER JOIN Publishers ON Books.PublisherID = Publisher.PublisherID);
```
