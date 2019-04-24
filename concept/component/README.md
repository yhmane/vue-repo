## 컴포넌트(Component)

#### Vue 웹 어플리케이션 구성품 중의 하나<br/>화면을 블록처럼 조합하여 화면을 구성할 수 있도록 하는 단위<br/>기본 HTML 엘리먼트를 확장하여 재사용 가능한 코드를 캡슐화하는 데 도움이 됨


## 컴포넌트 사용하기

* 전역등록

```html
<div id="app">
    <global-component></global-component>
</div>
```
```javascript
// 등록
Vue.component('global-component', {
  template: '<div>전역 컴포넌트</div>'
})

// 루트 인스턴스 생성
new Vue({
  el: '#app'
})
```

* 지역등록

```html
<div id="app">
    <local-component></local-component>
</div>
```
```javascript
// 등록
var cmp = {
    template: '<div>지역 컴포넌트</div>'
};

new Vue({
    el: '#app',
    components: {
        'local-component': cmp
    }
});
```

## 전달
#### 부모에서 자식으로 props -> 데이터 전달
#### 자식이 부모한테 emit -> (message)
* 하지만 vue는 단방향 통신이고, 자식에 의해 부모가 바뀌는 것을 막기 위해 자식이 부모에게 data를 전달하는 것을 지양. 데이터는 props을 사용하여 하위 컴포넌트로 전달 될 수 있음


## 비 부모-자식간 통신
#### 부모와 자식간에는 props, emit을 이용해 통신을 하였지만 컴포넌트끼리 통신이 필요한 경우도 있음<br/>이벤트 버스를 이용

```javascript
const eventBus = new Vue();
 
Vue.component('child-component1', {
    template: '<div>컴포넌트1<button @click="eventBusTest">show</button></div>',
    methods: {
      eventBusTest() {
        eventBus.$emit('busEvent', 100);
        }
    }
});
 
Vue.component('child-component2', {
    template: '<div>컴포넌트2 값 : {{ number }}</div>',
    created: function() {
        const self = this;
        eventBus.$on('busEvent', function(value){
          self.number += value;
        });
    },
    data: function() {
        return {
          number : 0
        }
    }
});
```

## slot
#### 하위 컴포넌트 템플릿에 최소한 하나의 slot 콘텐츠가 포함되어 있지 않으면 부모 콘텐츠가 삭제 됨<br/> 따라서, element를 유동적으로 사용하고자 하면 template에 slot을 작성


### Vue.js Reference Guide
* https://kr.vuejs.org/v2/guide/components.html
