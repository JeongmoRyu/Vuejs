# vue practice 2

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
  <h1>테스트</h1>
  <p id="input1">첫 번째 입력 : {{message1}} </p>
  <input id="inputname1" type="text" v-model="message1">
  <p id="input2">두 번째 입력 : {{message2}}</p>
  <input id="inputname2" type="text" v-model="message2">

  <p id="input3"> 합산 입력 : {{message1}} {{message2}}</p>
</div>

<script type="text/javascript">
   var app = new Vue({
        el : '#app',
        data: {
          message1: '',
          message2: '',

        }
   });
</script>

</body>
```