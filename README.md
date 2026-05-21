# SQL Security Filters Investigation
## Project Description
In this activity, I used SQL filtering techniques to investigate potential security incidents related to login attempts and employee devices. I queried organizational data from the employees and log_in_attempts tables using operators sush as AND, OR, NOT, and LIKE. The goal was to identify suspicious login activity and retrieve employee records retlated to specific security update requirements.

## Retrieve after hours failed login attempts
### SQL Query
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;
```
### Explanation
This query retrieves all failed login attempts that ocurred after business hours. The AND operator combines both conditions: login attempts after 18:00 and unsuccesful login attempts. This helps identify potentially suspicious activity occurring outside normal working hours.

## Retrieve login attempts on specific dates
### SQL Query
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```
### Explanation
This query retrieves all login attempts that ocurred on May 8 and May 9, 2022. The OR operator is used to include records from either date in the results. This helps investigate suspicious events that may have ocurred across multiple days.

## Retrieve login attempts outside of Mexico
### SQL Query
```sql
SELECT *
FROM log_in_attempts
WHERE country NOT LIKE 'MEX%' AND country NOT LIKE 'MEXICO%';
```
### Explanation
This query retrieves login attempts that did not originate from Mexico. The NOT operator excludes records matching values that begin with "MEX" or "MEXICO". The LIKE keyword with the % wildcard helps identify multiple variations of the country name.

## Retrieve employees in Marketing
### SQL Query
```sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```
### Explanation
This query retrieves employees who work in the Marketing department and are located in offices within the East building. The AND operator combines both filtering conditions, while the LIKE keyword with the % wildcard identifies offices that begin with "East".

## Retrieve employees in Finance or Sales
### SQL Query
```sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```
### Explanation
This query retrieves employees who belong to either the Finance or Sales departments. The OR operator allows records from both departments to be included in the results.

## Retrieve all employees not in IT
### SQL Query
```sql
SELECT *
FROM employees
WHERE department NOT LIKE 'Information Technology';
```
### Explanation
This query retrieves all employees who are not part of the Information Technology department. The NOT operator excludes records that match the IT department value.

## Sumary
In this project, I used SQL filtering techniques to analyze login activity and employee records related to cybersecurity investigations. I applied filtering operators such as AND, OR, and NOT, along with the LIKE keyword, to identify suspicious login attempts and retrieve relevant employee information. This activity strengthened my understanding of SQL query filtering and its application in security operations and incident investigations.
