# Lessson 6

## Pivot

```sql

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
-- Primary Key
ALTER TABLE YourTable
ADD CONSTRAINT PK_YourTable PRIMARY KEY (Column1);

-- Foreign Key
ALTER TABLE YourTable
ADD CONSTRAINT FK_YourTable FOREIGN KEY (Column2)
REFERENCES OtherTable (Column3);

```

# View

```sql
CREATE VIEW DBO.VW_DEMO AS
SELECT *
FROM TABLE
WHERE 1=1 AND CONDITION

```
