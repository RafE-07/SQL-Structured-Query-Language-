# SQL(**Structured Query Language)**

# Introduction

- A special language used to save and work with data in a relational database is called SQL.
- Database(create,read,update,delete)

            

# TOOLS

- MySql
- XAMPP
- DataGrip (paid)
- pycharm (paid)
- VScode , mysql ext. (paid)
- DBever(free)
- mysql workbench(free)
- dbforge studio(crack)
- oracle sql(free)

# CREATING DATABASE

- Click (+) button to ensure connection
- .sql format file create—→auto connection
- run —→CREATE DATABASE filename{select full text}

```sql
CREATE DATABASE testdb;
```

1. create a simple product table
- id
- name
- price
- stock
- created_at
- updated_at

```sql

USE testdb;
CREATE TABLE products (
  `id` INT AUTO_INCREMENT PRIMARY KEY,
  `name` VARCHAR(100) NOT NULL,
  `price` DECIMAL(10,2) NOT NULL,
  `stock` INT DEFAULT NULL,
  `created_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `updated_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
); 
```

COMMENTS :

starts with (- -)

```sql
*-- Create the products table*
```

VARIABLE :

- Syntax:

```sql
-- Assign a value
SET @price = 500;
SET @stock = 20;
```

- Basic Operations :

```sql
SELECT @num1 + @num2 AS total;
SELECT @num1 * @num2 AS product;
SELECT @num2 / @num1 AS division;
SELECT @num1 % @num2 AS modulus;
SELECT @num2 - @num1 AS difference;

-- Alternative
SELECT @num1 + @num2 AS total,
       @num1 * @num2 AS product,
       @num2 / @num1 AS division,
       @num1 % @num2 AS modulus,
       @num2 - @num1 AS difference,
       POWER(@num1, 2) AS power,
       SQRT(@num2) AS square_root,
       GREATEST(@num1, @num2) AS greatest,
       LEAST(@num1, @num2) AS least;
```

BUILD IN STRING FUNCTION :

- LOWER_CASE :

```sql
SET @text = "Syed MAHmudul Islam";

SELECT LOWER(@text) AS lower_text;
```

- UPPER_CASE :

```sql
SELECT UPPER(@text) AS upper_text;
```

- LENGTH :

```sql
SELECT LENGTH(@text) AS text_length;
```

- SUBSTRING :

```sql
SELECT SUBSTRING(@text, 6, 8) AS substring_text;
```

- REPLACE :

```sql
SELECT REPLACE(@text, 'Islam', 'rafi') AS replaced_text;
```

- STRING MENUPULATION :

```sql
        TRIM(@text) AS trimmed_text,
        CONCAT(@text, ' - Developer') AS concatenated_text,
        LOCATE('MAHmudul', @text) AS position_of_substring,
        LEFT(@text, 4) AS left_text,
        RIGHT(@text, 5) AS right_text,
        LPAD(@text, 30, '*') AS left_padded_text,
        RPAD(@text, 30, '*') AS right_padded_text
        REVERSE(@text) AS reversed_text,
        INSTR(@text, 'MAHmudul') AS instr_position
```

- DATE_TIME :
```sql
  --CURRENT DATE AND TIME
SELECT NOW() as CURRENTDATETIME;
SELECT CURDATE() as CURRENTDATE;
SELECT CURTIME() as CURRENTTIME;

--DATE DIFFERENCE
SELECT DATEDIFF('2024-12-31', '2024-01-01') as DATEDIFFERENCEINDAYS;

--ADD DAYS TO DATE
SELECT DATE_ADD('2024-01-01', INTERVAL 11 MONTH) as NEWDATEAFTERADDINGMONTHS;     
SELECT DATE_ADD('2024-01-01', INTERVAL 10 DAY) as NEWDATEAFTERADDINGDAYS;
```
