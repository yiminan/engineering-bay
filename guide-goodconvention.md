# guide-goodconvention.md

# Application

## Profile configuration

- Spring Cloud Config를 사용하여 .yml 설정 관리
- Spring Cloud Config Git Repository를 만들어 Profile별 .yml 설정 관리
- 암호화는 KMS를 이용한 cypher text 관리

## Object Naming Convention

- Presentation Layer Object Name
    - ex) UserRouter, PaymentRouter, ...
- Facade Layer Object Name
    - ex) UserFacade, PaymentFacade, ...
- Service Layer Object Name
    - ex) UserService, PaymentService, ...
- Implementation Layer Object Name
    - ex) UserCreator, PaymentUpdater, ...
- Persistence Layer Object Name
    - ex) UserJpaRepository, PaymentJpaRepository, ...

- Servlet -> Presentation DTO
    - ex) UserRequest, PaymentRequest, ...
- Servlet <- Presentation DTO
    - ex) UserResponse, PaymentResponse, ...

- Presentation -> Facade DTO
    - ex) UserData, PaymentData, ...
- Presentation <- Facade DTO
    - ex) UserData, PaymentData, ...

- Presentation -> Service DTO
    - ex) UserCreateData, UserUpdateData, ...
- Presentation <- Service DTO
    - ex) UserCreateResult, UserUpdateResult, ...

- Facade -> Service DTO
    - ex) UserCreateData, UserUpdateData, ...
- Facade <- Service DTO
    - ex) UserCreateResult, UserUpdateResult, ...

- Service -> Implementation DTO
    - ex) UserCreateData, UserUpdateData, ...
- Service <- Implementation DTO
    - ex) UserCreateResult, UserUpdateResult, ...

- Entity Suffix Naming
    - ex) UserEntity, PaymentEntity, ...
- Entity Value Object Suffix Naming
    - ex) UserIdVo, PaymentIdVo, ...

- Client -> Thirdparty RequestBody
    - ex) UserCreateRequestBody, PaymentUpdateRequestBody, ...
- Client <- Thirdparty ResponseBody
    - ex) UserCreateResponseBody, PaymentUpdateResponseBody, ...

# Github

## Pull Request

- PR의 제목은 `[JIRA-KEY] PR 제목` 형식으로 작성
    - ex) `[ABC-1234] 프레임워크 패치 버전 업데이트`
