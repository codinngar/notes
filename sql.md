## SQL Constraints
| Constraint     | Description                         |
| -------------- | ----------------------------------- |
| `NOT NULL`     | values cannot be null               |
| `UNIQUE`       | values cannot match any older value |
| `PRIMARY KEY`  | used to uniquely identify a row     |
| `FOREIGN KEY`  | references a row in another table   |
| `CHECK`        | validates condition for new value   |
| `DEFAULT`      | set default value if not passed     |
| `CREATE INDEX` | used to speedup the read process    |

## SQL Data Types

#### Numeric Data Types
| Data Type      | Description                       |
| -------------- | --------------------------------- |
| `TINYINT`      | Very small integer (-128 to 127)  |
| `SMALLINT`     | Small integer (-32,768 to 32,767) |
| `INT`          | Standard integer (-2B to 2B)      |
| `BIGINT`       | Large integer (for big numbers)   |
| `DECIMAL(p,s)` | Fixed-point number (exact value)  |
| `FLOAT`        | Single precision (approximate)    |
| `DOUBLE`       | Double precision (approximate)    |

#### String Data Types
| Data Type    | Description                               |
| ------------ | ----------------------------------------- |
| `CHAR(n)`    | Fixed-length string                       |
| `VARCHAR(n)` | Variable-length string (max 65,535 bytes) |
| `TEXT`       | Large text (max ~64KB)                    |
| `TINYTEXT`   | Up to 255 characters                      |
| `MEDIUMTEXT` | Up to 16MB of text                        |
| `LONGTEXT`   | Up to 4GB of text                         |

#### Date and Time Data Types
| Data Type   | Description                           |
| ----------- | ------------------------------------- |
| `DATE`      | Only date (YYYY-MM-DD)                |
| `TIME`      | Only time (HH:MM:SS)                  |
| `DATETIME`  | Date and time (YYYY-MM-DD HH:MM:SS)   |
| `TIMESTAMP` | Like DATETIME, but auto-updated often |
| `YEAR`      | Year only (YYYY)                      |

#### Boolean Type
| Data Type | Description                                    |
| --------- | ---------------------------------------------- |
| `BOOLEAN` | Synonym for `TINYINT(1)` (0 = false, 1 = true) |

#### Misc / Special Types
| Data Type | Description                                                               |
| --------- | ------------------------------------------------------------------------- |
| `ENUM`    | One value from a predefined list (e.g., `'small'`, `'medium'`, `'large'`) |
| `SET`     | A set of zero or more values from a predefined list                       |
| `BLOB`    | Binary data (e.g., images, files)                                         |

## Data Definition Language (DDL)
#### CREATE
```sql
CREATE TABLE table_name (
	id INT PRIMARY KEY,
	name VARCHAR(20)
);
```

#### ALTER
```sql
ALTER TABLE table_name
ADD email VARCHAR(50);

ALTER TABLE table_name
RENAME COLUMN email TO gmail;

ALTER TABLE table_name
MODIFY COLUMN email VARCHAR(100);

ALTER TABLE table_name
MODIFY COLUMN email VARCHAR(100);
AFTER id;
FIRST;

ALTER TABLE table_name
DROP COLUMN email;
```

#### DROP
- completely removes both the data and the table structure
```sql
DROP TABLE table_name;

DROP DATABASE database_name;
```

#### TRUNCATE
- removes all rows but preserves the table structure
```sql
TRUNCATE TABLE table_name;
```

## Data Manipulation Language (DML)
#### INSERT
```sql
INSERT INTO table_name (id, name)
VALUES (1, "Ali"),
	   (2, "Ziad");
```

#### UPDATE
```sql
UPDATE table_name
SET name = "Ahmed",
	age = 32
WHERE id = 1;
```

#### DELETE
```sql
DELETE FROM table_name
WHERE id = 2;
```

## Data Query Language (DQL)
#### SELECT
```sql
SELECT *
FROM table_name

SELECT id
FROM table_name

SELECT id AS person_id
FROM table_name

SELECT salary, salary + 100
AS "salary + 100"
```

#### DISTINCT
```sql
SELECT DISTINCT name
FROM table_name
```

#### AND
```sql
SELECT * FROM table_name
WHERE id < 10 AND age > 30;
```

#### OR
```sql
SELECT * FROM table_name
WHERE id < 10 OR age > 30;
```

#### NOT
```sql
SELECT * FROM table_name
WHERE name NOT "Ziad";
```
#### BETWEEN
```sql
SELECT * FROM table_name
WHERE age BETWEEN 10 AND 30;
```

#### IN
```sql
SELECT * FROM table_name
WHERE age IN [32, 54, 18];
```

#### Wildcards
```sql
SELECT * FROM table_name
WHERE name LIKE "A%"; -- % means multiple characters

SELECT * FROM table_name
WHERE name LIKE "A_"; -- _ means single character
```

#### ORDER BY
```sql
SELECT * FROM table_name
ORDER BY name, age DESC
LIMIT 10
```
