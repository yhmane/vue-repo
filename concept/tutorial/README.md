## 시작하기

#### Vue.js는 ECHMAScript5를 지원하기 때문에 IE8 버전을 지원하지 않음 <br/>하지만, 모든 ECHMAScript5 호환 브라우저를 지원

* Vue.js script import
```javascript
<!-- 도움되는 콘솔 경고를 포함한 개발 버전  —>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<!-- 속도와 용량이 최적화 된 상용 버전 -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

## 선언적 렌더링
* 간단한 템플릿 구문을 사용해, DOM에 데이터링 렌더링


```html
<div id="app">
  {{message}}
</div>
```
```javascript
const app = new Vue({
    el: '#app',
    data: function() {
        return {
            message: "Hello World"
        }
    }
})
```



### Vue.js Reference Guide
* https://kr.vuejs.org/v2/guide/index.html
