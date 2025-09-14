# Dynamic-Company-Database-creation-Data-importation-Data-analysis-Database-Backup-to-company-server.-
This SQL Server work on Dynamic company Database creation aims to keep record of structured data of the company business activities, staff record, analyze data that generate report to aid clear business decision making and backing up company Database to a server for safety. Key features are: Database creation, importation of structured data & extraction of report to support business decision making.  

Case Study by Morrison (Analyst).

> ## Project Overview
This case study - Dynamic Company Database creation, data importation, analysis & backup of Database. 

> ## Data Content
### Database: 1 in Total.
 ### Tables: were 8 in Total.
Tables Name: Employee, Mall ghana, Mall ikeja, Mall portharcourt, payment, salary.
View Tables Name: Mall transaction, Employee salary.

> ## Tool Used
SQL Server-SQL Studio (SQL quires & Sub quires).

> ## SQL Database Creation
## Steps
[CREATE DATABASE DSA_MG]
## Data importation Actions
Structured data was imported and saved in the database from on premise and cloud for analysis.
<img width="560" height="298" alt="image" src="https://github.com/user-attachments/assets/d088e049-4d18-44b3-8cd6-348e9919bfe2" />
> ## Key Business Questions Answered

1.	Create a Database in SQL Studio (SSMS)
Add query: CREATE DATABASE DSA_MG

2.	Update employee table imported?
   
Add query:

UPDATE EMPLOYEE

SET LASTNAME = 'ABUBAKAR'

WHERE STAFFID = 'AB234'

3.	Total no of staff from each state?
   
Add query:

SELECT [SELECT STATE OF ORIGIN], COUNT(DISTINCT STAFFID) AS TOTALEMPLOYEE

FROM EMPLOYEE

GROUP BY [STATE OF ORIGIN]

ORDER BY TOTALEMPLOYEE DESC

4.	Total no of staff in each state?
   
Add query:

SELECT [DEPARTMENT], COUNT(DISTINCT STAFFID) AS TOTALEMPLOYEE

FROM SALARY

GROUP BY [DEPARTMENT]

ORDER BY TOTALEMPLOYEE DESC

5.	Update of staff salary by 5%?
   
Add query:

CREATE VIEW NEW_SALARY AS

UPDATE salary

SET salary  = salary + (salary * 0.05)

6.	Creation of view Mall transaction?
   
Add query:

CREATE VIEW vw_DSA_Mall_Transaction

AS

select 

    'DSA MALL GHANA' AS BRANCH, customerid as [CUSTOMER ID],
	
	firstname as [FIRST NAME], lastname as [LAST NAME],
 
	customer_gender as GENDER, TRANSACTIONDATE AS [DATE],
 
	[ADDRESS], transaction_amount AS [TRANSACTION AMOUNT]
 
FROM [dbo].[Mall_Ghana]

UNION

select 

    'DSA MALL IKEJA' AS BRANCH, customerid as [CUSTOMER ID],
	
	firstname as [FIRST NAME], lastname as [LAST NAME],
 
	customer_gender as GENDER, TRANSACTIONDATE AS [DATE],
 
	[ADDRESS], transaction_amount AS [TRANSACTION AMOUNT]
 
FROM [dbo].[Mall_IKEJA]

UNION

select 

    'DSA MALL PORT HARCOURT' AS BRANCH, customerid as [CUSTOMER ID],
	
	firstname as [FIRST NAME], lastname as [LAST NAME],
 
	customer_gender as GENDER, TRANSACTIONDATE AS [DATE],
 
	[ADDRESS], transaction_amount AS [TRANSACTION AMOUNT]

FROM [dbo].[Mall_PORT HARCOURT]

7.	Total sale per branch
	
Add query:

select branch, sum([transaction amount]) as [Total sales]

from  [dbo].[vw_DSA_Mall_Transaction]

group by BRANCH

order by [Total sales] desc


8.	Extraction of result to excel and Back up of Database.
9.	<img width="657" height="348" alt="image" src="https://github.com/user-attachments/assets/d063bb6b-ed4b-4ba8-b034-879f2a8ad125" />

