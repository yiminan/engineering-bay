# guide-git.md

### checkout

| Shortcut                   | Description |
|----------------------------|-------------|
| `git checkout -b <branch>` | 새로운 브랜치 생성  |
| `git checkout <branch>`    | 해당 브랜치로 이동  |
| `git checkout <commit>`    | 해당 커밋으로 이동  |

### commit

| Shortcut                       | Description             |
|--------------------------------|-------------------------|
| `git add <file>`               | 파일 스테이징                 |
| `git add .`                    | 모든 파일 스테이징              |
| `git commit -m <message>`      | 커밋 메시지 작성               |
| `git commit --amend`           | 이전 커밋 메시지 수정            |
| `git commit --amend --no-edit` | 이전 커밋 메시지 수정(메시지 수정 없이) |

### push

| Shortcut                      | Description                  |
|-------------------------------|------------------------------|
| `git push -u origin <branch>` | 원격 저장소에 브랜치 생성               |
| `git push`                    | 원격 저장소에 푸시                   |
| `git push --force`            | 원격 저장소에 강제 푸시 기존 커밋히스토리 덮어쓰기 |

### pull

| Shortcut   | Description |
|------------|-------------|
| `git pull` | 원격 저장소에서 풀  |

### status

| Shortcut     | Description |
|--------------|-------------|
| `git status` | 현재 상태 보기    |

### rebase

| Shortcut                     | Description |
|------------------------------|-------------|
| `git rebase <branch>`        | 브랜치 리베이스    |
| `git rebase --continue`      | 리베이스 계속     |
| `git rebase --abort`         | 리베이스 취소     |
| `git rebase --skip`          | 리베이스 건너뛰기   |
| `git rebase -i <commit>`     | 커밋 합치기      |
| `git rebase -i HEAD~<count>` | 커밋 합치기      |
