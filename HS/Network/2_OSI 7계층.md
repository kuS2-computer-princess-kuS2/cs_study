![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/ecf2729f-dc96-473f-a34d-3e9f2d2eb2ef)

### [물리계층(Physical Layer)]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/cbbde9a5-dd92-4655-885f-ef2e93b49fa9)

- 데이터를 전기 신호로 바꾸어주는 계층 (단위: bit)
- 주로 전기적, 기계적, 기능적인 특성을 이용해 데이터 전송
- 데이터는 0과 1의 비트열, 즉 On/Off의 전기적 신호 상태로 이루어져 해당 계층은 단지 데이터를 전달함
- 데이터 전달의 역할만을 할 뿐이라 알고리즘, 오류제어의 기능이 없음
- 장비: 케이블, 리피터, 허브

---

### [데이터링크 계층(Data-Link Layer)]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/565a3f14-c624-40d0-bb0e-5914f0ca4876)

- 데이터의 물리적인 전송과 에러 검출, 흐름 제어를 담당하는 계층
- 오류 발생시 재전송 등을 통해 인접한 두 장치 간의 신뢰성 있는 정보 전송을 담당(Point-To-Point 전송)
- MAC 주소를 통해서 통신
- 데이터 단위: Frame
- 장비: 브리지, 스위치

---

### [네트워크 계층(Network Layer)]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/a5c861b9-553c-46b0-b017-cb14ea807eea)

- 데이터를 목적지까지 빠르게 전송하기 위한 계층 (라우팅)
- 전송 계층의 세그먼트를 송신자의 장치에서 더 작은 단위인 패킷으로 세분화 -> 수신 장치에서 패킷 다시 조립
- 컴퓨터에게 데이터를 전송할 주소를 가지고 있어서 통신가능(=IP 주소: 네트워크 계층 헤더)
- 데이터 단위: Packet
- 장비: 라우터, L3 스위치

  \*\* 라우팅: 데이터가 표적에 도달하기 위한 최상의 물리적 경로를 찾는 것

---

### [전송 계층(Transport Layer)]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/3b2987ff-33a3-4893-b69b-85bf7151ea28)

- 최종 수신 프로세스로 종단 간 신뢰성 있고 정확한 데이터 전송을 담당하는 계층
- 송신자와 수신자 간의 신뢰성있고 효율적인 데이터를 전송하기 위하여 **오류검출 및 복구, 흐름제어와 중복검사** 등을 수행
- 데이터 전송을 위해서 Port 번호를 사용 (대표적인 프로토콜: TCP, UDP)
- 데이터 단위: Segment

---

### [세션 계층(Session Layer)]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/16778018-9b21-4ad8-80c0-0881fc9675a1)

- 통신 장치 간 상호작용 및 동기화를 하기 위해 세션을 만드는 계층
- 교환되고 있는 모든 데이터를 전송할 수 있도록 충분히 오랫동안 세션을 개방한 다음 리소스를 낭비하지 않기 위해 세션을 즉시 닫을 수 있도록 보장함
- 연결 세션에서 데이터 교환과 에러 발생 시의 복구 관리

\*\* 세션: 통신이 시작되어 종료될 때까지의 시간

---

### [표현 계층 (Presentation Layer)]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/97f7f8f9-1ea6-41d6-bde9-40bae68b039b)

- 데이터의 표현 형식(Format)을 정의하는 계층
- 기능
  - 송신자에서 온 데이터를 해석하기 위한 응용계층 데이터의 **변환** (서로 다른 인코딩 방식 해결 등)
  - 전송할 데이터의 양을 최소화함으로써 통신의 속도와 효율을 높이는 데이터 **압축**
  - 데이터의 **암호화**와 복호화

---

### [응용 계층(Application Layer)]

![image](https://github.com/kuS2-computer-princess-kuS2/cs_study/assets/81477543/1a65a65b-a14f-4d6d-b9ac-f597d02693b9)

- 사용자와 가장 밀접한 계층, 인터페이스 역할
- 응용 프로세스 간의 정보 교환을 담당
- 소프트웨어가 사용자에게 의미 있는 데이터를 제공하기 위해 의존하는 프로토콜과 데이터를 조작
- 대표적인 프로토콜: HTTP, SMTP
