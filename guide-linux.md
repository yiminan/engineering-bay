# Linux Command

### ls

| Command | Description                    |
|---------|--------------------------------|
| ls      | 현재 디렉토리의 파일 리스트 출력             |
| ls -l   | 현재 디렉토리의 파일 리스트 출력(상세)         |
| ls -a   | 현재 디렉토리의 파일 리스트 출력(숨김파일 포함)    |
| ls -h   | 현재 디렉토리의 파일 리스트 출력(사이즈)        |
| ls -t   | 현재 디렉토리의 파일 리스트 출력(시간)         |
| ls -r   | 현재 디렉토리의 파일 리스트 출력(역순)         |
| ls -R   | 현재 디렉토리의 파일 리스트 출력(하위 디렉토리 포함) |

### pwd

| Command | Description               |
|---------|---------------------------|
| pwd     | 현재 디렉토리의 경로 출력            |
| pwd -P  | 현재 디렉토리의 경로 출력(전체)        |
| pwd -L  | 현재 디렉토리의 경로 출력(심볼릭 링크)    |
| pwd -LP | 현재 디렉토리의 경로 출력(심볼릭 링크 포함) |

### cd

| Command     | Description    |
|-------------|----------------|
| cd [디렉토리명]  | 디렉토리 이동(상대 경로) |
| cd /[디렉토리명] | 디렉토리 이동(절대 경로) |
| cd ..       | 상위 디렉토리 이동     |
| cd ~        | 홈 디렉토리 이동      |
| cd -        | 이전 디렉토리 이동     |

### mkdir

| Command          | Description         |
|------------------|---------------------|
| mkdir [디렉토리명]    | 디렉토리 생성             |
| mkdir -p [디렉토리명] | 디렉토리 생성(하위 디렉토리 포함) |

### mv

| Command                | Description         |
|------------------------|---------------------|
| mv [파일명] [이동할 경로]      | 파일 이동               |
| mv [파일명] [변경할 파일명]     | 파일 이동(이름 변경)        |
| mv [디렉토리명] [이동할 경로]    | 디렉토리 이동             |
| mv [디렉토리명] [변경할 디렉토리명] | 디렉토리 이동(이름 변경)      |
| mv -r [디렉토리명] [이동할 경로] | 디렉토리 이동(하위 디렉토리 포함) |

### rm

| Command         | Description          |
|-----------------|----------------------|
| rm [파일명]        | 파일 삭제                |
| rm -r [디렉토리명]   | 디렉토리 삭제              |
| rm -f [파일명]     | 파일 강제 삭제             |
| rm -rf [디렉토리명]  | 디렉토리 강제 삭제           |
| rm -i [파일명]     | 파일 삭제(삭제 여부 확인)      |
| rm -ri [디렉토리명]  | 디렉토리 삭제(삭제 여부 확인)    |
| rm -rfi [디렉토리명] | 디렉토리 강제 삭제(삭제 여부 확인) |

### nslookup

| Command                  | Description      |
|--------------------------|------------------|
| nslookup [도메인명]          | 도메인명의 IP 주소 확인   |
| nslookup -type=a [도메인]   | 도메인명의 A 레코드 확인   |
| nslookup -type=ns [도메인]  | 도메인명의 NS 레코드 확인  |
| nslookup -type=mx [도메인]  | 도메인명의 MX 레코드 확인  |
| nslookup -type=soa [도메인] | 도메인명의 SOA 레코드 확인 |

### lsof

| Command            | Description            |
|--------------------|------------------------|
| lsof -i :[포트번호]    | 포트번호를 사용하는 프로세스 확인     |
| lsof -i tcp:[포트번호] | 포트번호를 사용하는 TCP 프로세스 확인 |
| lsof -i udp:[포트번호] | 포트번호를 사용하는 UDP 프로세스 확인 |

### base64 (encode/decode)

| Command                                       | Description      |
|-----------------------------------------------|------------------|
| echo -n [문자열] \| base64                       | 문자열을 base64로 인코딩 |
| echo -n [문자열] \| base64 -d                    | 문자열을 base64로 디코딩 |
| base64 -i [파일명] -o [파일명]                      | 파일을 base64로 인코딩  |
| base64 -D -i [파일명] -o [파일명]                   | 파일을 base64로 디코딩  |
| base64 -d -> enter -> 인코딩대상문자열 -> control + D | base64 문자열 디코딩   |
| base64 -> enter -> 디코딩대상문자열 -> control + D    | base64 문자열 인코딩   |

### diff

| Command                            | Description        |
|------------------------------------|--------------------|
| diff [파일명1] [파일명2]                 | 두 파일의 차이 비교        |
| diff [파일명1] [파일명2] > [차이를 저장할 파일명] | 두 파일의 차이 비교(결과 저장) |
| diff -u [파일명1] [파일명2]              | 두 파일의 차이 비교(상세)    |
| diff -r [디렉토리명1] [디렉토리명2]          | 두 디렉토리의 차이 비교      |

### cmp

| Command           | Description          |
|-------------------|----------------------|
| cmp [파일명1] [파일명2] | byte 단위로 두 파일의 차이 비교 |

### vim

| Command              | Description |
|----------------------|-------------|
| vim [파일명]            | 파일 편집       |
| vim -d [파일명1] [파일명2] | 두 파일의 차이 비교 |

### history

| Command               | Description |
|-----------------------|-------------|
| history               | 명령어 히스토리    |
| history \| grep [검색어] | 명령어 히스토리 검색 |

### cat

| Command      | Description        |
|--------------|--------------------|
| cat [파일명]    | 파일 내용 출력           |
| cat -n [파일명] | 파일 내용 출력(라인 번호 포함) |
