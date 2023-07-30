# v-model_twoway

```html
<template>
  <div>
    <div>JM's Vue3</div>
    <div class="name">
      {{name}}
    </div>
    <input type="text" :value="name" @input="updateName">
    <button class="btn btn-primary" @click="onSubmit">
      Click
    </button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const name = ref('Lobstar')

    const onSubmit = () => {
      console.log(name.value)
    }
    const updateName = (e) => {
      name.value = e.target.value
    }
    return {
      name,
      onSubmit,
      updateName
    }
  }
}
</script>

<style>
.name {
  color: paleturquoise;
  font-size: 30px;
}
</style>
```

vuejs가 자체적으로 해주는 v-model

```html
<template>
  <div>
    <div>JM's Vue3</div>
    <div class="name">
      {{name}}
    </div>
    <input type="text" v-model="name">
    <button class="btn btn-primary" @click="onSubmit">
      Click
    </button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const name = ref('Lobstar')

    const onSubmit = () => {
      console.log(name.value)
    }

    return {
      name,
      onSubmit,
      
    }
  }
}
</script>

<style>
.name {
  color: paleturquoise;
  font-size: 30px;
}
</style>
```