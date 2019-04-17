## event handling
#### v-on 디렉티브를 이용함 <br/> Dom 이벤트를 듣고 트리거 될 때 JavaScript를 실행<br/> 약어로는 @를 사용

```html
<div id="app">
    <p>{{ message }}</p>
    <button v-on:click="reverseMessage">메시지 뒤집기</button>
    <button @click="reverseMessage">메시지 뒤집기</button>
</div>
```
```javascript
const app = new Vue({
  el: '#app',
  data() {
      return {
        message: 'Hello world'
      }
  },
  methods: {
    reverseMessage(){
            this.message = this.message.split('').reverse().join('')
    }
  }
})
```

## 이벤트 수식어
#### 이벤트 핸들러 내부에서 event.preventDefault() 또는 event.stopPropagation()를 호출<br/> Vue.js는 v-on 이벤트에 수식어를 붙여 간단히 해결
* .stop
* .prevent
* .capture
* .self
* .once

```javascript
<!-- 클릭 이벤트 전파가 중단됩니다 -->
<a v-on:click.stop="doThis"></a>

<!-- 제출 이벤트가 페이지를 다시 로드 하지 않습니다 -->
<form v-on:submit.prevent="onSubmit"></form>

<!-- 수식어는 체이닝 가능합니다 -->
<a v-on:click.stop.prevent="doThat"></a>
```

## 키 수식어
#### 키 이벤트도 이벤트 청취시 키코드를 체크함<br/> 이러한 과정을 Vue.js는 키 수식어를 사용하며 쉽게 대체<br/> 약어로 @를 사용
* .enter
* .tab
* .delete (“Delete” 와 “Backspace” 키 모두를 캡처합니다)
* .esc
* .space
* .up
* .down
* .left
* .right

```html
<div id="app">
    <p>enter inputbox <input v-on:keyup.enter="enterInput()"></p>
    <p>enter inputbox <input @keyup.enter="enterInput()"></p>
</div>
```
```javascript
const app = new Vue({
  el: '#app',
  data() {
      return {
      }
  },
  methods: {
    enterInput() {
        alert('enter');
    }
  }
})
```