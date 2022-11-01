# Mysql foreign keys
**Author**: Patrick Igiraneza   
**Date**: October 31 2022

## What are they?
 - allow to query 2 tables at the same time
 - can query one table and join with info from another table
Link: https://www.w3schools.com/sql/sql_foreignkey.asp

 ```sql
 ALTER TABLE current_table
ADD FOREIGN KEY (field_in_current_table) REFERENCES other_table_name(field_to_be_referenced);
 ```

## Querying
```sql
SELECT table.field,other_table.field FROM table JOIN other_table ON table.field = other_table.field
```
## Why we need relationships
Programmatically, we don't actually need to code the relationship in the database. The relationship can just be a mental abstraction/ concept.

But let us say you have students marks in a table with a field for student's ID. One day, the students gets delete from the account. You would have to manually delete all student's related items in all table to avoid a row with a null reference.

To deal with this, we use relationships and what those relationships mean. We can have a relationship that specify that if A certain foreign key is delete all the data linked to it should also be delete(CASCADE)

## Referential actions
https://en.wikipedia.org/wiki/Foreign_key#Referential_actions
1. **CASCADE**  
-> Delete the all the child(referencing) rows
1. **RESTRICT**  
-> Prevents deleting the foreign key if it is referenced any where.
1. **NO ACTION**
1. **SET NULL**
1. **SET DEFAULT**

# Data Types
https://dev.mysql.com/doc/refman/8.0/en/char.html
- the most appropriate/memory efficient type would be VARCHAR()
- VARCHAR(length) - you can specify the maximum length up to 65,000 char
- CHAR() - has to always have that many number of characters assigned.
- if they are 4 and no data is inserted it will automatically add 4 spaces.

## Lengths
Reference: https://condor.depaul.edu/gandrus/240IT/accesspages/fields-datatypes.htm

| Field | Type|
| ----- | ---- |
| names/emails | VARCHAR(255) |
| id | INT |
| telephone | VARCHAR(15)|
| Website | TEXT|

