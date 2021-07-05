# 이론

### OSI 7계층이 어떤 것이 있나?
* 7 응용
    * UI 담당계층, 네트워크 응용 프로그램
    * Device : L7 Switch
    * Protocol : HTTP, FTP, DNS, DHCP
* 6 표현
    * format 담당, 암호화, 복호화
    * Protocol : png, gif, ascii
* 5 세션
    * 통신 관리 담당, 세션의 유지, 종료 등을 담당(TCP/IP 세션을 관리)
    * Protocol : SSL/TLS, NetBIOS
* 4 전송
    * 오류제어, 흐름제어, 분할 재조립, TCP 의 경우 신뢰성 보장
    * Device : L4 Switch
    * PDU : Segment(TCP), Datagram(UDP)
    * Protocol : TCP, UDP
* 3 네트워크
    * 주소부여와 라우팅
    * Device : Router
    * PDU : packet or Datagram
    * Protocol : IP, ICMP, ARP, IPX, Routing Protocol(RIP, EIGRP, OSPF, BGP)
* 2 데이터링크
    * 오류검출, 흐름제어, 직접접근 Network에 관한 제어, MAC Add.
    * Device : Switch, Bridge
    * PDU : Frame
    * Protocol : Ethernet, Tocken ring, RARP, VPN(PPP, PPTP, L2TP)
* 1 물리
    * 전기적, 물리적 정의
    * Device : Hub, Repeater
    * PDU : bit

### TCP/IP 4계층을 설명하고 OSI 7계층의 차이는?
* 4 응용
    * OSI 7계층에서 7,6,5 를 합친 것. network 관점에서는 응용 프로그래머의 역할이므로 묶었음.
* 3 전송
    * TCP/IP 4계층이므로 TCP를 주로 의미. 오류제어, 흐름제어, 신뢰성
* 2 인터넷
    * OSI 7계층에서 network 에 해당. IP 를 주로 의미. 주소부여, routing.
* 1 네트워크 엑세스(네트워크 인터페이스, 링크)
    * OSI 7계층에서 1,2 를 합친 것. H/W Interface 에 관한 파트이므로 묶었음.
*  OSI는 가이드로서, TCP/IP는 계속 실무의 표준으로 쓰임.

### TCP 3-handshake, TCP 4-handshake 에 대해 설명과 왜 shaking 차이가 나는지 설명하시오.

* 3-handshake : TCP 세션 맺을 때 사용
    * Client : SYN
    * Server : SYN+ACK
    * Client : ACK
* 4-handshake : TCP 세션 종료 시 사용
    * Client : FIN
    * Server : ACK(and close-wait)
    * Server : FIN
    * Client : ACK
* 둘 간의 차이는 ~~

### 초기 Sequence Number인 ISN을 0부터 시작하지 않고 난수를 생성해서 설정하는 이유가 무엇인가요?
* Connection을 맺을 때 사용하는 포트(port)는 유한 범위 내에서 사용하고 시간이 지남에 따라 재사용된다. 따라서 두 통신 호스트가 과거에 사용된 포트 번호 쌍을 사용하는 가능성이 존재한다. 서버 측에서는 패킷의 SYN을 보고 패킷을 구분하게 되는데 난수가 아닌 순차적인 number가 전송된다면 이전의 connection으로부터 오는 패킷으로 인식할 수 있다. 이러한 문제가 발생할 가능성을 줄이기 위해서 난수로 ISN을 설정한다.

### Data Encapsulation 에 대해 설명하시오

### 오류 제어 방식에 대해 설명하시오

* 에러검출(CRC, 해밍, BCH), 에러정정(블록코딩(해밍, BCH, LDPC), 비블록(터보, 컨볼루션)), 재전송(FEC, ARQ)
* 재전송(Stop & Wait, Go back N, Selective, Adaptive ARC)
* FEC : 오류정정, CRC : 오류검출, ARQ : 오류 재전송, Hybrid-ARQ : FEC+ARQ 섞은 것

# Network Engineering

### 여러 network topology 에 대해 설명하시오

### TCP UDP 란? 차이는? 둘 간의 헤더도 비교하시오

### Subnetting, Subnet mask, Supernetting, Supernet Mask 에 대해 설명하시오

### 라우터와 스위치, 허브의 차이를 설명해주세요

### Straight Through, cross, rollover cable 에 대해 설명하시오 

### VLAN 과 tagging에 대해 설명하시오

### Gateway 란?

# Protocol

### DHCP 에 대해 설명하시오

### SMTP 에 대해 설명하시오

### DNS 에 대해 설명하시오

### Ethernet 에 대해 설명하시오

### IPv4와 IPv6 차이를 설명하시오

### MAC Address 에 대해 설명하시오

### routing protocol에 대해 설명하시오

# Web

### HTTP가 무엇인지 설명하시오

### HTTP/2에 대해 설명하시오

### HTTPS 와 SSL/TLS에 대해 설명하시오

### HTTP 요청/응답 헤더의 구조를 설명하시오

### HTTP GET과 POST 메서드를 비교/설명하시오

### CORS가 무엇인가요?

### 쿠키와 세션에 대해 설명하시오

### Web cache 에 대해 설명하시오

### REST 와 RESTFUL 에 대해 설명하시오

### STATEFUL 과 STATELESS 에 대해 설명하시오

### Server 와 Client 에 대해 설명하시오

# Network Programming

### Socket 에 대해 설명하시오, 언어로 구현해보시오

### Socket.io와 WebSocket의 차이를 설명하시오

###

# 홈 네트워킹

### 123.123.123.123 을 차단하려고 한다. 어떻게 하면 차단이 될까?
* Linux 기준
    1. route 명령어로 차단하기
        route add -host 123.123.123.123 reject
        기본적으로 interface를 통해 gateway로 나가던 routing이 사라져
        해당 host -> IP 로 나가는 연결이 막힌다.
    2. 방화벽으로 차단하기
        iptables 는 CentOS 6에서 쓰던 방화벽
        iptables -A INPUT -s 123.123.123.123. -j DROP
        -A INPUT = A(추가)하라. INPUT(들어오는 패킷)에 대해
        -s IP = s(출발지주소)가 IP면
        -j DROP = jump 하라. DROP(버리기)로
* Network Device 기준
    1. Standard ACL
        Router> enable
        Router# confiture terminal
        Router(config)# access-list 1 deny 123.123.123.123 0.0.0.0
        Router(config)# access-list 1 permit any
        wildcard mask 이므로 subnet 과는 1,0이 반대임에 주의
    2. Extended ACL
        Router(config)# access-list 101 deny ip 127.0.0.0 0.0.0.255 123.123.123.123 0.0.0.0
        Router(config)# access-list 101 permit any
        Router(config)# access-list 110 deny tcp 127.0.0.0 0.0.0.255 123.123.123.123 0.0.0.0 eq 80
        Router(config)# access-list 101 permit any
        1. Interface 적용
            Router(config)# interface serial 0/0
            Router(config-if)# ip access-group 1 in
            inbound 에 적용해야함에 주의
        3. Routing 적용
            Router(config)# router rip
            Router(confing-router)# distribute-list 1 in serial 0/0
            distribute list 는 주로 outbound 에 적용한다.(송신측에서 설정한다.)
            routing AD 를 줄여 대역폭과 리소스 낭비를 막는다.
            Router(config)# router rip
            Router(confing-router)# offset-list 1 in 16 serial 0/0
            offset list 는 주로 inbound 에 적용한다. (수신측에서 설정한다.)
            차단이 아닌 hop 증가임에 주의
        5. vty 적용
            Router(config)# line vty 0 4
            Router(config-line)# access-class 1 in
            Router에 접근하는 telnet 접근 차단임에 주의

### 브라우저로 구글(google.com)에 접속시 페이지를 띄우기 까지 과정을 자세히 설명하시오
* local host → local DNS(+ARP) → 루트 DNS 서버(+ARP) → .com DNS 서버 → test.com DNS 서버 순서대로 www.test.com에 해당하는 IP주소 요청하고, 있다면 그 서버에서 바로 주소를 받음
* 
* TCP 통신을 통해 소켓 개방
* HTTP 프로토콜로 요청
* 라우팅 중 프록시 서버를 만나면 웹 캐시에 저장된 정보를 response 받음
* 프록시 서버를 만나지 못해 www.test.com를 서빙하는 서버까지 가면 요청에 맞는 데이터를 response로 전송함
* 브라우저의 loader가 해당 response를 다운로드 할지 말지 결정
* 브라우저의 웹 엔진이 다운로드한 .html 파일을 파싱해 DOM 트리를 결정
* .html 파싱중 script 태그를 만나면 파싱을 중단함
* script 태그에 있는 자원을 다운로드해 처리가 완료되면 다시 파싱 함
* CSS parser가 .css 파일을 파싱해 스타일 규칙을 DOM 트리에 추가하고 렌더 트리를 만듦
* 렌더트리를 기반으로 브라우저의 크기에 따라 각 노드들의 크기를 결정
* 렌더링 엔진이 배치를 시작(페인팅)
* https://parksb.github.io/article/36.html
### Gateway 란?

# 기타

### STP FTP UTP 차이?
* STP
    * Spanning Tree Protocol (Switch topology configuration을 위한 프로토콜)
    * Shielded Twisted Pair(LAN Cable 의 한 종류 UTP 보다 잡음에 강해 신호전송길이가 긺, 전체 은박 + pair 끼리 은박)
* FTP
    * File Transfer Protocol (7계층 파일 전송을 위한 프로토콜)
    * Foiled Twisted Pair (LAN Cable 의 한 종류로 STP 보단 약함, 전체 은박)
* UTP
    * Unshielded Twisted Pair (기본 LAN Cable)
* 보통 cable 로서 STP, FTP 를 볼 일이 없기 때문에 연관없는 프로토콜들이다.
(UTP는 프로토콜이 아니므로 제외)
### delay, timing(jitter), throughput 차이를 설명하시오
