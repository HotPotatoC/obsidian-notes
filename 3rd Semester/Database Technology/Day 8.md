# Day 8
Class: [[COMP6799001 - Database Technology]]
Session:  8
Topics: Queries, Programming and Triggers
Date: 2022-12-06
Lecturer: [[3rd Semester/Lecturers/D6659 - EKO SETYO PURWANTO, S.Pd., M.Kom.]]

# Distinct in SQL

`DISTINCT` operation in SQL is used to remove duplicate rows in the specified list of columns.

Example:

```sql
select city
from sales.customers
order by city;
```

```
+----------+
|   city   |
+----------+
|  Bekasi  |
|  Bekasi  |
|  Jakarta |
|  Jakarta |
+----------+
```

Using `distinct`

```sql
select distinct city
from sales.customers
order by city;
```

```
+----------+
|   city   |
+----------+
|  Bekasi  |
|  Jakarta |
+----------+
```