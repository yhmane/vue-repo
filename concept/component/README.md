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
* 하지만 vue는 단방향 통신이고, 자식에 의해 부모가 바뀌는 불상사를 막기 위해 자식이 부모에게 data를 전달할 수 없음. 즉, 하위 컴포넌트의 템플릿에서 상위 데이터를 직접 참조 할 수 없으며 그렇게 해서는 안됨. 데이터는 props 옵션 을 사용하여 하위 컴포넌트로 전달 될 수 있음.


### Vue.js Reference Guide
* https://kr.vuejs.org/v2/guide/components.html