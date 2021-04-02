# 네트워크 계층

- OSI 7 Layer 3계층으로 패킷 포워딩과 네트워크 간 라우터를 통한 라우팅 수행
- IP 주소를 사용하여 통신, 계층적 구조
- 대표적인 장비는 라우터, 또는 L3라고 부른다.

## IP(Internet Protocol)

- 네트워크 계층에서 통신하는 주요 프로토콜로 라우팅을 구현하고 본질적인 인터넷을 구축하는 계기
- 구조 : 헤더와 페이로드로 구성되어있음.
  - 헤더는 목적지 & 출발지 IP 주소등을 포함, 페이로드는 전송되는 데이터를 의미
  - IP v4 헤더 구조
    - Version : IP 버전, IPv4
    - Header Length : gpejdml rlfdl
    - Type of Service : 서비스 품질
    - Total Packet Length : Ip 패킷 전체 길이
    - Identifier, Flags, Offset : IP Fragment 필드로 단편화와 재조합
    - Time to Live : IP 패킷 수명
    - Protocol ID : 데이터에 포함되어 있는 상위계층의 프로토콜
    - Header Checksum : 오류 검출

- 네트워크와 호스트
  - IP 주소는 네트워크 부분과 호스트 부분으로 나뉨
  - 네트워크는 브로드캐스트 영역, 호스트는 개별 단말기