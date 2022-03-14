## Basics
Run MS SQL Server with docker

```sql
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Awesomepass@" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2019-latest
```

Connect locally  
[Install sqlcmd before continue](https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-ver15#ubuntu)
```sql
sqlcmd -S localhost -U SA
```

Create a new database
```sql
CREATE DATABASE TestDB
```

List databases
(Must type go to execute last commands)
```sql
SELECT Name from sys.Databases
GO
```


Select a database to use
```sql
USE TestDB
```

Create a new table
```sql
CREATE TABLE Inventory (id INT, name NVARCHAR(50), quantity INT)
```
Insert Data
```sql
INSERT INTO Inventory VALUES (1, 'banana', 150);
INSERT INTO Inventory VALUES (2, 'orange', 154);
```

Execute previous commands
```sql
GO
```

Select
```sql
SELECT * FROM Inventory WHERE quantity > 152;
GO
```

## Sample Database
Load a [sample database](sample database/README.md) to practice


## Reference
<https://www.sqlservertutorial.net/>