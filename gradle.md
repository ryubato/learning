# Gradle

## 참고

http://woowabros.github.io/tools/2019/04/30/gradle-kotlin-dsl.html

https://docs.spring.io/spring-boot/docs/current/gradle-plugin/reference/html/

https://plugins.gradle.org/plugin/org.springframework.boot

https://plugins.gradle.org/plugin/io.spring.dependency-management

## 빌드 자동화 도구

- 의존성 라이브러리 다운로드
- 컴파일: 소스코드 -> 바이너리코드
- 테스트 실행
- 바이너리코드 패키징
- 배포

## maven 보다 gradle이 좋은 이유

멀티 프로젝트(모듈), wrapper 지원

### wrapper

빌드도구를 실행할 수 있는 래퍼 바이너리 파일(gradle-wrapper.jar)과 이를 실행할 수 있는 스크립트를 함께 등록하여 관리하는 방식, 빌드할때 배포본에는 포함되지 않는다.

wrapper 가 없는 경우 각 개발자가 자신의 환경에 빌드도구를 설치하여 실행환경 설정을 하고 관리했어야했다.

wrapper를 사용하면 모든 개발자에게 일관된 빌드 환경을 제공하여 재현 가능하고 유지보수 가능한 빌드에 대한 자동화를 제공한다.

## groovy dsl, kotlin dsl

xxxx.gradle : groovy dsl
xxxx.gradle.kts : kotlin dsl

표현이 자유로운 groovy

```groovy
# build.gralde

dependencies {
  testImplementation 'org.codehaus.groovy:groovy'
  testImplementation "org.codehaus.groovy:groovy-test"
  testImplementation "org.spockframework:spock-core:$spockVersion"
  testImplementation("org.spockframework:spock-spring:$spockVersion")
}
```

표현에 제약이 있는 kotlin (다수의 사람들과 사용할때는 제약이 있어한다는 의견에 동의한다.)

```kotlin
# build.gradle.kts

dependencies {
  testImplementation("org.codehaus.groovy:groovy")
  testImplementation("org.codehaus.groovy:groovy-test")
  testImplementation("org.spockframework:spock-core:$spockVersion")
  testImplementation("org.spockframework:spock-spring:$spockVersion")
}
```

kotlin dsl 특징 중 오류코드 강조가 맘에 든다.

## Spring Boot

### spring boot plugin 추가

Using the plugins DSL:

```groovy
plugins {
  id "org.springframework.boot" version "2.1.9.RELEASE"
}
```

Using legacy plugin application:

```groovy
buildscript {
  repositories {
    maven {
      url "https://plugins.gradle.org/m2/"
    }
  }
  dependencies {
    classpath "org.springframework.boot:spring-boot-gradle-plugin:2.1.9.RELEASE"
  }
}

apply plugin: "org.springframework.boot"
```

### Spring Boot's Dependency Management Plugin

Spring Boot의 플러그인을 해당 프로젝트에 적용하지 않고도 프로젝트에서 Spring Boot의 종속성 관리를 사용할 수 있습니다. SpringBootPlugin 클래스는 그룹 ID, 이슈 ID 또는 버전을 몰라도 bom을 가져 오는 데 사용할 수있는 BOM_COORDINATES 상수를 제공합니다.

```groovy
plugins {
    java
    id("org.springframework.boot") version "2.1.9.RELEASE" apply false
    id("io.spring.dependency-management") version "1.0.8.RELEASE"
}

dependencyManagement {
    imports {
        mavenBom(org.springframework.boot.gradle.plugin.SpringBootPlugin.BOM_COORDINATES)
    }
}
```

```groovy
apply plugin: 'io.spring.dependency-management'

dependencyManagement {
    imports {
        mavenBom org.springframework.boot.gradle.plugin.SpringBootPlugin.BOM_COORDINATES
    }
}
```

참고

https://docs.spring.io/spring-boot/docs/current/gradle-plugin/reference/html/

https://plugins.gradle.org/plugin/io.spring.dependency-management
