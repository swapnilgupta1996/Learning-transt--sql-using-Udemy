

--VIEW >>> DENY ACCESS TO THE TABLES 

CREATE VIEW MYCUSTOMUSVIEW

AS 
SELECT * FROM AdventureWorks2012.Sales.SalesTerritory
WHERE CountryRegionCode LIKE 'US'

SELECT * FROM MYCUSTOMUSVIEW


SELECT * FROM AdventureWorks2012.Sales.vPersonDemographics

SELECT * FROM AdventureWorks2012.Sales.SalesPerson
---Two tables to join 

CREATE VIEW NASalesQuota
AS 
SELECT [Name],[Group][SalesQuota],[bonus]
From Adventureworks2012.sales.salesterritory A inner join Adventureworks2012.sales.salesperson b
ON A.TerritoryID = B.TerritoryID
WHERE [Group] LIKE 'NORTH AMERICA'

SELECT * FROM NASalesQuota
-------------------------------
CREATE VIEW NASalesQuota1
AS 
SELECT [Name],[Group],[SalesQuota],[bonus]
From Adventureworks2012.sales.salesterritory A inner join Adventureworks2012.sales.salesperson b
ON A.TerritoryID = B.TerritoryID
WHERE [Group] LIKE 'NORTH AMERICA'

SELECT * FROM NASalesQuota1

CREATE VIEW NASalesQuota2
AS 
SELECT [Name],[Group],[SalesQuota],[bonus]
From Adventureworks2012.sales.salesterritory A inner join Adventureworks2012.sales.salesperson b
ON A.TerritoryID = B.TerritoryID
WHERE [Group] LIKE 'NORTH AMERICA'


SELECT * FROM NASalesQuota2

-------------------------------------

--- Triggers 

SELECT * FROM AdventureWorks2012.HumanResources.Shift


SELECT * FROM HumanResources.Shift
create trigger demotrigger
ON HumanResources.shift
AFTER INSERT 
AS
BEGIN
PRINT 'INSERT IS NOT ALLOWED. YOU NEED APPROVAL'
ROLLBACK TRANSACTION
END 
GO

-- testing the trigger 
insert into HumanResources.Shift
([Name],[StartTime],[EndTime],[ModifiedDate])
VALUES
('Rakesh','08:00:00.0000000','06:00:00.0000000', GETDATE ())

-- getting the date to check  the date syntax
SELECT GETDATE ()


---Database level trigger 

Create trigger demodbtrigger 
on DATABASE 
AFTER CREATE_TABLE
AS
BEGIN
PRINT 'CREATION OF NEW TABLES NOT ALLOWED'
END
GO

---tRYING TO CREATE A TABLE 

CREATE TABLE MYDEMOTABLE(col1 varchar(10))
