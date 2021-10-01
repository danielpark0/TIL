## DispatcherServlet

- 스프링 MVC도 프론트 컨트롤러 패턴으로 구현되어 있음
- dispatcher servlet이 프론트 컨트롤러
- Dispatcherservlet이 부모클래스에서 HttpServlet을 상속 받음
- 스프링부트는 DispatcherServlet을 서블릿으로 자동으로 등록하면서 모든 경로 ` urlPatterns=""` 에 대해 매핑

### 요청흐름

- 서블릿이 호출되면 HttpServlet이 제공하는 `service()`가 호출됨.
- 스프링 MVC는 dispatcher servlet의 부모인 FrameworkServlet에서 service를 오버라이드 해두었다.
- FrameworkServlet.service()를 시작으로 여러 메서드가 호출되면서 DispatcherServlet.doDispatch()가 호출됨

## 스프링 부트가 자동 등록하는 핸들러 매핑과 핸들러 어댑터

### HandlerMapping

0 = RequestMappingHandlerMapping : 애노테이션 기반의 컨트롤러인 @RequestMapping에서 사용

1 = BeanNameUrlHandlerMapping : 스프링 빈의 이름으로 핸들러를 찾는다

### HandlerAdapter

0 = RequestMappingHandlerAdapter

1 = HttpRequestHandlerAdapter

2 = SimpleControllerHandlerAdapter



### 뷰 리졸버

스프링부트는 InternalResourceViewResolver라는 뷰 리졸버를 자동으로 등록하는데, 이때 application.properties에 등록한 spring.mvc.view.prefix, spring.mvc.view.suffix 설정정보를 사용해서 등록한다.



## 스프링 부트가 자동으로 등록하는 뷰 리졸버

1 = BeanNameViewResolver : 빈 이름으로 뷰를 찾아서 반환

2 = InternalResourceViewResolver : JSP를 처리할 수 있는 뷰를 반환



@Controller

- 스프링이 자동으로 스프링 빈으로 등록
- 스프링 MVC에서 애노테이션 기반 컨트롤러로 인식(RequestMappingHandlerMapping에서 꺼내 쓸수있는 대상인된다.)

@RequestMapping

- 요청정보를 매핑 해당 URL이 호출되면 이 메서드 호출

`RequestMappingHandlerMapping`은 스프링 빈 중에서 @RequestMapping 또는 @Controller가 클래스 레벨에 붙어있는 경우에 매핑 정보로 인식한다.



