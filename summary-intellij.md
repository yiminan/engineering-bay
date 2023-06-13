# summary-intellij.md

# IntelliJ Shortcut

## Run and Debug

| Shortcut             | Description        |
|----------------------|--------------------|
| Control + Option + R | 선택하여 코드 실행         |
| Control + Control    | 코드 실행              |
| Control + Option + D | 선택하여 코드 디버깅        |
| Control + R          | 현재 IDE에 지정된 코드 실행  |
| Control + D          | 현재 IDE에 지정된 코드 디버깅 |
| Option + Enter       | 오류 해결 솔루션 제시       |
| Command + Shift + A  | 모든 액션 검색           |

## Editor

| Shortcut                     | Description                       |
|------------------------------|-----------------------------------|
| Fn + 방향키(위, 아래)              | 페이지 위 혹은 아래로 이동                   |
| Option + Shift + 방향키(위, 아래)  | “라인 단위”로 위 혹은 아래로 이동              |
| Command + Shift + 방향키(위, 아래) | “구문 단위”로 위 혹은 아래로 이동              |
| Command + Shift + 방향키(좌, 우)  | 커서부터 맨 왼쪽 혹은 오른쪽까지 선택             |
| Command + Shift + J          | 라인 합치기                            |
| Command + Backspace          | 라인 한 줄 전체 삭제                      |
| Command + N                  | 현재 코드 화면에서 생성자/getter/setter 자동생성 |
| Control + Option + O         | 사용하지 않는 import 정리                 |
| option + command + L         | 코드 자동정렬                           |
| Control + Tab (+ Shift)      | Editor switcher 실행                |

## Generate

| Shortcut            | Description |
|---------------------|-------------|
| Command + N         | 모든 구성요소 생성  |
| Command + Shift + T | 테스트 클래스 생성  |

## Refactor

| Shortcut             | Description   |
|----------------------|---------------|
| Control + T          | 모든 리팩토링 선택 기능 |
| Shift + F6           | 파일 이름 변경      |
| Command + Option + M | 메소드 추출 분리     |
| Command + Option + C | 정적 상수 분리      |
| Command + Option + F | 필드(객체변수) 분리   |
| Command + Option + V | 지역변수 분리       |
| Command + Option + L | 코드 컨벤션 체크     |
| F2                   | 오류난 곳으로 이동    |
| Option + Enter       | 리팩토링 수정 제안    |

## Bookmark

| Shortcut     | Description     |
|--------------|-----------------|
| F3           | 라인에 북마크 설정/해제   |
| Command + F3 | 북마크 목록 보기       |
| Option + F3  | Mnemonic 북마크 설정 |

## Comment

| Shortcut    | Description |
|-------------|-------------|
| Command + / | 주석 처리       |

## Focus

| Shortcut                     | Description             |
|------------------------------|-------------------------|
| Command + 방향키(좌, 우)          | "라인" 단위로 왼쪽 혹은 오른쪽으로 이동 |
| Command + 방향키(위, 아래)         | 페이지 위 혹은 아래로 이동         |
| Option + 방향키(좌, 우)           | "단어" 단위로 왼쪽 혹은 오른쪽으로 이동 |
| Option + 방향키(위, 아래)          | 포커스 확장 및 축소             |
| Option + Option + 방향키(위, 아래) | 멀티 포커스(다중 라인 편집시)       |

## Finder

| Shortcut              | Description                 |
|-----------------------|-----------------------------|
| Shift + Shift         | 전체 검색                       |
| Command + Option + O  | 메소드 검색                      |
| Command + Shift + A   | 액션 검색                       |
| Command + F           | 현재 파일에서 검색                  |
| Command + Shift + F   | 전체에서 검색                     |
| Command + R           | 현재 파일에서 교체                  |
| Command + Shift + R   | 전체에서 교체                     |
| Command + E           | 최근 열었던 파일 목록                |
| Command + Shift + E   | 최근 수정한 파일 목록                |
| Command + B           | 해당 인터페이스/클래스/변수의 선언된 곳으로 이동 |
| Option + Command + B  | 해당 인터페이스/클래스/변수가 구현된 곳 알려줌  |
| Alt + F7              | 해당 인터페이스/클래스/변수의 사용된 곳 알려줌  |
| Command + Control + G | 일치하는 단어 전체 선택               |
| Command + 방향키(위)      | 패키지 또는 파일 경로 검색             |

## Diagram

| Shortcut             | Description   |
|----------------------|---------------|
| Option + Command + U | Class Diagram |

## Supports Window

| Shortcut     | Description          |
|--------------|----------------------|
| Option + F12 | Terminal 창 실행        |
| Command + 1  | Project 창 실행         |
| Command + 2  | Bookmarks 창 실행       |
| Command + 4  | Run 창 실행             |
| Command + 5  | Debug 창 실행           |
| Command + 6  | Problem 창 실행         |
| Command + 7  | Structure 창 실행       |
| Command + 8  | Services 창 실행        |
| Command + 9  | Version Control 창 실행 |

--- 

# IntelliJ Tips

## Auto Code Folding 셋팅하기

### Enable Code Folding

Settings > Editor > General > Code Folding > Check "Code Folding을 원하는 요소"

### Disable Code Folding

Settings > Editor > General > Code Folding > Uncheck "Code Unfolding을 원하는 요소"

## Single name import 사용하기 (같은 계층의 import가 많아지면 *로 변경하는 것 방지)

### Use single name import in "Top level symbols"

Settings > Editor > Code Style > Kotlin(사용 언어 선택) > Imports > Top level symbols > Use single name import

### Use single name import in "Java statics and Enum members"

Settings > Editor > Code Style > Kotlin(사용 언어 선택) > Imports > Java statics and Enum members > Use single name import

## Auto Optimize imports 셋팅

Settings > Editor > General > Auto Import > Java(사용 언어 선택) > Check "Optimize imports on the fly"

## 새로운 파일 탭을 열면 기존 파일 탭이 대체되어 닫히는 경우, 닫히지 않게 하는 방법

Settings > Editor > General > Editor Tabs > Uncheck "Enable Preview Tab"

## IntelliJ에서 Pull Request 환경 셋팅

### 1. GitHub Account 셋팅

#### 1.1. Github.com

Settings > Version Control > Github > Add(Github Account) > Log In with token > Generate (Token) > Add Account

#### 1.2. Github Enterprise

Settings > Version Control > Github > Add(Github Account) > Log In to Github Enterprise > Generate (Token) > Add Account

### 2. Pull Request 플러그인 사용

Shift + Shift > Pull Request

---

# IntelliJ Live Template

## Live Template 설정 방법

---

# IntelliJ Plugin

### [.ignore : gitignore 파일 생성](https://plugins.jetbrains.com/plugin/7495--ignore)

### [Atom Material Icons : IDE의 Icon을 Atom 스타일 만듦](https://plugins.jetbrains.com/plugin/10044-atom-material-icons)

### [CamelCase : Camel Case로 변경](https://plugins.jetbrains.com/plugin/7160-camelcase)

### [Code Screenshots : 클립보드에 Code 스크린샷 생성](https://plugins.jetbrains.com/plugin/9406-code-screenshots)

### [CodeMetrics : Code 복잡도 분석](https://plugins.jetbrains.com/plugin/12159-codemetrics)

### [GitHub Copilot : 생산성을 위한 코드 추천](https://plugins.jetbrains.com/plugin/17718-github-copilot)

### [GitToolBox : Git과 관련된 Tool box](https://plugins.jetbrains.com/plugin/7499-gittoolbox)

### [RestfulBox : 구현한 API Spec Requester](https://plugins.jetbrains.com/plugin/14723-restfulbox)
