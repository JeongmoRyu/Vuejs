# v-bind_oneway

```html
<template>
  <div>
    <div>JM's Vue3</div>
    <div class="name">
      {{name}}
    </div>
    <input v-bind:type="type" v-bind:value="name">
    <!-- v-bind: == : -->
    <!-- 똑같이 작동한다. -->
    <button class="btn btn-primary" v-on:click="updateMenu">
      Click
    </button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const name = ref('Lobstar')
    const type = ref('text')
    const nameClass = ref('name')

    const updateMenu = () => {
      name.value = 'Lobstar Plus Shrimp'
      type.value = 'text'
      nameClass.value = 'name'
      console.log(name)
    }
    return {
      name,
      type,
      updateMenu,
      nameClass
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