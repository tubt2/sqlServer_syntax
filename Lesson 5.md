# Lesson 5

## Window function
<img src="./assets/window_function.png" alt="image" width="70%" height="auto">

```sql
--row_number
SELECT *,
    ROW_NUMBER() OVER (PARTITION BY column_name ORDER BY order_column) AS row_num
FROM table_name;

-- rank
SELECT *,
    RANK() OVER (PARTITION BY column_name ORDER BY order_column) AS rank_num
FROM table_name;

-- sum partition
SELECT *,
    SUM(column_name) OVER (PARTITION BY partition_column ORDER BY order_coulmn) AS sum_partition
FROM table_name;

-- max partition
SELECT *,
    MAX(column_name) OVER (PARTITION BY partition_column ORDER BY order_column) AS max_partition
FROM table_name;

select
	sum(lcy_amt) over(partition by storedid, trans_date order by sale_id desc
			rows between 2 preceding and current row) as over_sum
	,*
from test_sql.dbo.banhang;

current row: dòng hiện tại
preceding: các dòng bên trên của dòng hiện tại
following: các dòng bên dưới của dòng hiện tại
partition by : chia cả bảng lớn thành các bản bé hơn thông qua trường được partition

```
[Link Window function](https://datapot.vn/windows-functions-trong-sql-va-ung-dung-cua-no/)

## Join Statement

<img src="./assets/join.png" alt="image" width="70%" height="auto">

```sql
-- left join: trả về các bản ghi của bảng bên trái (table1), với các bản ghi không map được qua key join ở on, những bản ghi đó sẽ NULL thông tin các cột của bảng bên phải (table2)
SELECT *
FROM table1
LEFT JOIN table2 ON table1.column_name = table2.column_name;

-- right join: trả về các bản ghi của bảng bên phải(table2), với các bản ghi không map được qua key join ở on, những bản ghi đó sẽ NULL thông tin các cột của bản bên trái (table1)
SELECT *
FROM table1
RIGHT JOIN table2 ON table1.column_name = table2.column_name;

-- inner join: trả về bản ghi có key join xuất hiện đồng thời ở cả 2 bảng
SELECT *
FROM table1
INNER JOIN table2 ON table1.column_name = table2.column_name;

-- full join: trả về tất cả các bản ghi của 2 bảng,những bản ghi xuất hiện đồng thời sẽ được trả 1 lần
SELECT *
FROM table1
FULL JOIN table2 ON table1.column_name = table2.column_name;

```