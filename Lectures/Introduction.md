	(Date 26/11/2024)
## Topic entire course:
- Database Concepts.
- Relational Database Model.
- Database Analysis.
- Conceptional Modelling and Database Design.
- Database Programming.
#### Ref
- C.J. Date An Introduction to Database Systems
- Elmasri & Navathe Fundamentals of Database Systems

External is the subset of conceptual view.
Conceptual view is logical level define the database gonna be

# Database
A database is a collection of data objects and relationships among them.
from an information system perspective.

There are several types of databases. Each type uses its own **representation** of objects and relationships. Also each type uses it s own **language(s)** and there are particular **rules (regulations)** on the representations Theses types of database use different **database models**.

Each DBMS software supports a database model.

The relational database model or the hierarchical database model are both Logical representations of objects and relationships.
So we don't compare logical database models in terms of speed and performance.
 
S

| S#  | SNAME | STATUS | CITY   |
| --- | ----- | ------ | ------ |
| S1  | SMITH | 20     | LONDON |
| S2  | JONES | 10     | PARIS  |
| S3  | BLAKE | 30     | PARIS  |

P

| S#  | SNAME | STATUS | CITY   |
| --- | ----- | ------ | ------ |
| S1  | SMITH | 20     | LONDON |
| S2  | JONES | 10     | PARIS  |
| S3  | BLAKE | 30     | PARIS  |

SP (Relational Database)

| S#  | P#  | QTY |
| --- | --- | --- |
| S1  | P1  | 300 |
| S2  | P2  | 200 |
| S3  | P3  | 400 |
```SQL
SELECT * FROM S WHERE CITY == PARIS AND STATUS ==  30
```
## Principle of the three level architecture.
![[Pasted image 20250115002902.png]]
- Individual user view (External Level) this level create to serve need of user application. View the necessary information also is the subset of conceptual level.
- Conceptual Level (Community user views) community data model level logical part.
- Internal Level (Storage views) physical
   
## Factor that influence the response time of a query (Database Statistics):
need to be precollected
- size of database table
- availability of index
- number of rows returned to each condition.
## Query Optimizer:
A module of the DBMS which finds the best physical route to the result.
## Rule-based optimizer:
users fired set if rules which may depend on the way programmers write the SQL code.
## Cost-based optimizer (Popular in the curtain of time):
uses **database statistics** for query optimization. (its like pre collect data)

## Conclusion:
Database is the collection of data object and relationship have various way to separate them. Even query have an optimizer to increase the performance.

# Database System Architecture
![[Pasted image 20250115012455.png]]write program on view make a bit slower to translate to main but increase privacy. The query on view is on the first time only.
![[Pasted image 20250115013651.png]]

# Good Characteristics of Database Systems
1. **Data Independence** - Changes made to data structures c logical or physical should not lead to changes classify into physical data independence: changes made to 
	**Physical Data Structures** and relation should not lead to changes of application programs.
	**Logical Data Independence**: changes made to the logical data structures should not lead to the changes of application programs. (Logical data structures changed: extended data structures remain unchanged, application program remain unchanged)
2. **High Degree of data privacy and security** - In principle, the DBMS should handle userID & password, Non-subversion
3. **High degree of data integrity** (correctness) - Information in the database must be correct according to integrity rules (integrity constraints, validation rules )
	**Example:**
	**R1:** Undergrad students can borrow at most 10 books.
		(Where to declare 1. Application (R1 declare here), 2. DBMS, 3. DB)
		Rules should be declared on the DB and be enforced by the DBMS (Recommend)
4. **High productivity data model, languages, and tools**.
5. **Data Management facilities and tools** - Concurrency control, recovery, query optimization, data distribution etc. are provided by the DBMS. 
	![[Pasted image 20250115151551.png]]
6. **Logically Centralized control** (Physically distributed centralized) - The database system should be managed by a control team called the DBA tram (Database Administrator)