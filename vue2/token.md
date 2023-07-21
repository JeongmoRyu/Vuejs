# token

- token을 생성하기

```jsx
// Login.vue

methods: {
  login: function () {
      ...

      .then(res => {
				const token = res.data.access
        localStorage.setItem("tokenName", token)
      })
  }
```

- token을 가져와서 isLogin 상태에 따라 확인해주기

```jsx
// App.vue

export default {
  name: 'App',
  data: function () {
    return {
      isLogin: false,
    }
  },
  created: function () {
    const token = localStorage.getItem('tokenName')
    if (token){
		  isLogin = true
    }
    else {
      isLogin = false
    }
  },
}
```

- 삭제할때에는

```jsx
localStorage.removeItem('tokenName')
```

- 새로고침할 때 token 확인하기

```jsx
beforeCreate() {
	this.$store.dispatch("tokenName")
}
```