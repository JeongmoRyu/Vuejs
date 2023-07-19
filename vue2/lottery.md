# lottery

```jsx
<template>
  <div class="Lotto">
    <h1>This is an Lotto page</h1>
    

    <hr>

    <h2>당첨 숫자</h2>
    
    <button @click="getRandomLotto">Click To Check Lottery</button>
    <p v-if='randomLotto'>당첨번호 : {{ randomLotto }}</p>

  </div>
</template>
<script>

export default {
  name: 'LottoView',

  data() {
		return {
      randomLotto: [0, 0, 0, 0, 0, 0],
    
		}
	},
  methods: {
    getRandomLotto() {
      let usedNum = []
      let i = 0
      while (i < 6) {
        let randomIndex = Math.floor(Math.random() * 45)
        if (usedNum.includes(randomIndex)){
          continue
        } else {
          usedNum.push(randomIndex)
          this.$set(this.randomLotto, i, randomIndex+1) 
          i++
        }        
      }
		},    
	}
}
</script>
```