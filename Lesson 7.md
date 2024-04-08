# Lesson 7

## IF else

```sql
IF 1=1
    BEGIN
        print('pass')
    END
ELSE
    BEGIN
        print('not pass')
    END


```
## Dynamic code
```sql
DECLARE @myVariable INT;
SET @myVariable = 10;

PRINT(@myVariable)

--- dynamic code

DECLARE @dynamicSQL NVARCHAR(MAX);
SET @dynamicSQL = N'SELECT * FROM YourTable WHERE ColumnName = ' + CAST(@myVariable AS NVARCHAR(10));

EXEC sp_executesql @dynamicSQL;

---

DECLARE @myVar varchar(8) = 'store 1'

SELECT *
FROM <Table>
WHERE COL = @myVar


```