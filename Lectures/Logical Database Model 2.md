(Date 17/12/2024)
## Basic Structure
"Relation is the subset of cartesian product."
customer_name = {Jones, Smith, Curry, Lindsay}
customer_street = {Main, North, Park}
customer_city = {Harrison, Rye, Pittsfield}

It has only one relation that been true.
Then r = {(Jones, Main, Harrison), (Smith, North, Rye), (Curry, North, Rye), (Lindsay, Park Pittsfield)}

Domain is data part and the header is the value. We can swap the order in the table without confusing. 

Representation

| Coor | X       | Y       | Z       |
| ---- | ------- | ------- | ------- |
|      | $x_{1}$ | $y_{1}$ | $z_{1}$ |
|      |         |         |         |
and point

This is the bad relationship. General purpose table. It's bad because one column must comes from only one domain. This table comes from many domain in one column.
$S^{'}$

| S#  | COLNAME | VALUE |
| --- | ------- | ----- |
| S1  | SNAME   | SMITH |
| S1  | STATUS  | 20    |
| S1  | CITY    | Paris |
Write SQL code list SNAME of London Suppliers whose status = 20. From $S^{'}$

A table which correctly represents a relation must have the following properties.
- Values in a column must be from the same topic (domain).
- Column values must be atomic.
- No 2 rows are the same (A primary key is required).
- Rows have no order.


| ID# | NAME | GENDER    |
| --- | ---- | --------- |
|     |      | 1-MaleB   |
|     |      | 2-FemaleB |
|     |      | 3-MaleM   |
|     |      | 4-FemaleM |
How many female students in KMITL
```sql
SELECT COUNT(*) FROM STUDENT WHERE GENDER = 2 OR GENDER = 4
```

EMP

| E#  | .... | ..... | TELNO |
| --- | ---- | ----- | ----- |
|     |      |       |       |
This kind of structure is not allowed. It's not atomic.
> Atomic means single value.

TELNO a collection is a repeating group. which is not allow because we can't get the repeating group from the cartesian product of domain. 

We can make it to this

| E#  | .... |
| --- | ---- |
|     |      |

Separate to two table.

| E#  | TELNO |
| --- | ----- |
|     |       |
In this example
customer(A)

| C#  | ..... | Address |
| --- | ----- | ------- |
|     |       |         |
customer(B)

| C#  | .... | HOUSE# | STREET | DISTRICT | PROVICE | PROTENDS |
| --- | ---- | ------ | ------ | -------- | ------- | -------- |
|     |      |        |        |          |         |          |
<u>Atomic value</u>
No applications access a subset of the data item.

In mathematics {s1, s2, s3} == {s2, s1, s3} in SQL table a row can be anywhere. Once table have 4 properties so it represent a correct relation table. In SQL input must be a relation then output will be relation.

**"What is an SQL table in relational database theory"**. 
It a **variable** whose data type must be relation (Relation Variable , REL Var).

Schema
| S# | SNAME | STATUS | CITY |

r1(s) ------v
r2(s) -->  relations
r3(3) ------^

Analogy SQL table:
x integer 0 (x is a variable type integer)
x: = 5
x: = x+1
x: = 30

In relational database have 3 simple rule that enforce the relation.
- **Data Structure** - relations only
- **Integrity rules** - Entity Integrity (primary key must not be null), Referential Integrity (foreign key values must match primary key values)
- **Data Manipulation Language** - Relational complete languages (relation algebra (calculus equivalents) )

## Primary key 
Key is an identifier and might not be sorted (unique, should not be changed and may not have meaning).
Index is access mechanism not even part of table (outside access mechanism and can be duplicated value) and value should be sorted.

S# is a key. 

| S#  | SNAME | STATUS | CITY  |
| --- | ----- | ------ | ----- |
| S1  | Smith | 30     | Paris |
