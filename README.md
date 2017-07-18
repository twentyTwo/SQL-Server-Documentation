# SQL-Server-Documentation

## Documentation of the below topics
- STUFF
  > Replace part of a string with a second string
  * Example :
  ```SELECT STUFF('TechOnTheNet.com', 1, 12, 'CheckYourMath')```
  > Output: 'CheckYourMath.com'
- LEAD / LAG
- XML PATH
- COALESCE
- RANK Functions
- CTE
- OVER Clause
- FOR XML PATH
- Analyzing a Query 
- Pagination
- Tally
- GROUP_CONCAT
- PARSENAME
> Splits a string by a [.] (DOT)
  * Example 1
   ```sql
   Declare @ObjectName nVarChar(1000) 
   Set @ObjectName = 'HeadOfficeSQL1.Northwind.dbo.Authors' 

   SELECT PARSENAME(@ObjectName, 4) as Server,PARSENAME(@ObjectName, 3) as DB,PARSENAME(@ObjectName, 2) 
   as Owner,PARSENAME(@ObjectName, 1)   as Object
   ```
   > Output: 
   
   |    Server    |    DB   |Owner| Object|
   |--------------|---------|-----|-------|
   |HeadOfficeSQL1|Northwind| dbo |Authors|
   
   
   * Example 2
   ```sql
   DECLARE @TestString AS VARCHAR (200) = '_999_123456_8888888-123564578'; 
   SELECT PARSENAME(REPLACE(@TestString, '_', '.'), 2)
   ```
   > Output: 12345
   
   - OUTER APPLY
