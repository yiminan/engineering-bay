# summary-intellij.md

# IntelliJ Shortcut

## Run and Debug

- 선택하여 코드 실행 → Control + Option + R
- 코드 실행 → Control + Control
- 선택하여 코드 디버깅 → Control + Option + D
- 현재 IDE에 지정된 코드 실행 → Control + R
- 현재 IDE에 지정된 코드 디버깅 → Control + D
- 오류 해결 솔루션 제시 → Option + Enter
- 모든 액션 검색 → Command + Shift + A
- 디버깅 중단점 설정/해제 → Command + F8

## Editor

- 페이지 위 혹은 아래로 이동 → Fn + 방향키(위, 아래)
- “라인 단위”로 위 혹은 아래로 이동 → Option + Shift + 방향키(위, 아래)
- “구문 단위”로 위 혹은 아래로 이동 → Command + Shift + 방향키(위, 아래)
- 커서부터 맨 왼쪽 혹은 오른쪽까지 선택 → Command + Shift + 방향키(좌, 우)
- 라인 합치기 → Command + Shift + J
- 라인 한 줄 전체 삭제 → Command + Backspace
- 현재 코드 화면에서 생성자/getter/setter 자동완성 → Command + N
- 사용하지 않는 import 정리 → Control + Option + O
- 코드 자동정렬 → option + command + L
- Editor switcher 실행 → Control + Tab (+ Shift)

## Generate

- 모든 구성요소 생성 → Command + N
- 테스트 클래스 생성 → Command + Shift + T

## Refactor

- 모든 리팩토링 선택 기능 → Control + T
- 파일 이름 변경 → Shift + F6
- 메소드 추출 분리 → Command + Option + M
- 정적 상수 분리 → Command + Option + C
- 필드(객체변수) 분리 → Command + Option + F
- 지역변수 분리 → Command + Option + V
- 코드 컨벤션 체크 → Command + Option + L
- 오류난 곳으로 이동 → F2
- 리팩토링 수정 제안 → Option + Enter

## Comment

- 주석 처리 → Command + /

## Focus

- 라인 맨 왼쪽 혹은 오른쪽으로 이동 → Command + 방향키(좌, 우)
- 단어 맨 왼쪽 혹은 오른쪽으로 이동 → Option + 방향키(좌, 우)
- 포커스 확장 및 축소 → Option + 방향키(위, 아래)
- 멀티 포커스(다중 라인 편집시) → Option + Option + 방향키(위, 아래)

## Finder

- **전체 검색 → Shift + Shift**
    - 메소드 검색 → Command + Option +O
    - 액션 검색 → Command + Shift + A
- 현재 파일에서 검색 → Command + F
    - 전체에서 검색 → Command + Shift + F
- 현재 파일에서 교체 → Command + R
    - 전체에서 교체 → Command + Shift + R
- 최근 열었던 파일 목록 → Command + E
    - 최근 수정한 파일 목록 → Command + Shift + E
- 해당 인터페이스/클래스/변수의 선언된 곳으로 이동 → Command + B
    - 해당 인터페이스/클래스/변수가 구현된 곳 알려줌 → Option + Command + B
    - 해당 인터페이스/클래스/변수의 사용된 곳 알려줌 → Alt + F7
- 일치하는 단어 전체 선택 → Command + Control +G
- 패키지 또는 파일 경로 검색 -> Command + 방향키(위)

## Diagram

- Class Diagram → Option + Command + U

## Terminal

- Terminal 창 실행 → Option + F12

## Git

- Git Window 실행 → Command + 9

--- 

# IntelliJ Settings

## Auto Code Folding 셋팅하기

### Enable Code Folding

Settings > Editor > General > Code Folding > Check "wanted element"

### Disable Code Folding

Settings > Editor > General > Code Folding > Uncheck "wanted element"

## Single name import 사용하기 (같은 계층의 import가 많아지면 *로 변경하는 것 방지)

### Use single name import in "Top level symbols"

Settings > Editor > Code Style > Kotlin(사용 언어 선택) > Imports > Top level symbols > Use single name import

### Use single name import in "Java statics and Enum members"

Settings > Editor > Code Style > Kotlin(사용 언어 선택) > Imports > Java statics and Enum members > Use single name import

## Auto Optimize imports 셋팅

Settings > Editor > General > Auto Import > Java(사용 언어 선택) > Check "Optimize imports on the fly"

## 새로운 파일 탭을 열면 기존 파일 탭이 대체되어 닫히는 경우, 닫히지 않게 하는 방법

Settings > Editor > General > Editor Tabs > Uncheck "Enable Preview Tab"

---

# IntelliJ Live Template

## Live Template 설정 방법

