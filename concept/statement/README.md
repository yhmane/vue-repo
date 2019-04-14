
## 조건문 (Conditional statement)
* v-if
* v-else-if
* v-else
#### 일반적인 조건문과 같다.v-if와 v-else-if엔 비교 필드값이 들어 오지만, v-else는 없다.

```html
<div id="app">
    <p v-if="seen">{{message}}</p>
    <p v-else>Good bye</p>
</div>
```
```javascript
const app = new Vue({
    el: '#app',
    data: function() {
        return {
            message: "Hello World",
            seen: true
        }
    }
})
```

* v-show
#### true일 경우 show하여 준다. false일 경우에는 display:none이 됨

```html
<div id="app">
    <p v-show="seen">{{message}}</p>
    <p v-show="unseen">Good bye</p>
</div>
```
```javascript
const app = new Vue({
    el: '#app',
    data: function() {
        return {
            message: "Hello World!",
            seen: true,
            unseen: false
        }
    }
})
```

#### v-if와 v-show의 차이는 Rendering에 있다.<br/> v-if는 lazy rendering을 하기 때문에 true일 경우에만 객체를 렌더링 함.<br /> 자주 바뀌는 경우라면  v-show를 runtime에 바뀌지 않는다면 v-if를 사용하는 것이 적합



## 반복문 (Loop)
* v-for 구문을 이용하여 반복 순회


```html
<div id="app">
    <ul>
        <li v-for="todo in todoList">
            {{todo}}
        </li>
    </ul>
</div>
```
```javascript
const app = new Vue({
    el: '#app',
    data: function() {
        return {
            todoList: [
                "tiger",
                "lion",
                "elephant"
            ]
        }
    }
})
```

### Vue.js Reference Guide
* https://kr.vuejs.org/v2/guide/index.html