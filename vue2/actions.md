# actions

- App.vue

```jsx
// 

export default {
  name: 'App',
  created: function () {
    this.$store.commit('fetchTodoList')
  },
}
```

- store/index.js

```jsx
// 
actions : {
  fetchTodoList: async function ({ commit }) {
    const requestUrl = 'http://localhost:8000/api/v1/todos/'

    const response = await axios.get(requestUrl)
    commit('TODO_LIST_SUCCESS', response)
  },
}
```