(Date 03/12/2024)
**Model**
comprises 3 parts these use for general purpose doesn't fit all database structure.
- **Data Structure**: Logical data structure as seen by applications and programmers (Table(n-ary relations), Tree, Graph, Object).
- **Data Integrity (Correctness)**: Rules that enforce correctness on the logical database structures example relational database model have 2 rules primary key value, foreign key value. Like tree each node of tree must have at most one parent.
- **Data Manipulation**: languages use on the logical data structure some database have more than one languages such as relational algebra or relational calculus.

>group of 2 person on NoSQL product compare to SQL. After exam midterm.

## "Relation in the database area is data rows without the heading. (Data rows excluding the table structure)"
A relation is a subset of the cartesian product of domains.
- **Domain mean a finite set of permitted values**
- **The cartesian product mean the concatenation (combination) of all possible domain.**

**Example Domain:**
S = {S1, S2, S3}
SNAME = {Jon, John, Jane Jul, ...}
STATUS = {10, 20, 30, 40, ...}
CITY = {London, Paris, DC, ...}

Rows  (tuple)
S1 -- Jon -- 10 -- London
S1 -- Jon -- 20 -- London
S1 -- Jon -- 30 -- London
..... -- ....... -- ..... -- ................

It will keep like this (S1, Jon, 10, London) ...

Some rows can true XOR false according to the world.

From the huge tuples of cartesian product we pick the True row that according to the world if keep false the database could lead to infinite relationship and the search engine will become complicated. 
**Example** telephone operator when call the number it keep record the number call that number for how long. If keep false i will keep like which number is didn't call.

$(S1, Jon, 10, London)$
From this structure you will see that it a data rows without the heading.

| S#  | SNAME   | STATUS | CITY |
| --- | ------- | ------ | ---- |
| r1  | base on | schema | S    |
| r2  | base on | schema | S    |
| r3  | base on | schema | S    |
Each one is attribute. 
The whole structure call relational schema

Heading is for mapping the value to the domain and value staying in one domain.

|    X    | Y       | Z       | V       |
| :-----: | ------- | ------- | ------- |
| $x_{2}$ | $y_{2}$ | $z_{2}$ | $v_{2}$ |
| $x_{1}$ | $y_{1}$ | $z_{1}$ | $v_{1}$ |
| $x_{3}$ | $y_{3}$ | $z_{3}$ | $v_{3}$ |
**There are two way to represent the relation are table and coordinate.**
Table representation is popular when use the database table in practice make sure table is correctly relation.

**To be a relation the table must have a curtain property**

Attribute-value pair (programmer suggest this) it call Crosstab using in excel but not a relation.

| S#  | COLNAME | VALUE  |
| --- | ------- | ------ |
| S1  | SNAME   | Smith  |
| S1  | STATUS  | 20     |
| S1  | CITY    | London |
Twist from column to row. **This table is not a relation**. Each column value must come from only one domain. This table is come from many domain. SQL work only relation this table is not good for SQL.

**Write SQL code. (Midterm)**
List SNAME of London suppliers whose status = 20.
```SQL
SELECT SNAME FROM S WHERE CITY == "London" and STATUS == 20
```

This SP Table is not a relation.

| S#  | P1  | P2  | P3  | P4  | P5  | P6  |
| --- | --- | --- | --- | --- | --- | --- |
| S1  | 300 | 200 | 400 | 200 | 100 | 100 |
Suppose some day we add the P7 to it. It will make the table corrupt.
Use this SP table instead

| S#  | P#  | QTY |
| --- | --- | --- |
| S1  | P1  | 300 |
| S1  | P2  | 200 |

When doing project make sure we make a correct relation.

Just to know Data Warehouse for data analytic using coordinate representation.
Like X, Y, Z dimension rubric represent or you can call cube multidimensional database.

List two table that is not a relations (Midterm)

## Properties of Relation table.
A table which correctly represent relation not all table are correctly must have the following properties:
- Values of each column belong to only one domain.
- Column values must be atomic.
- No 2 rows are the same.
- Rows have no order.
If the table have these 4 properties the table is correctly representation.

## Conclusion
SQL can do if the input is a relation and output is relation. We can't write the SQL code to produce not a relation result cannot produce a crosstab format.