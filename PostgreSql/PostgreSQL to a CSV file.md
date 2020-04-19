PostgreSQL to a CSV file
```sql
Copy (Select * From foo) To '/tmp/test.csv' With CSV DELIMITER ',';
```
