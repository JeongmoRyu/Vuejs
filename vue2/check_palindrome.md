# check palindrome

```html
<!DOCTYPE html>
<html>
  <head>
  <meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate" />
  <meta http-equiv="Pragma" content="no-cache" />
  <meta http-equiv="Expires" content="-1" />
  <meta charset="utf8">
  <title>Hello, world</title>
  <script src="https://cdn.jsdelivr.net/npm/vue@2.7.8/dist/vue.js"></script>
</head>
<body>
<div id="app">
  <h1>회문 검사기</h1>
  <input type="text" v-model="name">
  <button @click="checkPalin">Check Palin</button>
</div>

<script type="text/javascript">
  var app = new Vue({
    el : '#app',
    data : {
      name: '',
    },
    methods: {
      
      checkPalin: function(name) {
        const Input = document.querySelector('input').value
        const Reverse = Input.split('').reverse().join('')
        if (Input==='') {
          alert('텍스틀를 입력하세요')
        }
        else if (Input===Reverse) {
          alert('회문입니다.')
        }
        else {
          alert('회문이 아닙니다.')
        }
      }
    }
  });

   
</script>

</body>
```