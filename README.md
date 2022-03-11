## Basics
Run with docker

```bash
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Awesomepass@" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2019-latest
```

Connect locally  
[Install sqlcmd before continue](https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-ver15#ubuntu)
```bash
sqlcmd -S localhost -U SA
```



Create a new database
```bash
CREATE DATABASE TestDB
```

List databases
(Must type go to execute last commands)
```bash
SELECT Name from sys.Databases
GO
```


Select a database to use
```bash
USE TestDB
```

Create a new table
```bash
CREATE TABLE Inventory (id INT, name NVARCHAR(50), quantity INT)
```
Insert Data
```bash
INSERT INTO Inventory VALUES (1, 'banana', 150);
INSERT INTO Inventory VALUES (2, 'orange', 154);
```

Execute previous commands
```bash
GO
```

Select
```bash
SELECT * FROM Inventory WHERE quantity > 152;
GO
```

