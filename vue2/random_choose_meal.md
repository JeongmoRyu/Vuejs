# random choose meal

```jsx
<template>
  <div class="home">
    <h1>점심메뉴</h1>
    <p v-if='randomLunch'>점심으로 당첨 : {{ randomLunch }}</p>
    <button @click="getRandomLunch">오늘의 점심은??</button>
    <HelloWorld/>
    
  </div>
</template>

<script type="module">
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'LunchView',
  components: {
    HelloWorld
  },
  data() {
		return {
			myArray: ['국밥', '스테이크', '파스타', '치킨', '피자', '볶음밥', '짜장면'],
      randomLunch: '',
		}
	},
  methods: {
    getRandomLunch() {
			const randomIndex = Math.floor(Math.random() * this.myArray.length)
			this.randomLunch = this.myArray[randomIndex]
		}
	}
}

</script>
```