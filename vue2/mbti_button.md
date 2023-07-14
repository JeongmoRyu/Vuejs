# mbti button

components/HelloWorld.vue

```jsx
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
```

components/MbtiButton.vue

```jsx
<template>
  <div class="btn" :class="{ 'selected': selected }">
    <span>{{ label }}</span>
    <span>{{ desc }}</span>
    <span>{{ longDesc }}</span>
  </div>
</template>

<script>
export default {
  name: 'MbtiButton',
  props: {
    label: String,
    desc: String,
    selected: Boolean,
    longDesc: String,
  }
}
</script>

<style scoped>
.btn {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 45%;
  height: 80px;
  border: 1px solid dodgerblue;
  border-radius: 10px;
  cursor: pointer;
}

.selected {
  background-color: aquamarine;
}
</style>
```

components/MbtiButtonBoard.vue

```jsx
<template>
  <div>
    <div class="btn-row">
      <MbtiButton label="E" desc="외향형" 
      long-desc="자기 외부에 주의 집중" :selected="clicked.includes('E')" @click.native="handleClick(0, 'E')" />
      <MbtiButton label="I" desc="내향형" :selected="clicked.includes('I')" @click.native="handleClick(0, 'I')" :long-desc="clicked.join('')" />
    </div>
    <div class="btn-row">
      <MbtiButton label="S" desc="감각형" @click.native="handleClick(1, 'S')" :selected="clicked.includes('S')" />
      <MbtiButton label="N" desc="직관형" @click.native="handleClick(1, 'N')" :selected="clicked.includes('N')" />
    </div>
    <div class="btn-row">
      <MbtiButton label="T" desc="사고형" @click.native="handleClick(2, 'T')" :selected="clicked.includes('T')"/>
      <MbtiButton label="F" desc="감각형" @click.native="handleClick(2, 'F')" :selected="clicked.includes('F')"/>
    </div>
    <div class="btn-row">
      <MbtiButton label="J" desc="판단형" @click.native="handleClick(3, 'J')" :selected="clicked.includes('J')"/>
      <MbtiButton label="P" desc="인식형"  @click.native="handleClick(3, 'P')" :selected="clicked.includes('P')"/>
    </div>
    <button @click="emitToParent">Emit to parent</button>
  </div>
</template>
<script>
import MbtiButton from './MbtiButton.vue'

export default {
  name: 'MbtiButtonBoard',
  data: function () {
    return {
      selected: true,
      clicked: [0, 0, 0, 0]
    }
  },
  components: {
    MbtiButton
  },
  methods: {
    emitToParent() {
      this.$emit('child-to-parent', this.clicked.join(''))
    },
    toggleSelected: function () {
      this.selected = !this.selected
    },
    // clicked array에 index 위치에 label을 할당한다.
    handleClick(index, label) {
      this.$set(this.clicked, index, label)
    }
  }
}
</script>

<style scoped>
.btn-row {
  display: flex;
  justify-content: space-evenly;
  margin-bottom: 10px;
}
</style>
```

App.vue

```jsx
<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Hello SFC!!"/>
    <!-- <h1>Hello VUE!</h1> -->
    <MbtiButtonBoard @child-to-parent="getChildToParentEvent" />
    <p>Nice to meet you!!!</p>
  </div>
</template>

<script>
// import MbtiButton from './components/MbtiButton.vue'
import MbtiButtonBoard from './components/MbtiButtonBoard.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    // MbtiButton,
    MbtiButtonBoard,
  },
  methods: {
    getChildToParentEvent(emittedData) {
      console.log(emittedData)
      // location.href = 'https://www.16personalities.com/ko/%EC%84%B1%EA%B2%A9%EC%9C%A0%ED%98%95-' + emittedData
      window.open('https://www.16personalities.com/ko/%EC%84%B1%EA%B2%A9%EC%9C%A0%ED%98%95-' + emittedData, '_blank')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/* .btn-row { 
  display: flex;
  justify-content: space-evenly;
  margin-bottom: 10px;
} */

</style>
```