# function

```html
<template>
  <div>
    <div>JM's Vue3</div>
    <div class="name">
      {{dinner(name)}}</div>
  </div>
</template>

<script>
export default {
  setup() {
    const name = 'Lobstar'
    
    const dinner = (name) => {
      return 'I want to eat dinner' + ' with '+name
    } 
    return {
      name,
      dinner,
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