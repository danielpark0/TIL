## Http

- WWW 상에서 정보를 공유하는 프로토콜 Port 80 HTML
- WWW - 전세계에 연결된 인터넷을 통해 정보를 공유
- HTML - 웹페이지 언어

### URL - 웹 페이지를 찾기 위한 주소

### HTML - 웹 페이지 언어

### HTTP Request

- Client가 Server에게 특정 Method를 사용하여 요청
- Head, Body로 구성
- HTTP Method : 요청의 목적 - GET, POST, PUT, HEAD, DELETE
- GET : 리소스 요청, POST : 내용 전송, PUT : 내용 갱신
  HEAD : 리소스에 대한 정보만 요청, DELETE : 리소스 제거
- Request Target : 리소스 경로

#### Head

- accept : 클라이언트가 허용 가능한 파일 형식
- User-Agent : 클라이언트의 OS, 브라우저 정보
- Host : 서버의 도메인 네임

### HTTP Response

- Client 요청에 따른 Server 응답
- HEAD + Body
- version : HTTP 버전, Status : 상태, Status Message : 상태 메시지
- Date, Content-location, etag : 캐시 정보 업데이트
- Last-modified : 요청한 데이터의 최종 수정일
- Content-Length : 요청한 데이터 길이

#### Status Code

- 200 - OK
- 307 - Temporary Redirect
- 400 - Bad Request
- 401 - Unauthorized
- 404 - Not Found
- 500 - Internal Server Error
- 502 - Bad Gateway
- 503 - Service Unavailable

## HTTP 속성

### Stateless

- Http는 통신이 끝나면 상태 정보를 유지하지 않는다
- 서버는 HTTP 요청에 대한 응답을 보내고 접속을 끊어 커넥션 리소스 비용을 줄인다.
- 단순 페이지 또는 문서 정보 열람은 가능
- 하지만 클라이언트가 새로운 페이지를 접속 할 때마다 서버는 신원을 알 수 없다
- 예를들어 인터넷 쇼핑몰의 경우 페이지 마다 인증 필요
- 해결책 -> Cookie & Session

#### Cookie - 클라이언트 웹 브라우저 로컬에 저장되는 키와 값이 들어있는 파일

#### Session - 서버에 정보를 저장(안전) - 인증에 세션을 사용 - 보안을 위해 HTTPS - SSL/TLS

#### SSL/TLS

- TCP/IP 네트워크 통신간 보안을 제공하는 프로토콜
- 기능
  - 인증 - Client to Server 통신 간 상대방에 대한 인증 RSA, DSS
  - 무결성 - 메시지 인증 코드로 제공 HMAC - MD5, SHA-2
  - 기밀성 - 데이터 암호 - 3DES, RC4

- 동작과정
  1. 클라이언트 지원가능한 cipher suite 전달
  2. 서버는 자신이 지원하는 cipher suite 전달
  3. 서버 인증서 전달
     DH 키교환 - 키 전달
     인증서 요청
     모든 메시지 전달완료
  4. 클라이언트 인증서 전달
     DH, 클라이언트 키 교환
     인증서 확인
     버전, chipher suite 결정, 상대방 신원 확인 완료
  5. CHange CipherSpec Finished