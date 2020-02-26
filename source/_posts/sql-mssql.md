---
title: sql-mssql
date: 2019-12-04 21:40:29
categories:
   - db
   - mssql
tags:
   - mssql
---
# mssql tips
## UNIQUEIDENTIFIER사용 및 insert시 값 가져오기
```
CREATE TABLE TY (  
   Y_id UNIQUEIDENTIFIER DEFAULT (newsequentialid()) PRIMARY KEY,
   Y_name varchar(20) NULL,
);  
declare @guid table (Y_id UNIQUEIDENTIFIER);

INSERT into TY(Y_name)
output INSERTED.Y_id into @guid
VALUES ('Rosalie');

SELECT (select top(1) Y_id from @guid) as blabla

SELECT * FROM TY;  

drop table TY;
```
## newdate
```
select GETDATE() as newdate
```