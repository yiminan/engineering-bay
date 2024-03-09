# guide-redis.md

Redis에서 사용할 수 있는 주요 명령어 모음은 다음과 같습니다.   
이 명령어들은 데이터의 저장, 조회, 수정, 삭제 등 다양한 작업을 수행하는 데 사용됩니다.  
Redis 데이터 구조에 따라 사용되는 명령어가 다르기 때문에, 여기에는 가장 일반적으로 사용되는 명령어들을 포함시켰습니다.

### 일반 명령어

- **`KEYS pattern`**: 키 패턴에 일치하는 모든 키를 반환합니다.
- **`SCAN cursor [MATCH pattern] [COUNT count]`**: 데이터베이스를 점진적으로 스캔합니다.
- **`EXISTS key`**: 키가 존재하는지 확인합니다.
- **`DEL key`**: 키를 삭제합니다.
- **`TYPE key`**: 키의 데이터 타입을 반환합니다.
- **`EXPIRE key seconds`**: 키의 만료 시간을 설정합니다.
- **`TTL key`**: 키의 남은 만료 시간을 초 단위로 반환합니다.

### 문자열(String) 명령어

- **`SET key value`**: 키에 문자열 값을 설정합니다.
- **`GET key`**: 키의 값을 가져옵니다.
- **`INCR key`**: 키의 값을 1 증가시킵니다.
- **`DECR key`**: 키의 값을 1 감소시킵니다.
- **`APPEND key value`**: 키의 값을 끝에 추가합니다.

### 해시(Hash) 명령어

- **`HSET key field value`**: 해시 키의 필드에 값을 설정합니다.
- **`HGET key field`**: 해시 키의 필드 값을 가져옵니다.
- **`HGETALL key`**: 해시 키의 모든 필드와 값의 쌍을 가져옵니다.
- **`HDEL key field`**: 해시 키의 필드를 삭제합니다.

### 리스트(List) 명령어

- **`LPUSH key value`**: 리스트의 왼쪽(앞)에 값을 추가합니다.
- **`RPUSH key value`**: 리스트의 오른쪽(뒤)에 값을 추가합니다.
- **`LPOP key`**: 리스트의 왼쪽에서 값을 꺼냅니다.
- **`RPOP key`**: 리스트의 오른쪽에서 값을 꺼냅니다.
- **`LRANGE key start stop`**: 리스트의 지정된 범위의 요소를 가져옵니다.

### 집합(Set) 명령어

- **`SADD key member`**: 집합에 멤버를 추가합니다.
- **`SMEMBERS key`**: 집합의 모든 멤버를 반환합니다.
- **`SREM key member`**: 집합에서 멤버를 삭제합니다.

### 정렬된 집합(Sorted Set) 명령어

- **`ZADD key score member`**: 정렬된 집합에 멤버와 그 점수를 추가합니다.
- **`ZRANGE key start stop [WITHSCORES]`**: 정렬된 집합의 범위 내 멤버를 반환합니다.

### HyperLogLog 명령어

- **`PFADD key element`**: HyperLogLog에 요소를 추가합니다.
- **`PFCOUNT key`**: HyperLogLog의 유니크한 요소의 개수를 반환합니다.

### 기타 데이터 구조 명령어

- **`SUBSCRIBE channel`**: 메시지 채널을 구독합니다.
- **`PUBLISH channel message`**: 메시지 채널에 메시지를 발행합니다.
- **`GEOADD key longitude latitude member`**: 지오스페이셜 인덱스에 위치를 추가합니다.
