## HttpServletRequest

- 서블릿은 개발자가 HTTP 요청 메시지를 편리하게 사용할 수 있도록 개발자 대신 HTTP 요청 메시지 파싱해서 HttpSErvletRequest 객체에 담아서 제공

### Start Line

- http 메소드
- URL
- 쿼리 스트링
- 스키마, 프로토콜

### Header

- 헤더 조회

### Body

- form 파라미터 형식 조회
- message body 데이터 직접 조회

### 추가 기능

- 임시 저장소 기능
  - 저장 : request.setAttribute(name,value)
  - 조회 : request.getAttribute(name)
- 세선 관리 기능
  - request.getSession(create: true)