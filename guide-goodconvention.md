# guide-goodconvention.md

## Database

- DB DDL에서 Column, Table의 comment 작성 필수
- FK는 column naming을 prefix: ‘ref_’를 적용
    - ex) ref_user_id, ref_payment_id

## Application

- Spring Cloud Config를 사용하여 설정 관리
- JPA Entity Class를 생성할 때 suffix로 '~Entity'를 붙임
    - ex) UserEntity, PaymentEntity

## Pull Request

- PR의 제목은 `[JIRA-KEY] PR 제목` 형식으로 작성
    - ex) `[ABC-1234] 프레임워크 패치 버전 업데이트`
