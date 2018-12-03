175.

```mysql
SELECT
	p.FirstName,
	p.LastName,
	a.City,
	a.State
FROM
	Person p
LEFT JOIN Address a ON p.PersonId = a.PersonId;
```

176.

```mysql
SELECT
	(
		SELECT DISTINCT
			Salary
		FROM
			Employee
		ORDER BY
			Salary DESC
		LIMIT 1,
		1
	) SecondHighestSalary;
```

181.

```mysql
SELECT
	e1. NAME Employee
FROM
	Employee e1
LEFT JOIN Employee e2 ON e1.ManagerId = e2.Id
WHERE
	e1.Salary > e2.salary;
```

182.

```mysql
SELECT
	Email
FROM
	Person
GROUP BY
	Email
HAVING
	count(Email) > 1;
```

183.

```mysql
SELECT
	c. NAME Customers
FROM
	Orders o
RIGHT JOIN Customers c ON o.CustomerId = c.Id
WHERE
	o.CustomerId IS NULL;
	
SELECT
	c.Name Customers
FROM
	Customers c
WHERE
	c.Id NOT IN (SELECT CustomerId FROM Orders);
```

627.
```mysql
UPDATE salary
SET sex = CASE sex
WHEN 'm' THEN
	'f'
ELSE
	'm'
END;
```
