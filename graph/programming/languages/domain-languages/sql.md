In 1986, SQL (Structured Query Language) became a standard. Over the next 40 years, it became the dominant language for relational database management systems. Reading the latest standard (ANSI SQL 2016) can be time-consuming. How can I learn it?

There are 5 components of the SQL language:
- DDL: data definition language, such as CREATE, ALTER, DROP
- DQL: data query language, such as SELECT
- DML: data manipulation language, such as INSERT, UPDATE, DELETE
- DCL: data control language, such as GRANT, REVOKE
- TCL: transaction control language, such as COMMIT, ROLLBACK

Used for [[graph/programming/databases/databases|databases]]


![[attachments/Pasted image 20231105232738.png]]



## How is an SQL statement executed in the database?
![[attachments/Pasted image 20231105232157.png]]
1. A SQL statement is sent to the database via a transport layer protocol (e.g.TCP).
2. The SQL statement is sent to the command parser, where it goes through syntactic and semantic analysis, and a query tree is generated afterward.
3. The query tree is sent to the optimizer. The optimizer creates an execution plan.
4. The execution plan is sent to the executor. The executor retrieves data from the execution.
5. Access methods provide the data fetching logic required for execution, retrieving data from the storage engine.
6. Access methods decide whether the SQL statement is read-only. If the query is read-only (SELECT statement), it is passed to the buffer manager for further processing. The buffer manager looks for the data in the cache or data files.
7. If the statement is an UPDATE or INSERT, it is passed to the transaction manager for further processing.
8. During a transaction, the data is in lock mode. This is guaranteed by the lock manager. It also ensures the transaction’s ACID properties.

## Visualizing an SQL query
![[attachments/Pasted image 20231105232538.png]]
SQL statements are executed by the database system in several steps, including:
- Parsing the SQL statement and checking its validity
- Transforming the SQL into an internal representation, such as relational algebra
- Optimizing the internal representation and creating an execution plan that utilizes index information
- Executing the plan and returning the results

The execution of SQL is highly complex and involves many considerations, such as:
- The use of indexes and caches
- The order of table joins
- Concurrency control
- Transaction management