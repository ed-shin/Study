# Spring Batch

- 배치 잡
- 태스크릿
- 다중 스레드 스텝
- 병렬 스탭
- 원격 청킹
- 파티셔닝
- https://recordsoflife.tistory.com/54
- https://velog.io/@kihwanyu/Spring-Batch-%EC%A0%95%EB%A6%AC
- https://woowabros.github.io/experience/2020/02/05/springbatch-querydsl.html

# Spring Integration
- Spring Integration 은 스프링 프레임웍의 기능에 Enterprise Integration Pattern 을 지원하는 확장 기능을 제공한다. 스프링 기반 어플리케이션 내에 가벼운 메시징 기반 서비스를 제공하고 선언적 어뎁터를 사용해 외부 시스템과의 통합을 쉽게 해준다. 이런 어뎁터들은 리모팅, 메시징, 스케쥴링과 같이 스프링이 제공하는 기능들을 추상화하고 있다.

Spring Integration 은 스프링 프레임웍의 기본 기능에 Messages, Message Channel, EndPoint 라는 3가지 핵심 컴포넌트를 추가로 제공해 준다.

- https://www.slideshare.net/WangeunLee/spring-integration-47185594


# Spring XD
- 분산 데이터 수집, 실시간 분석, 일괄 처리, 데이터 내보내기를 위해 설계된 확장 가능한 런타임 서비스로 목표는 빅 데이터 애플리케이션의 개발을 단순화하는 것입니다.
- https://projects.spring.io/spring-xd/

# Spring-Webflux
- 함수형 웹 프레임워크, 비동기 API를 위해 설계된 웹 프로그래밍 모델을 제공
- 반응형 stream을 사용하는 프로그래밍

### RxJava vs Webflux
- 일반적으로 JDK8- 기반은 RxJava, JDK8+은 Webflux(Reactor)를 지원한다.
- RxJava의 단점을 수정하고 백엔드 개발에 더 적합하다.
- RxJava는 잘 못 사용하는 경우 메모리 부족을 유발할 가능성이 많다.

