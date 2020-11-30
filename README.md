# What is View JS?

<img src="./gitImages/View_Logo.PNG" />

## 왜 VueJs 인가

1. 학습 곡선이 낮다.
2. 컴포넌트의 분해
3. 가볍고 빠르다.
4. View 최적화
5. 모듈의 다양성

## CDN

```javascript
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

## NPM

```javascript
npm install vue
```

## 어떻게 사용해요?

```javascript

// Vue.JS 선언문
const app = new Vue({
    el:"#root",
    data: {
        // State
        value:'',
        isTrue:false
    },
    methods: {
        // function
        test() {
            this.value = 'test'
        }
    }
})

// HTML 내에서 변수사용

<div>{{value}}</div>

// if 조건문 사용

// 보이지 않음
<div v-if="isTrue"></div>
// 보임
<div v-else="isTrue"></div>

// state 변경
// text 변경시 state 자동변경
<input type="text" v-model="value" />

// ref

<input type="text" ref="test" />

...
// DOM 에 접근하고 싶은 경우
refTest() {
    this.$refs.test.focus()
}
```
