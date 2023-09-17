# guide-database.md

### mysql 에서 column_name 으로 시작하는 컬럼을 가진 모든 테이블 찾기

```sql
SELECT TABLE_NAME,
       COLUMN_NAME
FROM INFORMATION_SCHEMA.COLUMNS
WHERE COLUMN_NAME LIKE 'column_name%';
```

---

### mysql에서 해당 DB Transaction Isolation level 조회

```sql
SHOW
VARIABLES WHERE VARIABLE_NAME = 'tx_isolation';
```

---

### mysql에서 해당 DB Transaction Isolation level 변경

```sql
SET
GLOBAL TRANSACTION ISOLATION LEVEL READ COMMITTED;
```

---

### 현재 실행 중인 프로세스 리스트

```sql
SHOW
FULL
PROCESSLIST;
```

---

### 현재 실행 중인 프로세스 리스트에서 특정 프로세스 kill

```sql
KILL
PROCESS_ID;
```
