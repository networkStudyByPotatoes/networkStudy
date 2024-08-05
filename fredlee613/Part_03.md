# Part3. TCP/IP와의 만남

## TCP/IP
- TCP(Transmission Control Protocol)
- IP (Internet Protoccol)
- ARPANET에 의해서 개발되었음.
- 고유의 주소값을 가지기 때무에 다른 네트워크에 연결되어있는 호스트에게 데이터를 전달할 수 있다.
- 10진수 4자리로 표현된다. (편의상)
- 사실은 이진수 32자리로 표기되는 것이다. (1 ~255.1 ~255.1 ~255.1 ~255) 


## OSI 7 Layer에서의 TCP/IP
- TCP/IP 계층: 애플리케이션(OSI 7 ~ 5) > 트랜스포트(OSI 4) > 인터넷(OSI 3) > 네트워크 액세스 계층(OSI 2 ~ 1)

## IP 주소 
- IP주소는 모든 사용자가 고유한 IP 주소 값을 가진다.

## 한정된 IP 주소를 위한 관리 방법
- NAT(Network Address Translation): 공인 IP 하위에 사설 IP주소를 사용하여 하나의 공인 IP를 통하여 여러 IP 주소를 활용할 수 있는 방법. 
- PAT(Port Address Translation): 동일한 IP 주소에 대하여 port 번호로 구분하는 방법
- [NAT/PAT/포트 포워딩에 대한 게시글입니다.](https://hooni-playground.com/661/)

## DHCP(Dynamic Host Configuration Protocol)
- 동적으로 내부 네트워크의 IP 주소 배정을 하는 방식.
- 내부 네트워크의 장치가 켜질 시 내부 네트워크에 브로드캐스팅을 진행.
- 이를 수신한 DHCP서버가 고유한 사설 IP 주소를 반환.
- 이로 인하여 내부 네트워크에 소속된 장치들의 IP 주소를 자동으로 관리할 수 있음.
