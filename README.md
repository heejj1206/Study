# OSI 7 Layer

[작성자: 노희재]


💡 OSI 7 Layer 는 파면 팔수록 엄청난 양의 지식이 필요합니다.

이번 발표는 OSI 7 Layer 에 관해 처음 듣는 분들이 타켓이기 때문에

핵심이라고 생각한 부분들만 추려내어 간략하게 정리했습니다.

후에 이건 뭐고 저건 뭐지? 🤔 같은 궁금증이 생긴다면 더 찾아보시는 것을 추천합니다.

각 계층에 대한 설명을 하기 전에,

우선 OSI 7 Layer 의 모델을 이미지로 만들어봤습니다.

![스크린샷 2022-01-10 오전 1.08.44.png](OSI%207%20Layer%20e67eb9722fc34b56868d2d9cabced99b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-01-10_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_1.08.44.png)

이렇게 7가지 계층으로 이루어져 있지만

많은 사람들이 5,6 계층인 Presentation Layer, Application Layer 는 제외하고 설명하는데요

그 이유는, 현대의 인터넷은 사실 OSI 모델이 아니라 TCP/IP 모델을 따르고 있기 때문입니다.

![스크린샷 2022-01-10 오전 1.10.52.png](OSI%207%20Layer%20e67eb9722fc34b56868d2d9cabced99b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-01-10_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_1.10.52.png)

각 모델이 이러한 모습으로 구성되어 있습니다.

요즘은 Updated 모델이 더 많이 사용되기 때문에

5,6 계층은 제외하고 설명해보도록 하겠습니다.

# 1. 물리 계층 (Physical Layer)

- encoding 과 decoding 이 이루어지는 계층

(예를 들어, 0101 데이터를 보내려 한다면

0101 이라는 디지털 신호를 아날로그 신호로 바꾸어 보내는 것 = encoding

아날로그 신호를 받아 0101 디지털 신호로 다시 해석하는 것 = decoding)

- 하드웨어적

# 2. 데이터 링크 계층 (Data-link Layer)

- 같은 네트워크에 있는 여러대의 컴퓨터들이 데이터를 주고 받기 위해 필요한 계층

(예를 들어, 여러대의 컴퓨터가 통신 할 때 데이터의 구분을 위해

송신자는 데이터의 앞 뒤에 특정한 비트열을 붙인다

= framing 이라는 작업이며, 이것은 해당 계층에 속하는 작업들 중 하나)

- 순환 중복 검사(CRC) 기반의 오류제어와 흐름제어
- 하드웨어적

# 3. 네트워크 계층 (Network Layer)

- inter-network 속에서 목적지인 컴퓨터로 데이터를 전송하기 위해
    
    routing, forwarding, segmentation 이 이루어지는 계층
    
    (예시, IP 주소를 이용해서 길을 찾는 것 = routing
    
    자신 다음의 라우터에게 데이터를 넘겨주는 것 = forwarding
    
    데이터를 패킷 단위로 분할하는 것 = segmentation)
    
- 소프트웨어적

# 4. 전송 계층 (Transport Layer)

- TCP 혹은 UDP 방식으로 전송이 가능하다
    - TCP - 신뢰성이 있고, 순서가 보존되는 전송 시스템.
            손실되면 안되는 데이터들을 처리할 때 주로 사용 (ex 이메일, 채팅 등)
        
        1. 흐름 제어 - 수신측에 대역폭을 맞춰주는 기능
        2. 오류 제어 - 시퀀스 넘버 기반의 오류 제어 방식 사용 (시퀀스 넘버 누락시 재전송 요청)
        3. 연결 제어 - 3-way Handshaking, 4-way Handshaking 으로 연결을 시작하고 종료한다
    
    - UDP - 신뢰성이 없고, 순서의 보존을 보장해주지 않고 오류 제어를 해주지 않는 전송 시스템.
            때문에 전송 과정에서 데이터 조각이 하나 빠져도 알 수 없지만,
            그만큼 가볍기 때문에 전송이 빨라야 하는 데이터들을 처리할 때 주로 사용
            (ex 게임, 스트리밍 등)
        
- 도착지 컴퓨터의 최종 목적지인 프로세스(실행 중인 프로그램) 까지 데이터가 도달하게 하기 위해 port 번호를 붙이는 계층
    
- 소프트웨어적

# 5. 세션 계층 (Session Layer)

- 넘김

# 6. 표현 계층 (Presentation Layer)

- 넘김

# 7. 응용 계층 (Application Layer)

- 응용 프로세스와 직접 관계하여 응용 서비스(이메일, HTTP 등)를 수행하는 계층
- 소프트웨어적

여기까지가 각 계층에 관한 설명입니다.

그렇다면, 이를 토대로 데이터를 주고 받을 때에는 어떻게 진행되는 걸까요?

![스크린샷 2022-01-10 오전 1.50.25.png](OSI%207%20Layer%20e67eb9722fc34b56868d2d9cabced99b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-01-10_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_1.50.25.png)

A와 B가 데이터를 주고 받을 때에는

이런식의 화살표 방향을 따라 통신이 이루어집니다.

![스크린샷 2022-01-10 오후 10.00.26.png](OSI%207%20Layer%20e67eb9722fc34b56868d2d9cabced99b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-01-10_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_10.00.26.png)

A가 데이터를 보낼 때는 안에 있는 Layer 부터 차근차근 감싸서 전송하고,

B가 데이터를 받았을 때는 이런 모양으로 감싸져있는 상태에서

겉에서부터 하나하나 껍질 까듯 각 계층의 과정을 거쳐

A가 보낸 ‘진짜 데이터’ 를 받아낸다고 생각하면 쉽습니다!




# 👋 마치는 말

저는 네트워크에 관한 지식이 없다보니 이번 발표를 준비하면서 정말 많은 개념들을 훑어보게 되었습니다.

너무 많은 양이 될 것 같아 설명을 생략한 부분들이 꽤 있습니다.

이게 뭐지? 싶은 부분은 꼭! 따로 찾아보시길 바랍니다 :)
