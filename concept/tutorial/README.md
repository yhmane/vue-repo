## 시작하기

#### Vue.js는 ECMAScript5를 지원하기 때문에 IE8 버전을 지원하지 않음 <br/>하지만, 모든 ECMAScript5 호환 브라우저를 지원

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

## 보간법 (Interpolation)
#### 문자열
* 데이터 바인딩의 가장 기본 형태는 “Mustache” 구문(이중 중괄호)을 사용한 텍스트 보간

```html
<span>data: {{ message }}</span>
```
* v-once 디렉티브를 사용할 경우 값이 변하지 않음

```html
<span v-once>data: {{ message }}</span>
```

#### 원시 HTML
* 보간법을 이용하는 경우, html을 만들어서 뿌려줄 수 없음<br/> 그 방안으로 v-html 디렉티브가 있음
```html
<div id="app">
    <div v-html="aLink"></div>
</div>
```
```javascript
const app = new Vue({
    el: '#app',
    data: function() {
        return {
            aLink:"<a src='https://www.naver.com'>Link</a>"
        }
    }
})
```



### Vue.js Reference Guide
* https://kr.vuejs.org/v2/guide/index.html
