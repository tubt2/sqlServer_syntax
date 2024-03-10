# Lesson 4
## Temp table
```sql
/*
     Trong sql server khi bảng tạm (Temporary table) được tạo ra sẽ được lưu trên RAM và tiến trình xử lý của các session với các bảng này sẽ được xử lý trên RAM vì thế tốc độ rất nhanh.
    Có 2 loại bảng tạm trong sql server: Local temp và Global temp
*/
    -- Local Temp Table
    CREATE TABLE #LocalTempTable (
        ID INT,
        Name VARCHAR(50)
    );

    -- Global Temp Table
    CREATE TABLE ##GlobalTempTable (
        ID INT,
        Name VARCHAR(50)
    );

```

## Common Table Expression
```sql
-- Common Table Expression
WITH CTE_Table1 AS (
    SELECT ID, Name
    FROM YourTable1
    WHERE Condition1
)
SELECT * FROM CTE_Table1;

-- Multi CTE table 

WITH CTE_Table1 AS (
    SELECT ID, Name
    FROM YourTable1
    WHERE Condition1
),
CTE_Table2 AS (
    SELECT ID, Name
    FROM YourTable2
    WHERE Condition2
)
SELECT *
FROM CTE_Table1
JOIN CTE_Table2 ON CTE_Table1.ID = CTE_Table2.ID;

```
## Insert, Delete, Update, Alter
```sql
/* Insert: thêm bản ghi 1 vào 1 bảng có sẵn */

-- Insert values into a table
INSERT INTO YourTable (Column1, Column2)
VALUES (Value1, Value2);

-- Insert values from a select statement
INSERT INTO YourTable (Column1, Column2)
SELECT Column1, Column2
FROM AnotherTable
WHERE Condition;


/* Delete: xóa bản ghi (có điều kiện) từ 1 bảng */
-- Delete records from a table
DELETE FROM YourTable
WHERE Condition;

-- Delete records from multiple tables using JOIN
DELETE t1
FROM Table1 t1
JOIN Table2 t2 ON t1.ID = t2.ID
WHERE t1.Condition;

/* Update: cập nhật lại giá trị của các cột trong bảng */

-- Update records in a table
UPDATE YourTable
SET Column1 = NewValue1, Column2 = NewValue2
WHERE Condition;

-- Update records in multiple tables using JOIN
UPDATE t1
SET t1.Column1 = NewValue1, t2.Column2 = NewValue2
FROM Table1 t1
JOIN Table2 t2 ON t1.ID = t2.ID
WHERE t1.Condition;

/* Alter: sửa cấu trúc bảng, sửa kiểu dữ liệu, thêm/xóa các ràng buộc trong bảng... */

-- Add column to an existing table
ALTER TABLE YourTable
ADD NewColumn DataType;

-- Drop column from existing table
ALTER TABLE YourTable
DROP COLUMN ColumnName;

-- Modify datatype in SQL Server
ALTER TABLE YourTable
ALTER COLUMN ColumnName NewDataType;


```