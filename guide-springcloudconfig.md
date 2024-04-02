# guide-springcloudconfig.md

Spring Cloud Config는 애플리케이션의 설정 정보를 외부 시스템에서 관리할 수 있게 해주는 도구입니다.  
이를 통해 애플리케이션의 설정을 중앙에서 관리하고, 변경 사항을 쉽게 배포할 수 있습니다.
Spring Boot에서 Cloud Config를 사용하는 방법은 아래와 같은 단계로 구성됩니다.

### 1. Spring Cloud Config Server 설정 (실제 서버 생성)

먼저, Spring Cloud Config Server를 설정해야 합니다. 이 서버는 구성 설정 파일을 호스팅하며, 클라이언트 애플리케이션에게 설정 정보를 제공합니다.

1. **의존성 추가**: `pom.xml` 또는 `build.gradle` 파일에 Spring Cloud Config Server 의존성을 추가합니다.

    - Maven 예시:
      ```xml
      <dependency>
          <groupId>org.springframework.cloud</groupId>
          <artifactId>spring-cloud-config-server</artifactId>
      </dependency>
      ```

    - Gradle 예시:
      ```gradle
      implementation 'org.springframework.cloud:spring-cloud-config-server'
      ```

2. **애플리케이션 클래스에 어노테이션 추가**: Spring Boot 애플리케이션 클래스에 `@EnableConfigServer` 어노테이션을 추가하여, 애플리케이션을 Config Server로 활성화합니다.

   ```java
   @EnableConfigServer
   @SpringBootApplication
   public class ConfigServerApplication {
       public static void main(String[] args) {
           SpringApplication.run(ConfigServerApplication.class, args);
       }
   }
   ```

3. **application.properties 또는 application.yml 설정**: Config Server가 설정 파일을 어디에서 찾을지 지정합니다. 일반적으로 Git 저장소를 사용하지만, 파일 시스템을
   사용할 수도 있습니다.

    - Git 저장소 사용 예시:
      ```yml
      spring.cloud.config.server.git.uri=git://your-repository-url
      spring.cloud.config.server.git.clone-on-start=true
      ```

### 2. Spring Cloud Config Client 설정 (사용)

이제 클라이언트 측(Spring Boot 애플리케이션)에서 Config Server에 연결하여 설정 정보를 가져오는 방법을 설정합니다.

1. **의존성 추가**: 클라이언트 애플리케이션의 `pom.xml` 또는 `build.gradle` 파일에 Spring Cloud Config Client 의존성을 추가합니다.

    - Maven 예시:
      ```xml
      <dependency>
          <groupId>org.springframework.cloud</groupId>
          <artifactId>spring-cloud-starter-config</artifactId>
      </dependency>
      ```

    - Gradle 예시:
      ```gradle
      implementation 'org.springframework.cloud:spring-cloud-starter-config'
      ```

2. **bootstrap.properties 또는 bootstrap.yml 설정**: 클라이언트 애플리케이션의 `src/main/resources` 디렉토리에 `bootstrap.properties`
   또는 `bootstrap.yml` 파일을 생성하고, Config Server의 위치를 지정합니다.

   ```yml
   spring.cloud.config.uri=http://localhost:8888
   spring.application.name=your-application-name
   spring.profiles.active=your-profile
   ```

   `spring.cloud.config.uri`는 Config Server의 주소를 가리키며, `spring.application.name`과 `spring.profiles.active`는 Config
   Server에서 해당 애플리케이션의 설정을 찾는 데 사용됩니다.

### 3. 설정 변경 적용

설정을 변경할 때는 Config Server에 있는 설정 파일을 업데이트하고, 클라이언트 애플리케이션에서 변경 사항을 적용하기 위해 재시작하거나 `/actuator/refresh` 엔드포인트를 호출합니다(
Actuator 의존성과 `@RefreshScope` 어노테이션이 필요).

이러한 단계를 통해 Spring Boot 애플리케이션에서 Spring Cloud Config를 사용하여 외부 설정 관리를 구현할 수 있습니다.

이 방법은 애플리케이션의 구성을 중앙에서 관리하고, 환경에 따라 다른 설정을 적용할 수 있게 해줍니다.

### 4. Spring Boot 2.4 버전 이후, bootstrap 컨텍스트 활성화

`org.springframework.cloud:spring-cloud-starter-bootstrap` 의존성은 Spring Boot 2.4 버전 이후의 변경사항에 대응하기 위해 필요해졌습니다. Spring
Boot 2.4 버전부터는 `application.properties` 또는 `application.yml` 파일의 로딩 방식이 변경되었으며, 이로 인해 `bootstrap.properties`
또는 `bootstrap.yml` 파일을 사용하는 기존의 방식이 기본적으로 비활성화되었습니다. 이러한 파일은 애플리케이션 컨텍스트가 시작되기 전에 외부 설정을 로드하는 데 사용되며, 주로 Spring Cloud
Config 클라이언트 설정에 사용됩니다.

#### 왜 `spring-cloud-starter-bootstrap`이 필요한가?

Spring Cloud 환경에서는 애플리케이션의 구성 정보가 외부 시스템(예: Spring Cloud Config Server)에 의해 관리될 수 있습니다. 이러한 외부 구성 정보는 애플리케이션 시작 시, 심지어
일부 Spring Boot auto-configuration이 적용되기 전에 로드되어야 합니다. `bootstrap.yml` 또는 `bootstrap.properties`를 통해 이를 구현했으나, Spring
Boot 2.4 이후의 변경사항으로 인해 기본적으로 이 방식이 비활성화되었습니다.

`spring-cloud-starter-bootstrap` 의존성을 추가함으로써, Spring Cloud 애플리케이션은 다시 `bootstrap` 컨텍스트를 활성화할 수 있습니다. 이 컨텍스트는 주 애플리케이션
컨텍스트가 생성되기 전에 생성되며, 여기서 외부 설정 소스(예: Spring Cloud Config Server)에서 구성 정보를 로드합니다.

#### 주요 사용 사례

- **외부 구성 소스에서 설정 로드**: 애플리케이션 시작 전에 Spring Cloud Config Server와 같은 외부 구성 소스에서 설정 정보를 로드해야 하는 경우.
- **암호화된 속성 해독**: 애플리케이션의 구성 정보 중 일부가 암호화되어 있고, 이를 해독하기 위해 시작 시점에 필요한 경우.

#### 사용 방법

`spring-cloud-starter-bootstrap` 의존성을 프로젝트의 `pom.xml` 또는 `build.gradle` 파일에 추가합니다.

- Maven 예시:
  ```xml
  <dependency>
      <groupId>org.springframework.cloud</groupId>
      <artifactId>spring-cloud-starter-bootstrap</artifactId>
  </dependency>
  ```

- Gradle 예시:
  ```gradle
  implementation 'org.springframework.cloud:spring-cloud-starter-bootstrap'
  ```

이 의존성을 추가함으로써, Spring Boot 2.4 이상에서도 `bootstrap` 컨텍스트를 사용하여 외부 구성 정보를 로드할 수 있게 됩니다. 이는 특히 Spring Cloud Config를 사용하는
애플리케이션에서 중요하며, 애플리케이션의 설정 관리를 외부화하여 관리의 유연성을 높일 수 있습니다.
