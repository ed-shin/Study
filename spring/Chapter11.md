---
title: Web Socket
desc: Study/Spring
---

# Web Socket
- HTML의 상호 작용의 한계를 극복하기 위한 프로토콜
- TCP/IP 연결 기반에 초기 핸드쉐이크에는 HTTP를 사용하므로 HTTP(80)/HTTPS(443) 포트를 이용할 수 있음

```java
@Configuration
@EnableWebSocket
public class WebSocketConfig implements WebSocketConfigurer {
    @Override
    public void registerWebSocketHandlers(WebSocketHandlerRegistry registry) {
        registry.addHandler(echoHandler(), "/echo");
        //registry.addHandler(echoHandler(), "/echo").withSockJS();  sockJS 사용시
    }

    @Bean
    public EchoHandler() {
        return new EchoHandler();
    }
}

// web socket handler interface를 구현해서 웹소켓 메시징 처리
public class EchoHandler extends TextWebSocketHandler {
    @Override
    public void HandleTextMessage(WebScoketSession session, TextMessage message) throws IOException {
        session.sendMessage(new TextMessage(textMessage.getPayload()));
    }
}
```

---

### 용어
- STOMP(Streaming Text Oriented Messaging Protocol)
    - 텍스트 기반의 메시지 프로토콜의 한 종류로 웹 소켓을 지원한다.
    - 1:N 관계일수도 있고, 메시지를 서버에 저장했다가 클라이언트가 가져가기도 하는 등 메시지를 클라이언트에게 전송하기 위한 기술의 집합
    - 서브 프로토콜로 사용시 원시 웹소켓 사용에 비해 더 풍부한 프로그래밍 모델을 제공
    - 사용자 정의 메시지 프로토콜 및 메시지 형식을 개발할 필요가 없음
    - 웹소켓을 이용한 메시지 핸들링을 보다 쉽게 만들어줌
    - http://minjoon.com/spring-stomp
    - https://supawer0728.github.io/2018/03/30/spring-websocket/

<br>

- Payload
    - 사용에 있어서 전송되는 데이터를 뜻함(전송 행위의 본래 의도를 뜻함)
    - 전송의 목적이 되는 데이터의 일부분으로 헤더와 메타데이터와 같은 데이터는 제외
    - https://ko.wikipedia.org/wiki/%ED%8E%98%EC%9D%B4%EB%A1%9C%EB%93%9C_(%EC%BB%B4%ED%93%A8%ED%8C%85)

<br>

- SockJS
    - WebSocket의 경우 IE10 이상에서 지원하고 있기 때문에 이 문제를 해결하기 위한 방법들 중 하나
    - WebSocket은 브라우저에서 제공되는 라이브러리인 반면 외부 라이브러리 사용
    - IE6 이상부터 지원
    - 서버에서도 웹소켓이 아닌 SockJS Server Side Library 사용
    - 스프링에서 지원 방법이 웹소켓 서버와 거의 동일