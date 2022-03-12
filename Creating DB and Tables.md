# Creating DB and Tables

Create Stora database
```sql
CREATE DATABASE STORE
ON (NAME = 'GAMESTORE.DAT', -- Internal Name
	FILENAME = '/mssql/GAME_STORE.MDF', -- Database file path (Create database on another directory)
	SIZE = 5MB, -- Initial database size
	MAXSIZE = 50MB, -- Maximum database size
	FILEGROWTH = 5MB) -- Database size increment
LOG 
-- Save as above, but for logs
ON (NAME = 'GAMESTORE.LOG',
	FILENAME = '/mssql/GAME_STORE.LOG',
	SIZE = 5MB,
	MAXSIZE = 50MB,
	FILEGROWTH = 5MB)
```

Create Client table
```sql
CREATE TABLE [CLIENT] -- Brackets escape whitespaces, special chars, etc...
(
	[CPF] [CHAR] (11),
	[NAME] [VARCHAR] (100),
	[ADDRESS A] [VARCHAR] (150),
	[ADDRESS B] [VARCHAR] (150),
	[CITY] [VARCHAR] (50),
	[PROVINCE] [CHAR] (2),
	[CEP] [CHAR] (8),
	[BORN DATE] [DATE],
	[AGE] [SMALLINT],
	[GENRE] [CHAR] (1),
	[CREDIT LIMIT] [MONEY],
	[PURCHASE VOLUME] [FLOAT],
	[FIRST PURCHASE] [BIT] -- BIT = BOOLEAN
)
```

Create Seller table
```sql
CREATE TABLE [SELLER]
(
	[ENROLLMENT] [CHAR] (5),
	[NAME] [VARCHAR] (100),
	[COMISSION PERCENTAGE] [FLOAT]
)
```

Create Product table
```sql
CREATE TABLE [PRODUCTS]
(
	[ID] [VARCHAR] (20),
	[NAME] [VARCHAR] (150),
	[PACKAGING] [VARCHAR] (50),
	[SIZE] [VARCHAR] (50),
	[FLAVOR][VARCHAR] (50),
	[LIST PRICE] [SMALLMONEY]
)
```

## You can also

Delete table
```sql
USE [DATABASE_NAME]
DROP TABLE [TABLE_NAME];
```

Delete database
```sql
DROP DATABASE GAME_STORE
```

