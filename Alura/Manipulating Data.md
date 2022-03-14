# Manipulating Data.md

Insert Product
```sql
INSERT INTO PRODUCT
(
	ID,
	NAME,
	PACKAGING,
	[SIZE],
	FLAVOR,
	[LIST PRICE]
) VALUES
(
	'1040107',
	'Light - 350 ml - Melancia',
	'Lata'
	'350 ml',
	'Melancia',
	4.56
);

INSERT INTO PRODUCT
(
	ID,
	NAME,
	PACKAGING,
	[SIZE],
	FLAVOR,
	[LIST PRICE]
) VALUES
(
	'1037797',
	'Clean - 2 Litros - Laranja',
	'PET',
	'2 L',
	'Laranja',
	16.01
);
```

Insert Sellers
```sql
INSERT INTO SELLER
(
	ENROLLMENT,
	NAME,
	[COMISSION PERCENTAGE]
) VALUES
(
	'00235',
	'Márcio Almeida Silva',
	0.08
);

INSERT INTO SELLER
(
	ENROLLMENT,
	NAME,
	[COMISSION PERCENTAGE]
) VALUES
(
	'00236',
	'Cláudia Moraes',
	0.08
)
```

Insert wrong data
```sql
INSERT INTO PRODUCT
(
	ID,
	NAME,
	PACKAGING,
	[SIZE],
	FLAVOR,
	[LIST PRICE]
) VALUES
('544931', 'Frescor do Ver�o - 350 ml - Lim�o', 'PET', '350 ml','Lim�o',3.20),
('1078680', 'Frescor do Ver�o - 470 ml - Manga', 'Lata', '470 ml','Manga',5.18)
```

Fix wrong data
```sql
UPDATE PRODUCT
SET
	PACKAGING = 'Lata',
	[LIST PRICE] = 2.46
WHERE 
	ID = '544931';

UPDATE PRODUCT
SET
	PACKAGING = 'Garrafa'
WHERE 
	ID = '1078680';
```

Update sellers' information
```sql
UPDATE SELLER
SET
	[COMISSION PERCENTAGE]  = 0.11
WHERE 
	ENROLLMENT  = '00235';
	
UPDATE SELLER
SET
	NAME = 'Cláudia Moraes Souza'
WHERE 
	ENROLLMENT = '00236';
```

Delete a product
```sql
DELETE FROM PRODUCT
WHERE
	ID = '1078680'
```

Delete a seller
```sql
DELETE FROM SELLER
WHERE
	ENROLLMENT = '00235'
```