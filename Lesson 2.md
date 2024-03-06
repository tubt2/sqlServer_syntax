# Leson 2

## Where
Trong `SQL` khi cần lấy data thỏa mãn điều kiện lọc(filter) nào đó ta sử dụng mệnh đề `Where`
```sql
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE <condition>
;

Các điều kiện hay gặp trong Where
-- so sánh bằng
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 = 
;

-- so sánh khác
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 !=  -- hoặc thay thế != bằng <>
;

-- so sánh lơn hơn, nhỏ hơn...
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 > -- <, >=, <=
;

-- tìm giá trị NULL
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 IS NULL
;

-- tìm giá trị NOT NULL
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 IS  NOT NULL
;

-- tìm giá trị IN trong 1 tập giá trị
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 IN ()
;

-- tìm giá trị NOT IN trong 1 tập giá trị
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 NOT IN ()
;

-- kết hợp nhiều điều kiện đồng thời: sử dụng AND để ngăn cách các điều kiện
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 = .. AND col2 = ...
;

-- kết hợp thỏa mãn 1 trong các điều kiện: sử dụng  OR
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 = .. OR col2 = ...
;

-- lấy giá trị nằm trong 1 khoảng: sử dụng BETWEEN AND -> chỉ sụng với datatype: Number, Date
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 BETWEEN <value_1> AND <value_2>
;


-- lấy giá trị nằm ngoài 1 khoảng: sử dụng NOT BETWEEN AND -> chỉ sụng với datatype: Number, Date
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 NOT BETWEEN <value_1> AND <value_2>
;

-- lấy các bản ghi giống trong sql server
SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 LIKE 'pattern';

-- lấy các bản ghi không giống trong sql server

SELECT [list_column]
FROM <db_name>.<schema_name>.<table_name>
WHERE col1 NOT LIKE 'pattern';

-- lấy loại bỏ trùng lặp
SELECT DISTINCT [list_column]
FROM <db_name>.<schema_name>.<table_name>
;

```


## Aggregate function
```sql
SELECT SUM(col1)
FROM <db_name>.<schema_name>.<table_name>
;

SELECT MIN(col1)
FROM <db_name>.<schema_name>.<table_name>
;

SELECT MAX(col1)
FROM <db_name>.<schema_name>.<table_name>
;

SELECT AVG(col1)
FROM <db_name>.<schema_name>.<table_name>
;

SELECT COUNT(col1)
FROM <db_name>.<schema_name>.<table_name>
;

SELECT COUNT(DISTINCT col1)
FROM <db_name>.<schema_name>.<table_name>
;

```

## Subquery
```sql
--sub query in sql server
SELECT column1, column2
FROM table1
WHERE column1 IN (SELECT column1 FROM table2 WHERE condition);

```
