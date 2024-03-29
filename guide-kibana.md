# guide-kibana.md

## KQL(Kibana Query Language) Example

[Reference: Kibana Query Language](https://www.elastic.co/guide/en/kibana/current/kuery-query.html)

### 1. 특정 필드에 대한 검색

```status:404```

- `status` 필드가 404 값을 가진 모든 문서를 검색합니다.

### 2. AND 조건

```status:404 AND extension:php```

- `status` 필드가 404이며 `extension` 필드가 `php`인 모든 문서를 검색합니다.

### 3. OR 조건

```status:404 OR status:500```

- `status` 필드의 값이 404 또는 500인 문서를 검색합니다.

### 4. NOT 조건

```status:200 AND NOT extension:css```

- `status` 필드의 값이 200이지만 `extension` 필드의 값이 `css`가 아닌 문서를 검색합니다.

### 5. 와일드카드

```message:*timeout*```

- `message` 필드에 "timeout"이라는 단어가 포함된 모든 문서를 검색합니다.

### 6. 범위 검색

```bytes:[1000 TO 2000]```

- `bytes` 필드의 값이 1000에서 2000 사이인 문서를 검색합니다.

### 7. 존재하지 않는 필드 찾기

```NOT _exists_:fieldName```

- `fieldName`이라는 필드가 존재하지 않는 모든 문서를 검색합니다.

### 8. 정규식

```extension:/p?ng/```

- `extension` 필드의 값이 "png" 또는 "ping"인 문서를 검색합니다.

### 9. 특정 필드의 값이 존재하는 문서 검색

```_exists_:fieldName```

- `fieldName`이라는 필드가 존재하는 모든 문서를 검색합니다.
