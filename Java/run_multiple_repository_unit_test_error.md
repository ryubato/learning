### 문제

각각의 테스트 케이스가 JdbcTemplate을 사용하여 테스트 데이터를 Insert 하는 경우, 첫 번째 테스트 케이스의 Insert 만 동작하는 현상

### 해결

```java
@DirtiesContext(classMode = DirtiesContext.ClassMode.AFTER_EACH_TEST_METHOD)
public class RepositoryTest() {
```
