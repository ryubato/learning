
# Testing

IoC 를 올바르게 사용하면 unit, integration testing 이 수월해진다.

</br>

## Unit Testing

mock objects 를 사용하여 독립된 환경에서 테스트를 할 수 있다.

### Mock Objects

- Environment: `org.springframework.mock.env`
- JNDI: `org.springframework.mock.jndi`
- Servlet API: `org.springframework.mock.web`
- Spring Web Reactive: `org.springframework.mock.http.server.reactive`

</br>

## Integration Testing

- 서버에 배포하거나 다른 인프라와 연결할 필요없이 테스트를 할 수 있는게 중요하다.

### Goals of Integration Testing

