## maven project "group id", "artifact id" 네이밍 가이드

### group Id

프로젝트 접근할 수 있는 고유한 이름, 보통 패키지 네이밍룰(도메인 뒤집기)를 따른다.
ex) org.apache.maven

group id 에 프로젝트 구조를 표현하는 것이 좋다. 현 프로젝트가 멀티 프로젝트가 된 경우, 새로운 식별자를 부모의 group id 에 붙이면 된다.
ex) org.apache.maven, org.apache.maven.plugins

### artifact Id

배포되는 jar or war 파일에서 버젼 정보를 뺀 이름, 소문자로 작성
ex) maven, commons-math

### 참고

[Guide to naming conventions on groupId, artifactId and version](https://maven.apache.org/guides/mini/guide-naming-conventions.html)
