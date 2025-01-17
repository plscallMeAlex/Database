	(24/12/24)
Recap key is an identifier and not an index (mechanism).
Index can be duplicated but keys cannot.
## Super keys
Is an attribute or set of attributes which unique identify a tuple. Example S number on the table is super key. Schema is also super key.
Schema1:
| S# | SNAME | STATUS | CITY |

## Candidate key (Unique and minimum size)
Is a super key which doesn't have other super key as its proper subset.
from Schema1:
S has 2 Candidate keys
S#, SNAME                Each candidate key have 1 attribute.
## Primary keys (Entity Integrity)
A selected candidate key. It is the main unique identifier of a tuple on a relation. Must be unique and not null also must not change.

null values
EMP
| E# | ENAME | ..... | SALARY | SHIFT |

using ? don't know (Internal) to display null if that field not have anything.
### Null Values
- Attribute applicable but values unknown.
- Attribute not applicable.
- "Now" (The running now) in temporal database.
- Private (Do not allow people to see)

Love

| Person1 | Person2 | FromDate   | ToDate       |
| ------- | ------- | ---------- | ------------ |
| John    | Mary    | Dec 1,2024 | Dec 31, 9999 |
It the biggest number (infinity) make John love Mary still true.
Instead of using the infinity using null make it also true.

## Foreign keys (Referential Integrity)
A foreign key is a non-key attribute of a relation which is the primary key of other relations. 
Example
EMP
                   FK

| E#  |     |     | D#  |
| --- | --- | --- | --- |
| E1  |     |     | D1  |
| E2  |     |     | D1  |
| E3  |     |     | ?   |
| E4  |     |     | ?   |
BUT can't have the D12 (Because it don't have)

DEP 

| D#  |     |     |     |
| --- | --- | --- | --- |
| D1  |     |     |     |
| D2  |     |     |     |
| D3  |     |     |     |
| D4  |     |     |     |
**Create Example:**
Create table DEP (D# char(3))
Primary key is D#; D# is unique and not null.

Create table EMP (E# ... D#.... )
Primary key is E#
Foreign key is D# references D# of DEP

Line between table is called relationship or anther term called primary key foreign key relationship.

Default is null,
Update\[Restricted, Cascades, Default]
Delete\[Restricted, Cascades, Default]

## Data Manipulation Languages
Application/users -> What? (Relational calculus -> SEQUEL -> SQL) -> DBMS -> How? (Relational Algebra) -> DB

A relational complete language is a language which is as powerful as the relational algebra or the relational calculus.

**Example:**
English: List SNAME of London suppliers who supply P2
```sql
SELECT SNAME FROM S,SP WHERE S.S# == SP.S# AND CITY == 'London' AND P# == 'P2'
```

S

| S#  | SNAME | CITY | STATUS |
| --- | ----- | ---- | ------ |
|     |       |      |        |
SP

| S#  | P#  | QTY |
| --- | --- | --- |
|     |     |     |
![](/images/Pasted%20image%2020241224111146.png)

Database System Architecture (The 3 schema architecture, The 3-level architecture)

Host Language(Main program language for and development) + DSL(Data Sub Language or Database Language) == Application program