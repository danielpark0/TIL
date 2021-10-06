### V1 : 프론트 컨트롤러 도입

- 기존 구조를 최대한 유지하면서 프론트 컨트롤러를 도입

### V2 : View 분류

- 단순 반복되는 뷰 로직 분리

### V3 : Model 추가

- 서블릿 종속성 제거
- 뷰 이름 중복 제거

### V4 : 단순하고 실용적인 컨트롤러

- V3와 거의 비슷
- 구현 입장에서 ModelView를 직접 생성해서 반환하지 않도록 편리한 인터페이스 제공

### V5 : 유연한 컨트롤러

- 어댑터 도입
- 어댑터를 추가해서 프레임 워크를 유연하고 확장성 있게 설계