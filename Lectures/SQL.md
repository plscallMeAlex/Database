# Structured Query Language
SQL operating modes
- Interactive mode
- Embedded mode
```sql
SELECT <column list> | * | <build-in lns>
FROM <table names> | <view names>
[WHERE <row conditions>]
[GROUP BY <column list>]
[HAVING <group condition>]
[ORDER BY <column list>]
```
**Student table.**

| ID# | SCHOOL | DEPT |
| --- | ------ | ---- |
|     |        |      |
List DEPT of the engineering school which have more than 500 students.
```sql
SELECT DEPT
FROM STUDENT
WHERE SCHOOL == 'Engineering'
GROUP BY DEPT -- SORT BY DEPT
HAVING COUNT(*) > 500 -- 
ORDER BY COUNT(*) DESC -- Order decending
```
**President**

| .... | STATE_BORN | PANTY |
| ---- | ---------- | ----- |
|      |            |       |
List states which have more than 2 Republican presidents born.
```sql
SELECT STATE_BORN, COUNT(*)
FROM President
WHERE PARTY = 'Republican'
GROUP BY STATE_BORN
HAVING COUNT(*) > 1
```
Not equal sign
^=
<>
## SQL Logical Execution Sequence
1. From
2. Where
3. Group by
4. Built-in function (applies to each group)
5. Having
## Built-In function (Aggregates)
- AVG (work on column, numeric)
- SUM (work on column, numeric)
- MIN (work on column, alphanumeric)
- MAX (work on column, alphanumeric)
- COUNT (work on row)

Syntax Error!
```sql
select President, MIN('Death_age')
from president
```
**Set-of-value O/P cannot be together with single valye Output**

Syntax
Column names cannot be together with built-in function in a Select list (There is an exception.)

Show only the parties which have more than 15 presidents,
count(\*) >15

```sql
select party, sum(yrs_srv), count(*), avg(yrs_serv)
from president
where party in ('Democratic', 'Republican')
group by party
having count(*)
``` 