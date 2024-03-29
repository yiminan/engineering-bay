# guide-database.md

## MySQL

- DB DDL에서 Column, Table의 comment 작성 필수

- FK는 column naming을 prefix: ‘ref_’를 적용
    - ex) ref_user_id, ref_payment_id

- 테이블 간에 FK의 Constraint는 사용하지 않는다.
    - 성능 이슈: Foreign key constraint는 데이터베이스에서 데이터 무결성을 유지하기 위해 오버헤드를 발생시킬 수 있습니다. 특히 대량의 데이터를 다루는 시스템에서는 외래 키 제약 조건이 쿼리
      실행 속도를 느리게 할 수 있습니다. 따라서 높은 처리량이 필요한 시스템에서는 외래 키를 사용하지 않고 데이터 무결성을 애플리케이션 수준에서 관리하기도 합니다.
    - 데이터 마이그레이션: 기존 데이터베이스 스키마에서 외래 키를 추가하려면 기존 데이터들이 외래 키 제약 조건을 충족해야 합니다. 데이터베이스에 이미 대량의 데이터가 존재하는 경우, 외래 키를 추가하는 것은
      복잡하고 시간이 많이 소요될 수 있습니다. 때로는 이러한 마이그레이션을 회피하기 위해 외래 키 제약을 추가하지 않을 수 있습니다.
    - 데이터 무결성 유지의 책임 위임: 외래 키 제약은 데이터베이스 레벨에서 데이터 무결성을 강제하는데 도움을 줍니다. 그러나 개발자들이 외래 키 제약에 대한 이해와 적절한 관리를 하지 못할 수도 있습니다.
      때로는 애플리케이션 수준에서 데이터 무결성을 보장하는 것이 더 적절하다고 판단되는 경우가 있을 수 있습니다.
    - 데이터베이스 간 종속성 문제: 외래 키 제약을 사용하면 다른 데이터베이스와의 연결 및 이관이 어려워질 수 있습니다. 특히 여러 개의 데이터베이스를 관리해야 하는 시스템에서는 외래 키를 사용하지 않고
      데이터베이스 간 종속성을 최소화하는 것이 유리할 수 있습니다.
    - 애플리케이션 요구사항: 일부 애플리케이션에서는 외래 키 제약이 필요하지 않을 수 있습니다. 예를 들어, 데이터를 주기적으로 삭제해야 하는 로그 저장소 또는 간단한 프로토타입 애플리케이션 등에서는 외래 키를
      사용하지 않을 수 있습니다.
    - 위의 이유들은 외래 키를 사용하지 않는 경우의 일반적인 이유들이지만, 이러한 결정은 각 상황에 따라 달라질 수 있습니다. 데이터베이스 설계는 데이터의 중요성과 애플리케이션의 요구사항을 고려하여 신중하게
      수행되어야 합니다. 외래 키의 사용 여부는 프로젝트 요구사항과 성능, 유지보수 등 다양한 요인들을 고려하여 결정되어야 합니다.

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
SELECT *
FROM information_schema.processlist;
```

---

### 현재 실행 중인 프로세스 리스트에서 특정 프로세스 kill

```sql
KILL
PROCESS_ID;
```

---

### mysql에서 특정 DB의 특정 테이블의 모든 컬럼 조회

```sql
SELECT *
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_SCHEMA = 'DB_NAME'
  AND TABLE_NAME = 'TABLE_NAME';
```

---

### mysql에서 특정 DB의 특정 테이블의 특정 컬럼 조회

```sql
SELECT *
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_SCHEMA = 'DB_NAME'
  AND TABLE_NAME = 'TABLE_NAME'
  AND COLUMN_NAME = 'COLUMN_NAME';
```
