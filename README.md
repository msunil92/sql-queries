# sql-queries

```
USE care;

drop table dbo.Persons ;
drop table dbo.Persons_target ;


CREATE TABLE dbo.Persons (
    PersonID int NOT NULL,
    LastName VARCHAR(255),
    FirstName VARCHAR(255),
    Address VARCHAR(255),
    City int
);

CREATE TABLE dbo.Persons_target (
    PersonID int NOT NULL,
    LastName VARCHAR(255),
    FirstName VARCHAR(255),
    City int,
	Address VARCHAR(255),
);

insert into dbo.Persons values(1, 'Sunil', 'M', 'add', 1);
insert into dbo.Persons values(2, 'Ram', 'Kumar', 'ANDra', 2);
--update Persons_target set city = 100 WHERE PersonID = 1;

SELECT * FROM persons;
SELECT * FROM Persons_target;

EXEC [dbo].[dba_GenerateMergeStatement] @SOURCE_TABLE='care.dbo.Persons', @TARGET_TABLE='care.dbo.Persons_target', @PRIMARY_KEYS='PersonID', @SPECIAL_KEYS = 'City'

```