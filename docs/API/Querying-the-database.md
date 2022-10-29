# Safer SQL database querying
**Author**: Patrick Igiraneza   
**Date**: October 27, 2022

SQL database are known to be vulnerable to SQL injection attacks if the query string form a user is not properly escaped.

Please read: https://stackoverflow.com/questions/8263371/how-can-prepared-statements-protect-from-sql-injection-attacks

For our project we will be using mysql2 for the following reasons:
1. Speed
2. Prepared statement
1. Promises(async and await)   
promises allow you to run task/queries concurently. If a query takes long it should prevent other smaller queries from running.  


# Methods
## 1. Never trust user input data
You should never pass data from the suer/frontend directly to the database. It is good pactive to escape all HTML, JS tags to avoid XSS(Cross Site Scripting)

## 2. Always use prepared statements
Prepared statements allow us to send the query first to the database and send the data after. This ensures that the database knows what kind of data to expect and that no addictional queries/commands are to be executed. This is the base of SQL Inkection, an attacker is able to run his commands on top of a program's.