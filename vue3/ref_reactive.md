# ref reactive

- button은 bootstrap을 적용하였습니다.

```html
<template>
  <div>
    <div>JM's Vue3</div>
    <div class="name">
      {{name}}
    </div>
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
    
    // const dinner = (name) => {
    //   return 'I want to eat dinner' + ' with '+name
    // } 

    // const eat = dinner(name)
    const updateMenu = () => {
		name.value = 'Lobstar Plus Shrimp'
    console.log(name)
    }
    return {
      name,
      updateMenu
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

→ 버튼을 눌리면 Lobstar가

Lobstar Plus Shrimp로 바뀐다.