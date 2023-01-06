## Vue.js - 웹 프론트엔드 프레임워크

- 컴포넌트 기반의 SPA를 구축할 수 있게 해주는 프레임 워크

### 컴포넌트

- 웹을 구성하는 로고, 메뉴바, 버튼, 모달창 등 웹 페이지 내의 다양한 UI 요소
- 재사용 가능하도록 구조화 한 것

### SPA

- 단일 페이지 어플리케이션
- 하나의 페이지 안에서 필요한 영역만 로딩 되는 형태
- 빠른 페이지 변환
- 적은 트래픽 양

### LifeCycle

- before create
- created
- before mount
- mounted
- before update
- updated
- before destroy
- destroyed


## MVVM 패턴의 뷰모델 레이어에 해당하는 화면 단 라이브러리

View -> Dom Listener -> Model -> DataBinings -> View

### Object.defineProperty()
- 객체의 동작을 재정의 하는 API
```
Object.defineProperty(대상객체, 객체의 속성, {
    //정의할 내용
})
```

> VUE - 데이터의 변화를 라이브러리에서 감지해서 알아서 화면을 자동으로 그려줌 Reactivity

## 인스턴스
```
new Vue();
```
인스턴스를 생성하면 변수안에 인스턴스 내용 담을 수 있음.
- 생성자 함수를 이용해서 만들어놓은 함수를 갖다 쓸수있도록

## 컴포넌트
영역별로 화면을 구분해서 개발할 수 있는 뷰의 기능
재사용성이 올라가고 빠르게 화면을 제작할 수 있음
```
// 전역 컴포넌트
Vue.component('app-header',컴포넌트 내용);

// 지역 컴포넌트
components: {
    '컴포넌트 이름' : 컴포넌트 내용
}
```

- 컴포넌트는 각각 고유한 데이터 유효 범위를 갖는다.
- 상위 -> 하위 props, 하위 -> 상위 event

## Props
```
<app-header v-bind:프롭스 속성 이름="상위 컴포넌트의 데이터 이름"> </app-header>
```

## Event
- 하위 컴포넌트에서 상위 컴포넌트 메소드호출
```
<app-header v-on:하위 컴포넌트에서 발생한 이벤트 이름="상위 컴포넌트의 메서드이름">

var appHeader = {
    methods: {
        passEvent: function() {
            this.$emit('pass');
        }
    }
}
```

## 같은 레벨에서의 컴포넌트 통신 방법
- 상위로 event통해서 전달하고,
- 하위로 props통해서 다시 전달
- 이런 규칙을 지켜가면서 개발하면됨.

## 뷰라우터
- 뷰 라이브러리를 이용하여 싱글 페이지 애플리케이션을 구현할 때 사용하는 라이브러리
```
<router-view></router-viewddd>
```