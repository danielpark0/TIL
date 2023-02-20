# Data Binding
- html하드코딩하면 변경 어려움
- vue의 실시간 자동 렌더링 활용하기 위해 사용
- 변경이 필요없으면 데이터 바인딩 안해도 됨.
- HTML 속성도 데이터 바인딩 가능

# v-for
```js
<a v-for="작명 in 3" :key="작명"></>
```

# event handler
```js
@click=""
```
- vue에서는 @click으로 클릭시 이벤트 발생하게 할 수 있음
- 함수안에서 데이터 쓸 때는 this.데이터명