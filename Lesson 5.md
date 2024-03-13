# Lesson 5

## Window function
```sql
--row_number
SELECT *,
    ROW_NUMBER() OVER (PARTITION BY column_name ORDER BY order_column) AS row_num
FROM table_name;

-- rank
SELECT *,
    RANK() OVER (PARTITION BY column_name ORDER BY order_column) AS rank_num
FROM table_name;
```