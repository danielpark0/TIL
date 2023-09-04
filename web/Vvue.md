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
```js
v-else
```
- 조건식 참이 아닐 때 보여줌
- else if 도 가능

# import / export
```js
export default 변수명
import 변수명 from '파일경로'
export {a,b}
import {a} from '...' //변수명 그대로
```
- HTML 태그안의 속성 데이터 바인딩은 :어쩌구
- HTML 태그안의 내용 데이터 바인딩은 {{어쩌구}}

# Component
1. vue 파일 import 하고
2. 등록하고
3. 쓰기
## 쓰는 이유
- 보기 좋음
- 재사용 쉬움
- 한번에 변경하기 쉬움
## 문제
- 너무 많이 쓰면 데이터 관리 어려움

# Props
- 부모 데이터를 자식이 쓰고 싶을 때 씀
1. 데이터 보내고
2. 등록하고
3. 쓰기
- props 받아온건 read-only

# emit
- 부모에게 메지를 보낼 떈 custom event
``` $emit('작명', 데이터)```
- 자식이 보낸 데이터는
``` $event``` 변수에 담겨있음

# v-model
- 사용자 input 받을 때 사용할 수 있음
```v-model="데이터 이름"```

# watcher
- data 감시할 때 쓰면 됨.
- ex) input에 문자 입력하면 경고 띄우고 싶다.
```watch: {감시할데이터(){}}```

# animation
- transition

```<transition name="작명"></transition>```

```
.작명-enter-from{시작스타일}
.작명-enter-active{transition}
.작명-enter-to{끝날때스타일}
```
```
.작명-leave-from{시작스타일}
.작명-leave-active{transition}
.작명-leave-to{끝날때스타일}
```

# sort, data 보존
- array/object 데이터의 각각 별개의 사본을 만들려면

``` [...array자료] ```
- 등호로 array를 집어넣으면 왼쪽 오른쪽 값 공유해주세요 임

# lifecycle
- 컴포넌트는 웹페이지에 표시되기까지 일련의 과정을 거침
- create -> mount -> 컴포넌트 생성 -> update(컴포넌트 재랜더링) -> unmount
- lifecycle hook을 걸어서 중간에 원하는 코드 실행가능
- 서버에서 데이터 가져올때도 lifecycle hook 안에 코드 짬

# HashMode
```
import { createRouter, createWebHashHistory } from 'vue-router'

const router = [];
const router = createRouter({
  history: createWebHashHistory(),
  routes,
})
```
- 이렇게 하면 Hash Mode
- URL에 #이 붙은채로 시작하고, # 뒤에 있는 내용은 서버에 전달되지 않음.

# Navigation guards
- 특정 URL로 접속할 때 뭔가 코드를 실행하고 싶은 경우 사용