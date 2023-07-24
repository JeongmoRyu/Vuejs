# naming

- vue 3 시작하기

- template과 style을 쓰고 어떻게 변화되는지 확인해보자

```html
<template>
  <div>
    <div>JM's Vue3</div>
    <div class="name">{{name}}</div>
  </div>
</template>

<script>
export default {
  setup() {
    const name = 'Lobstar'

    return {
      name
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