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

196.

```mysql
DELETE p1
FROM
	Person p1,
	Person p2
WHERE
	p1.Email = p2.Email
AND p1.Id > p2.Id
```

620.

```mysql
SELECT
	*
FROM
	cinema
WHERE
	id % 2 = 1
AND description <> 'boring'
ORDER BY
	rating DESC;
```

197.

```mysql
SELECT
	t2.Id Id
FROM
	Weather t1,
	Weather t2
WHERE
	DATEDIFF(
		t2.RecordDate,
		t1.RecordDate
	) = 1
AND t2.Temperature > t1.Temperature;
```

595.

```mysql
SELECT
	NAME,
	population,
	area
FROM
	World
WHERE
	area > 3000000
OR population > 25000000;
```

596.

```mysql
SELECT
	class
FROM
	courses
GROUP BY
	class
HAVING
	count(DISTINCT student) > 4;
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
