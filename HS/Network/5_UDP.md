### [UDP(User Datagram Protocol)]
* **비연결형, 신뢰성이 없는** 전송 프로토콜
* OSI 7계층 중 전송계층의 프로토콜
* IP 데이터그램을 캡슐화하여 보내는 방법과 연결 설정을 하지 않고 보내는 방법을 제공


___

### [UDP의 특징]
![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/d55fff0e-2acf-424d-8b58-9cf8483af65d)

* UDP는 흐름제어, 오류제어 또는 손상된 세그먼트의 수신에 대한 재전송 X
  * 내용이 전송 중에 손실 될 수 있고, 전송되는 세그먼트의 순서가 바뀔 수 있음
* 수신자와 송신자 간의 handshaking X 
* 흐름제어를 하지 않기 때문에 전송 속도가 빠름 **(실시간)**
  * 신뢰성보다 전송 속도가 중요한 부문에서 사용
  * EX) 유튜브와 같은 스트리밍 어플리케이션
* 멀티캐스트/ 브로드캐스트 가능 (IPTV)


___

### [UDP checksum]
* 전송된 segment의 **에러를 탐지**하기 위한 것


##### [계산 방법]
* 도착 IP주소, 송신 포트번호, 수신 포트번호, 데이터 길이, payload 등의 데이터들을 16비트 단위로 쪼개서 전부 더함
* 계산한 값에 1의 보수를 취하면 checksum 값
* checksum 값을 송신측에서 checksum 영역에 넣어서 수신 측에 보냄
* 수신 측도 checksum 값을 구해서 송신측에서 보낸 checksum 과 동일한지 확인
* 동일: 에러 X  
<br/>

* 한계: 전송 도중 checksum값이 바뀌거나 데이터가 변형되어도 checksum 값은 변하지 X


___

### [TCP VS UDP]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/fab62825-87b4-4a8c-98ce-2990db511f35)

