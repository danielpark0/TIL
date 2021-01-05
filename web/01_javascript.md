# JavaScript

- 문법이 철저하지 않음
- 변수 선언할때 타입을 따로 설정 안해도 됨
- 오류가 생겨도 찾기 쉽지 않음

### Node

- npm : node 패키지들을 사용할 수 있도록 관리해주는 도구

### React

- npx : npm 5.2 + 버전의 패키지 실행도구
- 프로젝트 세팅

```bash
npx create-react-app [이름]
cd [이름]
npm start
```

### JS

- script 쓸때 defer 쓰면 페이지가 모두 로드되고 이후에 외부 스크립트 실행
- async 실행순서 보장 안됨
- var, let, const
  - var : 유효범위 구분x. (지역, 전역 변수를 구분 할 수 없음)
  - let : 특정 영역에서 지역변수로 사용할 수 있음.
  - const : 값이 변경되지 않는 상수.

