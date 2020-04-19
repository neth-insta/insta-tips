# PostgreSQL to a CSV file
```sql
Copy (Select * From foo) To 'D:/test.csv' With CSV DELIMITER ',';
```
