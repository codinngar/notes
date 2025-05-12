## What is database?
A database is an organized collection of structured information, or data, typically stored electronically in a computer system. A database is usually controlled by a database management system.

## What Is Structured Query Language (SQL)?
SQL is a programming language used by nearly all relational databases to query, manipulate, and define data, and to provide access control.

## Types of Databases

- **Relational databases**
	Items in a relational database are organized as a set of tables with columns and rows. Relational database technology provides the most efficient and flexible way to access structured information.

- **Object-oriented databases**
	Information in an object-oriented database is represented in the form of objects, as in object-oriented programming.

- **Distributed databases**
	A distributed database consists of two or more files located in different sites. The database may be stored on multiple computers, located in the same physical location, or scattered over different networks.

- **Data warehouses**
	A central repository for data, a data warehouse is a type of database specifically designed for fast query and analysis.

- **NoSQL databases**
	A NoSQL, or nonrelational database, allows unstructured and semistructured data to be stored and manipulated (in contrast to a relational database, which defines how all data inserted into the database must be composed). NoSQL databases grew popular as web applications became more common and more complex.

- **Graph databases**
	A graph database stores data in terms of entities and the relationships between entities.

- **Open source databases**
	An open source database system is one whose source code is open source; such databases could be SQL or NoSQL databases.

- **Cloud databases**
	A cloud database is a collection of data, either structured or unstructured, that resides on a private, public, or hybrid cloud computing platform. There are two types of cloud database models: traditional and database as a service (DBaaS). With DBaaS, administrative tasks and maintenance are performed by a service provider.

- **Multimodel database**
	Multimodel databases combine different types of database models into a single, integrated back end. This means they can accommodate various data types.

- Document/JSON database
	Designed for storing, retrieving, and managing document-oriented information, document databases are a modern way to store data in JSON format rather than rows and columns.

- **Self-driving databases**
	The newest and most groundbreaking type of database, self-driving databases (also known as autonomous databases) are cloud-based and use machine learning to automate database tuning, security, backups, updates, and other routine management tasks traditionally performed by database administrators.

## What Is Database Software?
Database software is used to create, edit, and maintain database files and records, enabling easier file and record creation, data entry, data editing, updating, and reporting. The software also handles data storage, backup and reporting, multi-access control, and security. Strong database security is especially important today, as data theft becomes more frequent. Database software is sometimes also referred to as a “database management system” (DBMS).
Database software makes data management simpler by enabling users to store data in a structured form and then access it. It typically has a graphical interface to help create and manage the data and, in some cases, users can construct their own databases by using database software.

## What Is a Database Management System (DBMS)?
A database typically requires a comprehensive database software program known as a database management system (DBMS). A DBMS serves as an interface between the database and its end users or programs, allowing users to retrieve, update, and manage how the information is organized and optimized. A DBMS also facilitates oversight and control of databases, enabling a variety of administrative operations such as performance monitoring, tuning, and backup and recovery.
Some examples of popular database software or DBMSs include MySQL, Microsoft Access, Microsoft SQL Server, FileMaker Pro, Oracle Database, and dBASE.

## What are the key features of a database management system?
- **Data storage**: Data can be structured, unstructured, or semi-structured. A DBMS should be able to organize and manage data.
- **Data retrieval and manipulation**: A DBMS allows users to query data with specific query languages such as SQL, PL\SQL, and KQL. Users can run commands such as inserts, updates, and deletes to perform database activities.
- **Data integrity and concurrency control**: A DBMS includes mechanisms to ensure data is accurate and consistent, and multiple users can work on the data without affecting its consistencies or conflicts.
- **Security**: A DBMS supports user authentication, authorization, and encryption mechanisms to ensure data is safe and secure while data is at rest or motion.
- **Backup and recovery**: A DBMS supports database backup and restoration mechanisms to safeguard against data loss or corruption. It should allow data recovery quickly, securely, and safely.
- **Consistency**: A DBMS ensures data is accurate, consistent, and anomalies-free. Any transaction should be a complete success or failure, not a partial failure or success.
- **Indexing**: A DBMS supports various indexing mechanisms for faster data retrieval and query performance tuning.

## What are the four types of DBMS?

**1. Relational Database Management Systems (RDBMS)**:
- An RDBMS organizes the structured data into tables. A table consists of rows and columns.
- Each table has a pre-defined schema with columns and their data types.
- It allows for setting up relationships among different tables.
- Examples include Microsoft SQL Server, Oracle, and MySQL.

**2. NoSQL Database Management System**
- A NoSQL DBMS is suitable for handling unstructured data.
- It offers flexible schema and various data models as per data requirements.
1. Document oriented
2. Key value pairs
3. Wide Column databases
4. Graph databases

**3. Object-Oriented Database Management System (ODBMS)**:
- It stores data in the form of objects based on classes.
- It is suitable for handling complex data structures.
- It allows for the creation of classes and inheritance
- Examples include ObjectDB and db4o.

**4. Hierarchical Database Management System**:
- A hierarchical DBMS organizes data into parent-child relationships like a tree structure.
- Each parent can have multiple children, while each child record has only one parent.
- Example: IBM's Information Management System (IMS)

## What is an example of a database management system?

**MySQL:** MySQL is a widely used open-source RDBMS. It is known for its speed, reliability, and ease of use. MySQL is often used in web applications and is a vital component of the Linux, Apache, MySQL, PHP/Perl/Python stack.  

**Microsoft SQL Server:** It is Microsoft's database management system suitable for following workloads.
- Online Transaction Processing ( OLTP)
- Online Analytical Processing (OLAP)

**Oracle Database:** Oracle’s database is famous for its scalability, robustness, and enterprise features suitable for large and mission-critical applications.

**MongoDB:** MongoDB is a popular NoSQL database that uses a document-oriented data model. It is designed for flexibility, scalability, and handling of unstructured data. MongoDB is widely used in web and mobile applications.

**Neo4j:** Neo4j is a graph database that manages and queries data with complex relationships. It is ideal for applications involving social networks, recommendation engines, and knowledge graphs.

**Redis:** Redis is an open-source, in-memory data store often used as a key-value database or cache. It is known for its high-speed data retrieval and is used to build real-time applications and cache frequently accessed data.

**Couchbase:** Couchbase is a distributed NoSQL cloud database with unmatched versatility, performance, and scalability for cloud, mobile, AI, and edge computing applications. 

**PostgreSQL:** PostgreSQL is an open-source RDBMS with high extensibility and SQL compliance. It supports relational (SQL) and non-relational (JSON) queries with increased resilience, correctness, and integrity. It adds support for geospatial, JSON data types, and analytical applications.

## What is SQL?
Structured query language (SQL) is a programming language for storing and processing information in a relational database. You can use SQL statements to store, update, remove, search, and retrieve information from the database. You can also use SQL to maintain and optimize database performance.
