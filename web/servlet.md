## Servlet

- urlPatterns의 URL이 호출되면 서블릿 코드가 실행
- HTTP 요청 정보를 편리하게 사용할 수 있는 HttpServletRequet
- HTTP 응답 정보를 편리하게 제공할 수 있는 HttpServletResponse
- 개발자는 HTTP 스펙을 매우 편리하게 사용

서블릿 컨테이너 - WAS 안에서 서블릿 객체를 자동으로 생성, 호출, 종료. 생명주기 관리

- 톰캣처럼 서블릿을 지원하는 WAS를 서블릿 컨테이너라고 함
- 서블릿 객체는 싱글톤으로 관리(같은 서버에서는 모든 고객 요청 동일한 서블릿 객체 인스턴스 접근, **공유 변수 사용 주의**)
- JSP도 서블릿으로 변환되어 사용
- 동시 요청을 위한 멀티 쓰레드 처리 지원