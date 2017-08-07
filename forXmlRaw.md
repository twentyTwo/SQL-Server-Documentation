1.
```sql
SELECT e.EmployeeID, c.FirstName, c.MiddleName, c.LastName
FROM Employee e 
INNER JOIN Person.Contact c ON c.ContactID = e.ContactID
WHERE c.FirstName = 'Noor'
```

> Output

EmployeeID|FirstName|MiddleName|LastName
----------|---------|----------|--------
4|Noor|NULL|Alam
5|Noor|A|Shuvo

2.
```sql
SELECT e.EmployeeID, c.FirstName, c.MiddleName, c.LastName
FROM Employee e 
INNER JOIN Person.Contact c ON c.ContactID = e.ContactID
WHERE c.FirstName = 'Noor'
FOR XML RAW;
```

> Output
```
<row EmployeeID="4" FirstName="Noor" LastName="Alam" />
<row EmployeeID="5" FirstName="Noor" MiddleName="A" LastName="Shuvo" />
```
3.
```sql
SELECT e.EmployeeID, c.FirstName, c.MiddleName, c.LastName
FROM Employee e 
INNER JOIN Person.Contact c ON c.ContactID = e.ContactID
WHERE c.FirstName = 'Noor'
FOR XML RAW('Employee');
```
> Output
```
<Employee EmployeeID="4" FirstName="Noor" LastName="Alam" />
<Employee EmployeeID="5" FirstName="Noor" MiddleName="A" LastName="Shuvo" />
```
4.
```sql
SELECT e.EmployeeID, c.FirstName, c.MiddleName, c.LastName
FROM Employee e 
INNER JOIN Person.Contact c ON c.ContactID = e.ContactID
WHERE c.FirstName = 'Noor'
FOR XML RAW('Employee'), ROOT('Employees');
```
> Output
```
<Employees>
  <Employee EmployeeID="4" FirstName="Noor" LastName="Alam" />
  <Employee EmployeeID="5" FirstName="Noor" MiddleName="A" LastName="Shuvo" />
</Employees>
```

