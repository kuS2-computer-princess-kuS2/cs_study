### [TCP(Transmission Control Protocol)]
* 인터넷상에서 데이터를 메세지의 형태로 보내기 위해 IP와 함께 사용하는 전송 프로토콜
* TCP는 애플리케이션에게 **신뢰적이고 연결지향성** 서비스를 제공
* 일반적으로 TCP와 IP는 함께 사용되며 IP: 전송, TCP: 패킷의 추적 및 관리
* TCP는 handshaking을 통해 신뢰적인 전송을 보장하고 데이터의 흐름제어와 혼잡제어를 수행
  * TCP의 **속도는 느림**


___

### [3-way Handshake (접속)]
* TCP 통신을 이용하여 데이터를 전송하기 위해 네트워크 연결을 설정하는 과정
* 양쪽 모두 데이터를 전송할 준비가 되었다는 것을 보장하고, 실제로 데이터 전달이 시작하기 전에 한 쪽이 다른 쪽이 준비되었음을 확인
* 데이터를 전송하기 전에 먼저 정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/8b946fa0-6776-494f-81de-e0b206960a9c)

1. Client -> Server : **SYN** 패킷 전송
    * **Client : SYN_SENT**
    * **Server : Wait for Client**
2. Server -> Client : **ACK, SYN** 패킷 전송
    * Client : SYN_SENT
    * **Server : SYN_RECEIVED**
3. Client -> Server : **ACK** 패킷 전송
    * **Client : ESTABLISHED**
    * **Server : ESTABLISHED**

* SYN(Synchronization) : 연결 확인을 위해 보내는 무작위 숫자값
* ACK(Acknowledgement) : Client 혹은 Server로부터 받은 SYN에 1을 더해 SYN을 잘 받았음을 알림

* 3번의 세그먼트 교환이 이뤄지지 않으면, 메시지를 전송하지 않음


___

### [4-Way Handshake(연결 해제)]
* 연결을 해제 (Connecntion Termination)하는 과정

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/3f73357c-31e1-4e70-b951-b2981c394547)

1. Client -> Server : **FIN** 패킷 전송
    * **Client : FIN_WAIT**
    * **Server : ESTABLISHED**
2. Server -> Client : **ACK** 패킷 전송
    * Client : FIN_WAIT
    * **Server : CLOSE_WAIT** (자신의 데이터 전송이 끝날 때까지 기다림)
3. Server -> Client : **FIN** 패킷 전송 (서버 전송 끝나면)
    * Client : FIN_WAIT
    * **Server : LAST_ACK**
4. Client -> Server : **ACK** 패킷 전송
    * **Client : TIME-WAIT** -> 세션 만료 후 **CLOSE**
    * **Server : ESTABLISHED**

* FIN (finish) : 세션을 종료시키는데 사용되며, 더 이상 보낼 데이터가 없음을 나타냄

* Server에서 FIN 플래그를 전송하기 전에 전송한 패킷이 라우 지연이나 패킷 유실로 인한 재전송 등으로 인해 FIN 패킷보다 늦게 도착하는 상황이 발생한다면?
  * **TIME_WAIT**: 이러한 현상에 대비하여 Client는 Server로부터 FIN 플래그를 수신하더라도 일정시간(Default: 240sec)동안 세션을 남겨 놓고 잉여 패킷을 기다림
* 초기 Sequence Number인 ISN을 0부터 시작하지 않고 난수를 생성해서 설정하는 이유?
  * 서버는 패킷의 SYN을 보고 패킷을 구분 -> 난수가 아닌 순처적인 Number가 전송된다면 이전의 Connection으로부터 오는 패킷으로 인식할 수 있음
