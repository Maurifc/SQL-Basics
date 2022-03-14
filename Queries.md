# Queries

```sql
SELECT 
	CPF AS ID, -- ID, now, is an alias to CPF field
	NAME AS [CLIENT NAME]
FROM
	CLIENT
```

As result you get

| ID | CLIENTNAME |
| -- | ----------- | 
| 00383454802 | João da Silva | 

Select products with watermelon flavor
```sql
SELECT 
	*
FROM
	PRODUCT
WHERE
	FLAVOR = 'Melancia'
```

Increase LIST PRICE field in 10% for watermelon flavored products
```sql
UPDATE PRODUCT
SET
	[LIST PRICE] = 1.1 * [LIST PRICE] 
WHERE 
	FLAVOR = 'Melancia'
```

Select products with LIST PRICE lesser than $10
```sql
SELECT * FROM PRODUCT 
WHERE 
	[LIST PRICE] < 10
```

Select clients born in or after 1995
```sql
SELECT * FROM CLIENT
WHERE 
	MONTH([BORN DATE])  >= 9 -- 9 = september. Use MONTH() function to filter by month
```

Select client born in september, october, november and december
```sql
SELECT * FROM CLIENT
WHERE 
	MONTH([BORN DATE])  >= 9 -- 9 = september. Use MONTH() function to filter by month
```

Select clients who born in day 25
```sql
SELECT * FROM CLIENT
WHERE 
	DAY([BORN DATE])  = 25 -- Use DAY() function to filter by day
```

Select clients who born day 22 and province is RJ
```sql
SELECT * FROM CLIENT
WHERE 
	DAY ([BORN DATE]) = 22 AND
	PROVINCE = 'RJ'
```

Select sellers where comission percentage is greater than 9% or enrollment is 00236
```sql
SELECT * FROM SELLER
WHERE 
	[COMISSION PERCENTAGE] > 0.09 OR
	ENROLLMENT = '00236'
```