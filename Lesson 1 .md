# Lesson 1

## Datatype
Các kiểu dữ liệu thường gặp trong SQL server được chia thành 3 nhóm chính:
1. String: varchar(10), nvarchar(10), char(10), nchar(10), text...
2. Number: integer, float, decimal(18,0), numeric(18,0) ...
4. Date: date, datetime, datetime2 ...

| Data type      | Sample value |
| ----------- | ----------- |
| Sring      | a,b, sql server       |
| Number   | 1,2,-1,-10, 2.908990        |
|Date| 2024-03-05, 2024-03-04 20:58:40.233, 2024-03-04 20:58:40.233786

## Create, drop, use database
```sql
CREATE DATABASE <DATABASE_NAME>;

ON  primary 
( NAME = TRAINING_MCI,  
  FILENAME = 'D:\Database\TRAINING_MCI.mdf',--Đường dẫn chưa file .mdf
    SIZE = 10,  
    MAXSIZE = 50,  
 FILEGROWTH = 5 
 )  
LOG ON  
( NAME = TRAINING_MCI_LOG,  
  FILENAME = 'D:\Database\TRAINING_MCI_LOG.ldf', -- Đường dẫn chưa file .ldf
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB 
)
;

-- file .mdf: file chứa data của bảng được lưu trong vào datafile
-- file .ldf : file chứa transaction log của người dùng tương tác vào database

USE <DB_NAME>;  -- sử dụng database

DROP <DB_NAME>; --xóa database
```
## Table
```sql
-- tạo table
CREATE TABLE <db_name>.<schema_name>.<table_name> -- Data Definition Languague
(
col1 <datatype>,
col2 <datatype>,
...
col_n <datatype>

)
;
-- Xóa table
DROP TABLE [IF EXISTS] <table_name>;


```

## Get data 
Trong sql khi cần truy vấn (get data) từ 1 bảng trong database, sử dụng mệnh đề `SELECT`

```sql
SELECT <list column>
FROM <db_name>.<schema_name>.<table_name>
;

khi muốn lấy hết tất cả các cột thay vì liệt kê toàn bộ tên cột của bảng ta thay thế bằng ký tự `*`
SELECT *
FROM <db_name>.<schema_name>.<table_name>
;

khi cần lấy 1 số dòng nhất định trong sql server dùng mệnh đề Top N

SELECT TOP 10 *
FROM <db_name>.<schema_name>.<table_name>
;

```

## Comment trong Sql Server
Trong SQL Server khi cần comment có thể sử dụng 1 trong 2 cách sau. Lưu ý khi sql thực thi code sẽ không thực thi các comment này. Nên sử dụng comment để note lại code đang muốn làm gi, ngày sửa, add rule code...

cách 1: sử dụng ít nhất 2 dấu `--`
```sql
-- đây là comment

```
cách 2: sử dụng `/* */`
```sql

/* đây là comment */
```

## Order by
Mệnh đề `Order by` cho phép sắp xếp lại kết quả truy vấn dữ liều từ mệnh đề `Select`

Có 2 kiểu sắp xếp:
1. Sắp xếp tăng dần: ascending /asc
2. Sắp xếp giảm dần: descending/ desc

```sql

SELECT * 
FROM <db_name>.<schema_name>.<table_name>
ORDER BY col1 asc/desc

-- mặc định trong sql khi không khai báo asc hay desc, thì kiểu sắp xếp sẽ là asc (tăng dần)

```