OSI 7계층이 어떤 것이 있나?
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

TCP/IP 4계층을 설명하고 OSI 7계층의 차이는?
* 4 응용
    * OSI 7계층에서 7,6,5 를 합친 것. network 관점에서는 응용 프로그래머의 역할이므로 묶었음.
* 3 전송
    * TCP/IP 4계층이므로 TCP를 주로 의미. 오류제어, 흐름제어, 신뢰성
* 2 인터넷
    * OSI 7계층에서 network 에 해당. IP 를 주로 의미. 주소부여, routing.
* 1 네트워크 엑세스(네트워크 인터페이스, 링크)
    * OSI 7계층에서 1,2 를 합친 것. H/W Interface 에 관한 파트이므로 묶었음.
*  OSI는 가이드로서, TCP/IP는 계속 실무의 표준으로 쓰임.


TCP UDP 란? 차이는?

STP FTP UTP 차이?

TCP 3-handshake, TCP 4-handshake 에 대해 설명

* 3-handshake : TCP 세션 맺을 때 사용
    * Client : SYN
    * Server : SYN+ACK
    * Client : ACK
* 4-handshake : TCP 세션 종료 시 사용
    * Client : FIN
    * Server : ACK(and close-wait)
    * Server : FIN
    * Client : ACK


0.0.0.0을 차단하려고 한다. 어떻게 하면 차단이 될까?

쿠키와 세션에 대해 설명

GET과 POST방식의 차이점

HTTP가 무엇인지 설명하시오
