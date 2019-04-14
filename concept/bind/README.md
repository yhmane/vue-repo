## bind
#### {{}} 를 이용하여 Data의 값을 html안에 뿌려 주었음.<br/> 하지만, HTML Tag의 속성 값에 Data의 값을 이용하면 에러가 발생.<br/> => bind를 이용하여 데이터를 묶어 줌

```html
<div id="app">
    <span v-bind:title="message">cursor the pointer</span>
</div>
```
```javascript
const app = new Vue({
    el: '#app',
    data: function() {
        return {
            message:'This page loaded on ' + new Date()
        }
    }
})
```


## model
#### bind와 기능은 똑같으나 차이점이 있음<br/> bind은 Data->View의 단방향으로 업데이트가 이루어짐<br/> 하지만, model의 경우 Data<->View 양방향으로 업데이트가 이루어짐

```html
<div id="app">
    <input v-model="message" type="text"/>
    <div>{{message}}</div>
</div>
```
```javascript
const app = new Vue({
    el: '#app',
    data: function() {
        return {
            message:""
        }
    }
})
```

### Vue.js Reference Guide
* https://kr.vuejs.org/v2/guide/index.html