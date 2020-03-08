# postgresql tip

## time zone set

```sql
select * from pg_timezone_names
where name like '%Seoul%';

SET TIME ZONE 'Asia/Seoul';
```
