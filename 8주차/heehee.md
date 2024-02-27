# TCP 3-way handshake

## 목적
TCP의 3-way handshake는 연결을 확립하기 위한 프로세스로, 클라이언트와 서버 간의 신뢰성있는 양방향 통신을 구축하기 위함입니다.

## TCP 플래그(코드 비트)
- SYN (synchronize sequence number) : TCP 연결 설정을 위한 플래그
- ACK (acknowledgement) : 데이터 응답을 확인하기 위한 플래그
- FIN (finish) : TCP 연결을 종료하기 위한 플래그

## 동작과정
![tcp-3way-handshake](https://github.com/CHZZK-Study/cs-study/assets/84820008/669ce95a-b670-4216-b9fb-6389332bda69)

### 1. 클라이언트 -> 서버 : 연결 확립 요청
- SYN = 1 : 클라이언트 -> 서버 연결을 확립하기 위해 클라이언트가 서버에게 요청 

### 2. 서버 -> 클라이언트 : 수락 + 연결 확립 요청
- ACK = 1 : 클라이언트의 요청을 수락
- SYN = 1 : 서버 -> 클라이언트 연결을 확립하기 위해 서버가 클라이언트에게 요청

### 3. 클라이언트 -> 서버 : 수락
- ACK = 1 : 서버의 요청을 수락

# TCP 4-way handshake

## 목적
TCP의 4-way handshake는 TCP 연결 확립 후, 연결을 종료하기 위한 프로세스

## 동작과정
![tcp-4way-handshake](https://github.com/CHZZK-Study/cs-study/assets/84820008/c60e7fc3-bfc5-4ddb-a306-ac2c6ce070bd)

### 1. 클라이언트 -> 서버 : 연결 종료 요청
- FIN = 1 : 클라이언트 -> 서버 연결을 종료하기 위해 클라이언트가 서버에게 요청 

### 2. 서버 -> 클라이언트 : 수락
- ACK = 1 : 클라이언트의 요청을 수락

### 3. 서버 -> 클라이언트 : 연결 종료 요청
- FIN = 1 : 서버 -> 클라이언트 연결을 종료하기 서버가 클라이언트에게 요청

### 4. 클라이언트 -> 서버 : 수락
- ACK = 1 : 서버의 요청을 수락

### Time wait이 있는 이유는?
- 연결의 정확한 종료 보장 : 네트워크 상의 이전 패킷이 지연되거나 재전송되는 경우를 대비하기 위함이다.