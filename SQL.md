_175._
`SELECT
	p.FirstName,
	p.LastName,
	a.City,
	a.State
FROM
	Person p
LEFT JOIN Address a ON p.PersonId = a.PersonId;`

_176._
`SELECT
	(
		SELECT DISTINCT
			Salary
		FROM
			Employee
		ORDER BY
			Salary DESC
		LIMIT 1,
		1
	) AS SecondHighestSalary;`

_181._
`SELECT
	name AS employee
FROM
	(
		SELECT
			e1.Name ,
			e1.Salary,
			e2.Name AS mname,
			e2.Salary AS msalary
		FROM
			employee e1
		LEFT JOIN employee e2 ON e1.ManagerId = e2.Id
	) e
WHERE
	salary > msalary;`