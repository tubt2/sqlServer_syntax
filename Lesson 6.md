# Lessson 6

## Pivot

```sql

-- pivot trong sql server giúp xoay chiều dữ liệu từ chiều row về column

SELECT *
FROM (
    SELECT Column1, Column2
    FROM YourTable
) AS SourceTable
PIVOT (
    SUM(Column2)
    FOR Column1 IN ([Value1], [Value2], [Value3])
) AS PivotTable;

```

## Unpivot

```sql
--unpivot trong sql server giúp xoay chiều dữ liệu từ cột về thành các dòng

SELECT Column1, Column2, Value
FROM 
   (SELECT Column1, Column2, Column3, Column4
   FROM YourTable) p
UNPIVOT
   (Value FOR Column IN (Column2, Column3, Column4)
)AS unpvt;

```


# Primary Key, Foreign key

```sql
-- Primary Key: cột (or bộ cột) được đánh là khóa chính, thì trường thông tin của cột (or bộ cột đó) sẽ là duy nhất (unique) và không chấp nhận giá trị NULL (not allow null)

ALTER TABLE YourTable
ADD CONSTRAINT PK_YourTable PRIMARY KEY (Column1);

-- Foreign Key: khóa ngoại để tăng tính nhất quán và ràng buộc giữa các bảng trong 1 database
ALTER TABLE YourTable
ADD CONSTRAINT FK_YourTable FOREIGN KEY (Column2)
REFERENCES OtherTable (Column3);

```

# View

```sql

-- view trong sql giúp tạo ra 1 khung nhìn (có thể xem là 1 bảng ảo) link với bảng chính (bảng from trong câu lệnh define ra view), khi dữ liệu ở bảng chính thay đổi dữ liệu ở view cũng thay đổi theo và ngược lại

CREATE VIEW DBO.VW_DEMO AS
SELECT *
FROM TABLE
WHERE 1=1 AND CONDITION

-- SỬA VIEW
ALTER VIEW DBO.VW_DEMO
AS
SELECT *
FROM TABLE
WHERE CONDITION;

-- DROP VIEW
    drop view  if exists dbo.vw_demo;

```
