# Data Binding
- html하드코딩하면 변경 어려움
- vue의 실시간 자동 렌더링 활용하기 위해 사용
- 변경이 필요없으면 데이터 바인딩 안해도 됨.
- HTML 속성도 데이터 바인딩 가능

# v-for
```js
<a v-for="작명 in 3" :key="작명"></>
// key 의 용도
// - 반복문 쓸 때 꼭 써야함
// - 반복문 돌린 요소를 컴퓨터가 구분하기 위해 씀
```

# event handler
```js
@click=""
```
- vue에서는 @click으로 클릭시 이벤트 발생하게 할 수 있음
- 함수안에서 데이터 쓸 때는 this.데이터명

# modal
- 상세 이미지 같은 느낌
- vue router 설치하면 다른 창으로도 가능
- 모달 창 미리 만들어 놓기
- ui 현재 상태를 데이터로 저장, 데이터에 따라 어떻게 보일지 작성

# v-if
```js
v-if = "조건식"
```
- 조건식 참일 때 보여줌

# import / export
```js
export default 변수명
import 변수명 from '파일경로'
export {a,b}
import {a} from '...' //변수명 그대로
```
- HTML 태그안의 속성 데이터 바인딩은 :어쩌구
- HTML 태그안의 내용 데이터 바인딩은 {{어쩌구}}