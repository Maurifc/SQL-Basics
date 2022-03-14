# Field order and Primary Key

Insert without describe fields
> There is no need to inform fields when inserting values according to field sequence
```sql
INSERT INTO PRODUCT
VALUES
(
	'788975',
	'Pedaços de Frutas - 1,5 Litros - Maça',
	'1.5 L',
	'PET',
	'Maçã',
	18.01
);
```

Insert in a different field order
> You may change value order if you change field order too
```sql
INSERT INTO SELLER
(
	NAME,
	ENROLLMENT ,
	[COMISSION PERCENTAGE] 
)
VALUES
(
	'Alberto de Sá Verneck',
	'00239',
	0.08
);
```

Insert another product
```sql
INSERT INTO PRODUCT
VALUES
(
	'1002767',
	'Videira do Campo - 700 ml - Cereja/Maça',
	'1.5 L',
	'Garrafa',
	'Cereja/Maçã',
	8.41
);
```

Set ID fielas as primary key on PRODUCT table
```sql
ALTER TABLE PRODUCT
ADD CONSTRAINT PK_PRODUCT -- PK_PRODUCT is arbitrary, but, by convention, use PK_<TABLE_NAME>
PRIMARY KEY CLUSTERED (ID)
```

```sql
ALTER TABLE PRODUCT 
ALTER COLUMN ID VARCHAR(20) NOT NULL; -- First set field as not null
```

To delete rows which certain field is null, use
```sql
DELETE FROM <TABLE_NAME>
WHERE <FIELD> IS NULL;
```

Set ENROLLMENT field as primary key on SELLER table
```sql
ALTER TABLE SELLER 
ALTER COLUMN ENROLLMENT CHAR(50) NOT NULL; -- First set field as not null
```

```sql
ALTER TABLE SELLER
ADD CONSTRAINT PK_SELLER
PRIMARY KEY CLUSTERED (ENROLLMENT)
```

Set COMISSION PERCENTAGE field as not null
```sql
ALTER TABLE SELLER 
ALTER COLUMN [COMISSION PERCENTAGE] FLOAT NOT NULL;
```

Set CPF field as primary key on CLIENT table
```sql
ALTER TABLE CLIENT 
ALTER COLUMN CPF CHAR(11) NOT NULL; -- First set field as not null
```

```sql
ALTER TABLE CLIENT
ADD CONSTRAINT PK_CLIENT
PRIMARY KEY CLUSTERED (CPF)
```

Insert a client
```sql
INSERT INTO CLIENT
(CPF, NAME, [ADDRESS A], [ADDRESS B], CITY, PROVINCE, CEP, [BORN DATE], AGE, GENRE, [CREDIT LIMIT], [PURCHASE VOLUME], [FIRST PURCHASE])
VALUES(
	'00383454802',
	'João da Silva',
	'Rua Projetada A',
	'Número 233',
	'Rio de Janeiro',
	'RJ',
	'22555332',
	'1967-05-22',
	54,
	'M',
	20000.0,
	3000.23,
	1
);
```