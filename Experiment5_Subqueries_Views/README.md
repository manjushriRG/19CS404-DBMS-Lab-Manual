# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![{3FB28952-DFCA-4D35-B950-F17F5F2D1786}](https://github.com/user-attachments/assets/eb13d287-6854-4616-93b9-5bbef1886b72)


```sql
select * from CUSTOMERS
where ADDRESS='Delhi' and AGE< '30'
ORDER BY ID 
```

**Output:**

![{3B457559-4B27-4DE5-B62C-9EADCBA41A3B}](https://github.com/user-attachments/assets/f832b7f9-8f5a-4b84-b799-f31be3ac1f61)


**Question 2**
---
![{B6FD0DFC-FC7E-44BC-8835-7A2781395F41}](https://github.com/user-attachments/assets/e54b5dae-af45-4806-bf79-3030148e8e74)


```sql
SELECT * FROM CUSTOMERS
WHERE ADDRESS='Delhi'
```

**Output:**

![{F3105120-DAF8-4C23-80F5-3B9A89FA0C30}](https://github.com/user-attachments/assets/34716438-632d-4e89-9ab1-65930d35055d)


**Question 3**
---
![{101E1790-20A0-45F8-A244-9DC43BD50D13}](https://github.com/user-attachments/assets/43b34673-55d1-4894-864b-12206d268bb2)


```sql
select * from customer
WHERE city <> (SELECT city FROM customer
                order by id DESC 
                LIMIT 1)
```

**Output:**

![{02B46630-D9B2-4812-9199-D3400EA40846}](https://github.com/user-attachments/assets/871db266-2280-44fc-b20f-f70d14b388b6)


**Question 4**
---
![{615AB660-7F1D-4097-BA30-CB8C2C94E801}](https://github.com/user-attachments/assets/62771ff5-9848-48f0-9d07-51a3a2865fa1)


```sql
select * from CUSTOMERS
WHERE SALARY<2500
```

**Output:**



**Question 5**
---
![{D627159B-D29E-4262-8A2F-E697780BA8B4}](https://github.com/user-attachments/assets/a2072f8b-d2c7-4d00-9e7f-6edd8da1c20b)


```sql
SELECT * FROM CUSTOMERS
WHERE SALARY>1500
```

**Output:**

![{D7276BC2-9B98-4BFF-9788-7B22DB50DE06}](https://github.com/user-attachments/assets/11746e03-6cf9-40aa-bfc7-8b69234a17d6)


**Question 6**
---
![{DD23DB7E-94FB-45F5-8EBF-341E17966492}](https://github.com/user-attachments/assets/f4bd88d5-10dd-488b-aac5-113bbbac04fd)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id FROM orders o
JOIN salesman s 
ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam'

```

**Output:**
![{A21A64DB-2C35-4CDE-8FCF-EE86019291F3}](https://github.com/user-attachments/assets/de134a2f-241d-4949-9b4e-8780ca2b8c3c)


**Question 7**
---
![{8C93B47B-AF0E-4422-B332-5A8769B040BF}](https://github.com/user-attachments/assets/b8a56d8a-42a1-45a2-8af7-3f2eb748cc78)


```sql
select o.ord_no,o.purch_amt,o.ord_date,o.salesman_id
from orders o
join salesman s on o.salesman_id=s.salesman_id
where s.commission=(select max(commission) from salesman)
```

**Output:**

![{622D71C8-758C-4D60-94B5-9A6D4AE0DCFC}](https://github.com/user-attachments/assets/2f9b4725-558c-42aa-873d-403f4950f176)


**Question 8**
---
![{D5118946-9B1A-4EBC-8B6A-7044F528C96C}](https://github.com/user-attachments/assets/e6d12c0b-bb7e-4655-9dff-9a59bb967656)


```sql
select grade, COUNT(*) from customer
where grade> (select avg(grade)from customer where city='New York')
GROUP BY grade
```

**Output:**

![{31AECD6C-C2F1-4439-8C54-4B733851C3B3}](https://github.com/user-attachments/assets/aa4c9bfb-1b0c-43ba-9b76-0266704b7231)


**Question 9**
---
![{7CFC522D-D0EE-46BA-8359-11516CC89E48}](https://github.com/user-attachments/assets/86b4ff25-cce3-44ac-94f8-dd8b77345d73)


```sql
SELECT * FROM CUSTOMERS
WHERE SALARY>4500
```

**Output:**
![{AE2535BC-1ADA-4761-AC9B-5D3251761BA1}](https://github.com/user-attachments/assets/1e7a5ea3-ff8f-4fbf-9bc1-136f35a59082)


**Question 10**
---
![{114A7F59-678F-434F-8CAF-C48CFF521153}](https://github.com/user-attachments/assets/95b1a527-0228-4f78-b3f7-7f4789a1fcfe)


```sql
select * from CUSTOMERS
WHERE AGE<30
```

**Output:**
![{5C9877B1-6A32-42DD-84C6-8BC6CB5FDCC1}](https://github.com/user-attachments/assets/d601ca16-47a8-4096-8f1b-86a95c0b5715)




## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
