# Testing

</br>

## spring boot test module

`spring-boot-test` : 테스트를 위한 핵심 아이템들을 포함

`spring-boot-test-autoconfigure` : auto-configuration 테스트 지원

대부분의 개발자들은 `spring-boot-test`, `spring-boot-test-autoconfigure` 두 가지 모듈이 다 포함 된 `spring-boot-starter-test`를 사용한다.

</br>

## spring-boot-starter-test

`spring-boot-starter-test`에는 테스트 코드 작성 시 공통적으로 사용하는 다음의 라이브러리들이 포함되어 있다.

* JUnit: 사실상 표준인 java unit test framework
* Spring Test & Spring Boot Test: Spring Boot Application 의 integration test 를 지원하는 도구
* AssertJ: JUnit 보다 직관적인 Assert와 풍부한 Assertion을 제공
* Hamcrest: Matcher 라이브러리, 테스트 표현식을 자연스러운 문장으로 만들 수 있게 도와줌, assertEquals 보다 assertThat 사용 권장
* Mockito: java mocking framework
* JSONassert: JSON assertion library
* JsonPath: JSON을 위한 XPath

</br>

## Testing Spring Boot Application

Spring Boot application is a Spring `ApplicationContext`

External properties, logging, and other features of Spring Boot are installed in the context by default only if you use `SpringApplication` to create it.

Spring Boot는 `spring-test`, `@ContextConfiguration`을 대체하는 `@SpringBootTest`를 제공

