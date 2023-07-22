# guide-database.md

### mysql 에서 column_name 으로 시작하는 컬럼을 가진 모든 테이블 찾기

```sql
SELECT TABLE_NAME,
       COLUMN_NAME
FROM INFORMATION_SCHEMA.COLUMNS
WHERE COLUMN_NAME LIKE 'column_name%';
```