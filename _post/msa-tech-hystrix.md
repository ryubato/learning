# Hystrix

</br>

## 개요

하나의 시스템을 여러개의 서비스로 나눠서 호출하는 마이크로 서비스 아키텍쳐 패턴에서 어느 서비스가 지연 되거나
장애가 발생하는 경우 서비스 호출 관계에 따라 그 영향이 다른 서비스로 전파 된다.
`Hystrix`는 지연과 장애에 대한 내성을 가진 분산 서비스 환경을 만들어 주는 라이브러리이다.

## 역할

- 지연과 장애에 대한 내성
  - Circuit Breaker
  
- 실시간 모니터링 및 설정 변경
  - Hystrix Dashboard
  
- Concurrency
  - Parallel Execution, Caching, Collapsing, Timeout, Thread Pool, Queuing ...

</br>

## 참고

개요: https://github.com/Netflix/Hystrix

동작방식: https://github.com/Netflix/Hystrix/wiki/How-it-Works

개요: https://medium.com/@goinhacker/hystrix-500452f4fae2

적용사례: http://woowabros.github.io/experience/2017/08/21/hystrix-tunning.html
