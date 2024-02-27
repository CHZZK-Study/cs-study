# HTTP & HTTPS

## HTTP(Hypertext Transfer Protocol)란?

### 정의

클라이언트와 서버 간 통신을 위한 통신 규칙 프로토콜입니다.

### 동작과정

![http](https://github.com/CHZZK-Study/cs-study/assets/84820008/429c46a0-239f-4f1e-a689-60d38f90fb18)

1. connect : 클라이언트가 원하는 서버에 접속합니다.
2. request : 클라이언트가 접속한 서버에 HTTP 요청을 전송합니다.
3. response : 서버가 HTTP 응답으로 응답한 후, 서버와 클라이언트 연결을 끊습니다.(stateless)

### HTTP Request(요청)

HTTP Method 종류
- GET : 특정한 리소스를 가져오도록 하는 메서드
- POST : 대상 리소스에게 리퀘스트 본문을 해당 리소스의 시멘틱에 따라 처리하도록 요청하는 메서드
- PUT : 리소스 수정 메서드
- DELETE : 리소스 삭제 메서드

### HTTP Response(응답)

상태 코드 종류
- 200번대 : 성공상태를 의미 <br/>
ex. 200 Ok : 서버가 요청을 제대로 처리했음

- 300번대 : 요청에 대한 추가적인 처리가 필요하다는 의미<br/>
ex. 301 Moved Permanently : 요청한 리소스가 영구적으로 새로운 위치로 이동했음

- 400번대 : 클라이언트의 요청이 잘못되었음을 의미<br/>
ex1. 400 Bad Request :서버가 request 구문을 인식하지 못했음
ex2. 404 Not Found : 해당 페이지를 찾을 수 없는 경우

- 500번대 : 서버때문에 발생하는 오류<br/> 
ex. 505 HTTP Version Not Supported : 요청한 HTTP 프로토콜 버전을 서버가 지원하지 않는 경우

### HTTP 장점

- 불특정 다수를 대상으로 하는 서비스에 적합합니다.
- 무상태(stateless = 클라이언트와 서버간의 연결을 끊음) 프로토콜이기 때문에 웹 서비스를 많이 사용하더라도 접속 유지는 최소한으로 할 수 있어 더 많은 유저의 요청을 처리할 수 있습니다.

### HTTP 단점

- 무상태 프로토콜이기 때문에 클라이언트의 이전 상태를 알 수 없습니다. -> 해결책 : Cookie
- 데이터를 평문(=일반 텍스트)으로 전송하기 때문에 보안에 취약합니다. -> 해결책 : HTTPS

## HTTPS(Hypertext Transfer Protocol Secure)란?

### 정의

웹 통신 프로토콜인 HTTP에 데이터 암호화가 추가된 프로토콜입니다.

### HTTP와의 차이점

- HTTP는 80번 포트를 사용하지만, HTTPS는 443번 포트를 사용합니다.
- HTTP를 사용하여 통신을 수행하면 홈페이지 URL이 'http://'로 시작하는 반면, HTTPS 프로토콜을 사용하면 'https://'로 시작합니다.
- 통신하는 과정에서 HTTP는 전송내용을 평문으로, HTTPS는 전송 내용을 암호화하여 전송합니다.