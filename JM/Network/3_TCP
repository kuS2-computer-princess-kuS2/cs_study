# TCP(Transmission Control Protocol)란?

---

OSI 7계층에서 Transport Layer에 해당하는 전송 프로토콜로 인터넷 상에서 데이터를 메시지의 형태로 보내기 위해 IP와 함께 사용하는 프로토콜이다. 

- 애플리케이션 간의 통신을 제공
- 애플리케이션에 신뢰적이고 연결지향성 서비스를 제공
    - 신뢰적 정소를 보장하기 위해 handshaking을 한다
    - 흐름 제어 및 혼잡 제어를 통해 높은 신뢰성을 보장한다.
- 3-way handshake를 통해 연결을 설정하고 4-way handshake를 통해 연결을 해제한다.

# TCP 3 way handshake & 4 way handshake

---

### TCP 3 way handshake

- TCP의 **연결을 초기화**할 때 사용한다.
- 데이터를 전송하기 전에 정확한 전송을 보장하기 위해 상대방의 컴퓨터와 사전에 세션을 수립하는 과정
- 과정
    1. Client가 Server에 접속을 요청하는 **SYN 패킷을 보낸다**. 이때, Client는 SYN을 보내고 SYN/ACK 응답을 기다리는 SYN_SENT 상태가 된다
    2. Server는 SYN 요청을 받고 Client에게 **요청을 수락**한다는 **ACK와 SYN flag가 설정된 패킷을 발송**하고 Client가 다시 ACK로 응답하길 기다린다. 이때 Server는 SYN_RECEIVED 상태가 된다. 
    3. Client는 Server에게 **ACK를 보내고** 이후는 연결이 되어 데이터를 송수신할 수 있더. 이때 Server는 **ESTABLISHED** 상태가 된다. 

### TCP 4 way handshake

- **세션을 종료**할 때 사용한다
- 과정
    1. Client가 연결을 종료하겠다는 **FIN 플래그를 전송**한다.
    2. Server는 **확인메시지(ACK)**를 보내고 **자신의 통신이 끝날때까지 기다린다.**
        - 서버에서 FIN을 전송하기 전, 이때 지연이나 유실로 인해 패킷이 도착한다면? → 패킷도착을 기다리고 해당 패킷을 Drop시키고 데이터는 유실된다 : 해당 상태가 TIME_WAIT 상태이다.
    3. Server가 통신이 끝나면 연결이 종료되었다고 Client에게 **FIN 플래그를 전송**한다.
    4. Client가 확인했다는 **ACK 패킷을 전송**한다.
