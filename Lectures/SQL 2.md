(10/1/)
```sql
select avg(Deathage) / count(*)
from president
where Deathage is not null
```
To prevent the data truncated or another solution to avoid
```sql
select 1.0*sum(Deathage) / count(*)
from president
where Deathage is not null
```

List Pres_name of presidents who sent at least 10% of their lives as presidents.


where (yrs_serv /death_age\*100)>10

```sql
SELECT party, count(*)
FROM president
WHERE BIRTH_YRS > 1850 AND COUNT(*) > 8 --WRONG
GROUP BY PARTY
```

```sql
SELECT party, count(*)
FROM president
WHERE BIRTH_YRS > 1850
GROUP BY PARTY
HAVING COUNT(*)>8 -- USE THIS INSTEAD
```


| S#  | P#  | OTY |
| --- | --- | --- |
| S1  | P1  | 20  |
| S1  | P2  | 15  |
| S1  | P3  | 18  |

List S# of suppliers who supply both P1 and P2
```sql
SELECT S#, P#
FROM SP
WHERE P# = P1 or P# = P2
GROUP BY S#
HAVING count(*) = 2
```
List Presname of president who have both swimming and walking as hobbies.
```sql
SELECT PRESNAME, HOBBY
FROM PRESIDENT
WHERE HOBBY = 'swimming' or HOBBY = 'walking'
GROUP BY PRESNAME
HAVING count(*) = 2
```

Syntax Error
```sql
SELECT *     -- PARTY, PRESNAME, BIRTHYR, ...
FROM PRESIDENT
GROUP BY PARTY
```

List PRES_NAME of married presidents who had no children at all
```sql
SELECT PRES_NAME
FROM PRES_MARRIAGE
GROUP BY PRESNAME
HAVING SUM(NUMCHILDREN) = 0
```

Join Table
- Want column from more than one table.
```sql
-- IT MIGHT COST A LOT OF CARTESIAN PRODUCT
SELECT president.PRES_NAME, BIRTH_YR, MAR_YR, SPOUSE_NAME
FROM president, pres_marriage

SELECT president.pres_name, birth_yr, mar_year, spouse_name
from president, pres_marriage
where president.presname=pres_marriage.pres_name

-- matched row comes out
SELECT president.pres_name, birth_yr, mar_year, spouse_name
from president inner join pres_marriage
on president.pres_name=pres_marriage.pres_name

-- matched and unmatch row will comes out
SELECT president.pres_name, birth_yr, mar_year, spouse_name
from president left outer join pres_marriage
on president.pres_name=pres_marriage.pres_name

-- common column name will matched automaticly and appear only once
SELECT president.pres_name, birth_yr, mar_year, spouse_name
from president natural join pres_marriage
```